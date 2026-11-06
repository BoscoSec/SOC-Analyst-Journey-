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
