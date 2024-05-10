---
title: "Management VPN"
---

## Overview

This document outlines the setup and configuration of the management VPN when a MikroTik router is integrated into the
MikroCloud platform.
The management VPN facilitates secure management and operational monitoring through an OpenVPN
tunnel.

## VPN Connectivity

The management VPN uses OpenVPN, configured to connect to `mgnt.mkcld.io` over `TCP` port `8443`. This configuration is
particularly resilient for routers situated behind NAT firewalls, ensuring stable connectivity under various network
conditions.

The choice of TCP is due to its reliability in maintaining connections through such environments.

![Management VPN](https://cdn.mkcld.io/2a70b135b38784654965b562a2444b415f22af74993a5163f3431ea0e362d0bb.png)


## Regional Management Clusters

The VPN tunnels terminate on regional management clusters that use geographical DNS routing to optimize connection
paths. For instance, a router located in Belgium might connect through a cluster in Germany, in which
case `mgnt.mkcld.io` would resolve to `europe1.mkcld.io`.

These clusters are part of a high-availability strategy, consisting of multiple servers
behind a load balancer, enhancing scalability and reliability. The system includes active health checks every five
minutes to ensure all regional clusters remain accessible. In the case of regional outages, connections are rerouted to
the
nearest operational cluster.

:::warning
Our DNS servers will automatically resolve to the nearest operational cluster. Therefore, it is important not to add
static DNS entries or routes that attempt to alter how the VPN connects to the management cluster.
:::

See the list of [Regional Servers](/documentation/resources/regional-servers) for more information.

## Identification and Authentication

Each management VPN tunnel is uniquely identified by a v4 UUID, which is specific to each site. This UUID is also used
as the name for the VPN, providing a clear link between the tunnel and its associated site. The corresponding PPP
profile carries the same name, ensuring consistency across configurations.

## Security and IP Addressing

The management tunnel employs AES CBC encryption for securing data, with the server handling all certificate
requirements. This means there is no need for manual certificate installation on the MikroTik routers. VPN tunnels
operate within the RFC reserved address space for CGNAT (`100.64.0.0/10`) to avoid conflicts with private network
addresses used within customer infrastructures.

## Management Traffic Types

The management VPN serves as a secure conduit for various types of operational data including:

- BGP security feeds
- DNS requests for content filtering
- TrafficFlow data
- SNMP data
- Synchronous API calls
- System logs
- Management access for users

The management VPN is restricted to transporting only the listed types of traffic.
It does not support connection to other MikroTik routers or any unlisted data types.

## Logging and Monitoring

OpenVPN logs from regional servers are streamed and parsed. We record the following information:

- The originating IP address
- Authentication attempts
- Connection establishment and teardown events
- Data transfer metrics
- ICMP latency metrics
- Metadata that helps us identify the regional server

This data aids in diagnosing and optimizing VPN performance.

## Remote Management and Recovery

In the event of accidental tunnel deletion, the tunnel can be recreated through the site overview in the MikroCloud
portal. This action triggers a job that clears all previous configurations for the tunnel on the MikroTik router and
recreates it based on the latest parameters.

## API Usage and Restrictions

Changes to the router configuration are generally not performed through the synchronous API due to its limitations in
delivery assurance and lack of idempotent request handling. This API is primarily used for real-time read operations
such as streaming interface traffic, log events, and traffic data to websockets for portal viewing. It also handles
tasks that could interrupt asynchronous operations, such as router reboots.
