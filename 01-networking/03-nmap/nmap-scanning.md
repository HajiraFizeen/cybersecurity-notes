# Nmap Scanning Notes

## 1. What is Nmap?
Nmap (Network Mapper) is a tool used to discover hosts and examine network services and ports.

## 2. Basic commands

### Check Nmap version
```bash
nmap --version
```

### Scan an authorized lab target
```bash
nmap <TARGET_IP>
```

### Scan selected ports
```bash
nmap -p 22,80,443 <TARGET_IP>
```

### Detect service versions
```bash
nmap -sV <TARGET_IP>
```

### Detect common TCP ports
```bash
nmap -sS <TARGET_IP>
```

### Save scan results
```bash
nmap -oN scan-results.txt <TARGET_IP>
```

Replace `<TARGET_IP>` with the IP address of your own lab or an explicitly authorized target.

## 3. Common port states
- Open: an application is accepting connections on the port.
- Closed: the host is reachable, but no application is listening on that port.
- Filtered: Nmap cannot determine whether the port is open because packet filtering or another network condition prevents a clear result.

## 4. What is service detection?
Service detection attempts to identify the application and version running on an accessible port.

Example:
```bash
nmap -sV <TARGET_IP>
```

## 5. How security teams use Nmap
- Discover hosts in authorized networks.
- Identify exposed ports and services.
- Check for unexpected network services.
- Support vulnerability assessment and asset inventory.

## 6. Defensive recommendations
- Disable unnecessary services.
- Restrict exposed ports with firewall rules.
- Keep services updated.
- Re-scan authorized assets after remediation.

## 7. Lab report template
- Lab name:
- Date:
- Objective:
- Authorized target:
- Commands used:
- Important findings:
- Security impact:
- Recommended mitigation:
- Evidence/screenshots:
- What I learned:

## Safety
Only scan systems you own or have explicit permission to test.
