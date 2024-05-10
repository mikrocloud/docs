---
title: "Regional Servers"
---

## Purpose of Regional Servers

Our regional servers play a crucial role in the robustness and efficiency of the MikroCloud management VPN
infrastructure.

Positioned strategically across various geographical locations, these servers ensure optimal routing,
reduced latency, and improved redundancy for all management traffic between MikroTik routers and our management system.

This design ensures that our management plane does not rely on a single piece of hardware,
thereby significantly mitigating potential points of failure.

## Available Regional Servers

The following is a list of our regional servers and their respective locations:

| Location                        | FQDN                 | IP Address       |
|---------------------------------|----------------------|------------------|
| 🇩🇪 Frankfurt, Germany         | `europe.mkcld.io`    | `45.63.116.182`  |
| 🇿🇦 Johannesburg, South Africa | `africa.mkcld.io`    | `139.84.235.246` |
| 🇦🇺 Melbourne, Australia       | `australia.mkcld.io` | `67.219.108.29`  |
| 🇺🇸 Seattle, USA               | `usa.mkcld.io`       | `45.77.214.231`  |

_Last updated: 10 May 2024_

## Geographical DNS Routing

Geographical DNS routing is instrumental in our approach to managing how routers connect to our regional servers. This
technique allows us to direct VPN traffic to the nearest available regional management cluster based on the geographical
location of the MikroTik router.

For example, if a router is operating within Belgium, DNS queries to `mgnt.mkcld.io` will be intelligently resolved
to `europe1.mkcld.io`, which would typically denote our server cluster located in Germany.
