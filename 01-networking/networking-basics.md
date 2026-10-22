# Networking Fundamentals

## 1. What is a network?
A network is a group of connected devices that communicate and share information.

Examples: computers connected to Wi-Fi, office networks, and the internet.

## 2. What is an IP address?
An IP address identifies a device's network interface so that data can be routed to the correct destination.

Examples:
- IPv4: `192.168.1.10`
- IPv6: `2001:db8::1` (documentation example)

## 3. What is a port?
A port is a logical endpoint used by network services and applications.

Common ports:
- 21 — FTP
- 22 — SSH
- 25 — SMTP
- 53 — DNS
- 80 — HTTP
- 443 — HTTPS
- 445 — SMB

## 4. What is TCP?
TCP is a transport protocol that provides reliable, ordered delivery of data.

TCP three-way handshake:
1. SYN — client requests a connection.
2. SYN-ACK — server acknowledges and responds.
3. ACK — client acknowledges the response.

## 5. What is UDP?
UDP is a connectionless transport protocol with lower overhead than TCP. It does not guarantee delivery or ordering.

Examples of uses include DNS queries, voice calls, and streaming.

## 6. What is DNS?
DNS translates domain names into information such as IP addresses.

Example: resolving `example.com` to an IP address.

## 7. HTTP vs HTTPS
- HTTP commonly uses port 80.
- HTTPS commonly uses port 443 and protects HTTP traffic using TLS.

## 8. What is a firewall?
A firewall applies traffic rules to allow or block network connections.

## 9. What is a vulnerability?
A vulnerability is a weakness that could be exploited to affect the confidentiality, integrity, or availability of a system.

## 10. Why networking matters in cybersecurity
Networking knowledge helps security analysts investigate suspicious traffic, understand scan results, identify exposed services, and troubleshoot connectivity.

## Key takeaway
An IP address helps identify a network destination, while a port helps identify the service endpoint. Neither alone guarantees that a service is accessible.
