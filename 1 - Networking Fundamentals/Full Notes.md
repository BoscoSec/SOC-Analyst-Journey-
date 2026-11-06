
# Networking Fundamentals for SOC Analysts

## Introduction

Networking is one of the most important foundations
of cybersecurity.

As a SOC analyst, I need to understand how devices
communicate, how data travels across networks, and
how to identify suspicious network activities.

This documentation covers six fundamental topics.

---

# 1. OSI Model

## What is the OSI Model?

The OSI Model is a framework that explains how
network communication works.

It consists of 7 layers. Each layer performs
a different function when devices communicate.

## The 7 Layers

| Layer | Name | Main Function |
|---|---|---|
| 7 | Application | User-facing network services |
| 6 | Presentation | Data formatting and encryption |
| 5 | Session | Manages communication sessions |
| 4 | Transport | TCP and UDP communication |
| 3 | Network | IP addressing and routing |
| 2 | Data Link | Local network communication |
| 1 | Physical | Cables and electrical signals |

## Why is it important for SOC?

The OSI Model helps SOC analysts identify
which part of network communication may be
involved in an incident.

Examples:
- Layer 3: Suspicious IP traffic.
- Layer 4: Unusual port activity.
- Layer 7: Suspicious HTTP requests.

---

# 2. TCP/IP

## What is TCP/IP?

TCP/IP is the main protocol suite used for
communication across the internet.

Two important protocols:

**TCP (Transmission Control Protocol)**
- Provides reliable data delivery.
- Ensures data arrives in the correct order.
- Retransmits missing data.

**IP (Internet Protocol)**
- Provides IP addressing.
- Routes data between devices and networks.

**UDP (User Datagram Protocol)**
- Sends data without TCP's delivery guarantees.
- Prioritizes speed and low overhead.
- Commonly used for streaming and DNS queries.

## TCP Three-Way Handshake

TCP establishes a connection using three steps:

1. SYN: Client requests a connection.
2. SYN-ACK: Server acknowledges the request.
3. ACK: Client confirms the connection.

## Why is it important for SOC?

Understanding TCP helps analysts investigate
suspicious network connections.

Examples:
- Large numbers of incomplete SYN connections
  may indicate a SYN flood attack.
- Unusual TCP connections may indicate scanning.
- TCP flags help analysts understand connection
  behaviour.

---

# 3. Ports and Protocols

## What are Ports?

An IP address identifies a device.

A port identifies a specific service or
application running on that device.

Port numbers range from 0 to 65535.

A protocol defines the communication rules
used by devices or applications.

## Common Network Ports

| Port | Protocol | Purpose |
|---|---|---|
| 20/21 | FTP | File transfer |
| 22 | SSH | Secure remote access |
| 23 | Telnet | Unencrypted remote access |
| 25 | SMTP | Sending emails |
| 53 | DNS | Domain name resolution |
| 80 | HTTP | Web communication |
| 110 | POP3 | Retrieving emails |
| 143 | IMAP | Email access |
| 443 | HTTPS | Encrypted web communication |
| 445 | SMB | Windows file sharing |
| 3389 | RDP | Remote Desktop access |

## Why is it important for SOC?

SOC analysts investigate network traffic
using IP addresses, ports and protocols.

Examples:
- Port 3389: Investigate suspicious RDP access.
- Port 22: Investigate unusual SSH connections.
- Port 445: Investigate suspicious SMB activity.
- Port 23: Investigate insecure Telnet usage.

An unusual port connection does not
automatically mean an attack. It requires
further investigation.

---

# 4. DNS (Domain Name System)

## What is DNS?

DNS translates human-readable domain names
into IP addresses.

Example:

google.com → IP address

Computers use IP addresses to communicate
with other devices and servers.

## How DNS Works

1. User enters a domain name.
2. Computer checks its DNS cache.
3. DNS resolver looks for the answer if needed.
4. Resolver queries the DNS hierarchy.
5. Authoritative DNS server provides the answer.
6. Resolver returns the IP address.

## Common DNS Record Types

| Record | Purpose |
|---|---|
| A | Maps domain to IPv4 address |
| AAAA | Maps domain to IPv6 address |
| MX | Identifies email servers |
| CNAME | Creates a domain alias |
| TXT | Stores text information and verification data |

## Why is it important for SOC?

DNS logs can help analysts identify
suspicious domain lookups.

Examples:
- Connections to known malicious domains.
- Unusual randomly generated domains.
- Queries to newly registered domains.
- Repeated suspicious DNS requests.

Malware may use DNS to communicate with
Command and Control (C2) infrastructure.

---

# 5. HTTP and HTTPS

## What is HTTP?

HTTP (HyperText Transfer Protocol) is used
for communication between web browsers
and web servers.

**HTTPS** uses TLS encryption to protect
communication between clients and servers.

## HTTP vs HTTPS

| HTTP | HTTPS |
|---|---|
| Unencrypted communication | Encrypted communication |
| Usually port 80 | Usually port 443 |
| Data can be exposed in transit | TLS protects data in transit |

## Common HTTP Status Codes

| Code | Meaning |
|---|---|
| 200 | Request successful |
| 301 | Permanent redirect |
| 302 | Temporary redirect |
| 400 | Bad request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Resource not found |
| 500 | Internal server error |

## Why is it important for SOC?

HTTP logs help analysts investigate
web-related suspicious activities.

Examples:
- Repeated 401 responses may indicate
  attempted brute-force authentication.
- Unusual POST requests may require investigation.
- Suspicious user-agent strings may indicate
  automated tools or malicious activity.

Important: HTTPS encryption does not guarantee
that a website is legitimate. Phishing websites
can also use HTTPS certificates.

---

# 6. Firewalls and NAT

## What is a Firewall?

A firewall monitors and controls network
traffic based on configured security rules.

Rules can evaluate:
- Source IP address.
- Destination IP address.
- Port number.
- Network protocol.
- Allow or deny action.

## What is NAT?

NAT stands for Network Address Translation.

It allows multiple devices using private IP
addresses to share a public IP address when
communicating with external networks.

## Firewall vs NAT

| Firewall | NAT |
|---|---|
| Controls network traffic | Translates IP addresses |
| Allows or blocks traffic | Maps private and public addresses |
| Uses security rules | Maintains address translation information |

## Why is it important for SOC?

Firewall logs help analysts identify
suspicious network activities.

Examples:
- Repeated denied connections.
- Attempts to access restricted ports.
- Unusual outbound connections.
- Connections from suspicious external IPs.

NAT is also important because multiple
internal devices may share one public IP.

SOC analysts may need NAT/session logs
and timestamps to identify the correct
internal device involved in an alert.

---

# 7. Key Takeaways for SOC Analysts

Networking knowledge helps SOC analysts
understand and investigate network activity.

Important things to remember:

1. OSI Model helps identify where network
   communication problems occur.

2. TCP/IP explains how devices communicate
   and how data is delivered.

3. Ports and protocols identify which services
   are communicating.

4. DNS logs help identify suspicious
   domain lookups.

5. HTTP/HTTPS logs help investigate
   suspicious web activity.

6. Firewall logs help identify allowed
   and blocked network connections.

7. NAT logs help correlate public IP traffic
   with internal devices.

---

# 8. Practical Skills to Develop

My next practical exercises:

- [ ] Use nslookup to investigate DNS resolution.
- [ ] Use ipconfig to inspect network configuration.
- [ ] Use ping to test network connectivity.
- [ ] Use netstat to inspect network connections.
- [ ] Use Wireshark to capture network packets.
- [ ] Identify TCP three-way handshakes.
- [ ] Analyse DNS queries in Wireshark.
- [ ] Investigate firewall allow/deny logs.

---

# 9. Learning Reflection

What I learned:

Networking is the foundation of understanding
how computers communicate.

As an aspiring SOC analyst, I need to understand
network protocols, ports, DNS queries and
firewall logs to investigate suspicious activity.

My next goal is to gain hands-on experience
using networking tools and analysing
network traffic.
