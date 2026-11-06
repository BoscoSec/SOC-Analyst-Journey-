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
