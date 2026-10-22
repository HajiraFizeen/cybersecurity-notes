# Cybersecurity Tools Notes

## 1. Nmap

**Purpose:** Network discovery and port scanning.

**Common uses:**
- Discover hosts in an authorized network.
- Identify open ports.
- Detect services and versions.

**Commands:**
```bash
nmap 10.82.145.93
nmap -p 22,80,443 10.82.145.93
nmap -sV 10.82.145.93
nmap -oN scan.txt 10.82.145.93
```

**Defensive use:** Identify unexpected exposed services and verify firewall changes.

## 2. Burp Suite

**Purpose:** Inspect and test web application traffic.

**Main components:**
- Proxy: intercepts and inspects HTTP/S traffic.
- Repeater: manually modifies and resends requests.
- Intruder: automates customized request testing.
- Decoder: transforms data between supported encodings.
- Scanner: identifies potential vulnerabilities in supported editions.

**Basic workflow:**
1. Open a permitted test application.
2. Configure the browser to use Burp's proxy.
3. Inspect requests and responses.
4. Send an interesting request to Repeater.
5. Test a vulnerability in the authorized lab.
6. Save sanitized evidence.

**Defensive use:** Reproduce web vulnerabilities and verify fixes.

## 3. Wireshark

**Purpose:** Capture and analyze network packets.

**Common uses:**
- Troubleshoot connectivity.
- Investigate suspicious network activity.
- Inspect DNS and TCP communication.
- Analyze protocol behavior.

**Useful display filters:**
```text
dns
http
tcp
tcp.flags.syn == 1
ip.addr == 192.168.1.10
```

These are display filters used to narrow captured traffic, not commands for sending packets.

**Basic workflow:**
1. Select an authorized network interface or capture file.
2. Start or open a capture.
3. Apply a display filter.
4. Inspect packet details and protocol fields.
5. Document relevant observations.

**Defensive use:** Investigate network anomalies and troubleshoot protocol issues.

## 4. Metasploit Framework

**Purpose:** A framework for authorized security testing and exploit validation.

**Important terms:**
- Module: a component that performs a specific task.
- Exploit: code that attempts to use a vulnerability.
- Payload: code executed as part of an exploit workflow.
- Auxiliary module: supporting tasks such as scanning or service checks.
- Session: an interactive connection established by a successful module, when applicable.

**Basic console commands:**
```text
msfconsole
help
search <keyword>
info <module_name>
```

Only use exploit modules against systems you own or have explicit permission to test.

**Defensive use:** Validate exposure in a controlled environment and confirm that patches or configuration changes address a weakness.

## Tool Comparison

| Tool | Main purpose | Typical use |
|---|---|---|
| Nmap | Network scanning | Identify services |
| Burp Suite | Web testing | Inspect HTTP requests |
| Wireshark | Packet analysis | Investigate network traffic |
| Metasploit | Security validation | Test known vulnerabilities |

## Safe Testing Rules
- Use authorized labs and targets.
- Keep tool versions updated.
- Avoid disrupting production systems.
- Remove credentials and sensitive information from screenshots.
- Document findings and remediation.

## Official Resources
- Nmap: https://nmap.org/book/man.html
- Burp Suite: https://portswigger.net/burp/documentation
- Wireshark: https://www.wireshark.org/docs/
- Metasploit: https://docs.metasploit.com/
