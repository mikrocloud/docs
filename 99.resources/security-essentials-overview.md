---
title: Security Essentials Overview
toc: false
---

This document provides an overview of the essential security policies available in MikroCloud's Security Essentials service. These policies include various IP address block lists and threat intelligence resources designed to protect your network from malicious activities. Each category and IP list is updated **daily** to ensure the most current protection against emerging threats.

#### RFC1918
RFC 1918 defines IP address ranges for private networks:
* 10.0.0.0 - 10.255.255.255 (Class A)
* 172.16.0.0 - 172.31.255.255 (Class B)
* 192.168.0.0 - 192.168.255.255 (Class C)

These IP addresses are intended for use within private networks, and theyre not routed on the public internet. It is recommended to turn this on unless it conflicts with VPN or private routing.

:::Note
This is the only category that only updates **monthly**.
:::


#### FullBogons by Team Cymru
This list contains IPs that are not assigned to any specific organization or individual and should not originate any legitimate traffic on the internet. These addresses are sometimes used in malicious activities such as spoofing attacks.

#### FireHOL Level1
This list includes IPs that have been observed engaging in malicious activity, such as spamming, scanning, brute force attacks, and more. The list is composed of the most aggressive IPs that should, in most cases, be blocked entirely.

#### Emerging Block IPs by Emerging Threats
This list includes sources of spam, known botnets, command and control servers, scanners, and more. The list is derived from a variety of data sources, including network telemetry, malware research, and other threat intelligence feeds.


#### Compromised IPs by Emerging Threats
This list includes hosts associated with malicious activities, including spamming, launching distributed denial-of-service (DDoS) attacks, serving as part of a command and control network for malware, or conducting malicious activities.

#### Feodo Tracker (Malware)
The Feodo Tracker IP address block list is a specialized threat intelligence resource that tracks and lists IP addresses associated with the Feodo family of malware, which includes versions like Cridex, Dridex, Emotet, and Heodo.

#### CINS Score by Sentinel IPs
This blocklist include IP's based on a risk rating assigned to hosts based on various factors, such as the type of malicious activity the IP has been involved in, how recent the activity was, and whether the IP has been a repeated offender.

#### DOH and DOT (DNS)
This list includes IP addresses associated with known DNS over HTTPS (DoH) and DNS over TLS (DoT) servers. It is recommended to enable this when using DNS based content filtering.

:::Warning
Enabling this category will block access to commonly used public DNS providers like Quad9, Cloudflare, and Google. 
:::

#### The Onion Router (TOR)
This list includes the IP addresses of all nodes in the TOR network. TOR is a system that enables anonymous communication over the internet by directing internet traffic through a worldwide network of servers.

#### AlienVault Reputation IP Address Block List
This block list is generated using data from AlienVault's extensive network of threat intelligence sources, including both proprietary research and data shared through the Open Threat Exchange (OTX) platform.