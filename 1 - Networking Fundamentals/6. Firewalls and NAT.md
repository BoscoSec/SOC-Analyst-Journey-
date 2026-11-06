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

