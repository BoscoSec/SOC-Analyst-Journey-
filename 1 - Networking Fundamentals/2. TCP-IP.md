# TCP/IP

## What is TCP/IP ?

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





