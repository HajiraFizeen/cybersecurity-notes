# SOC Analyst Notes

## 1. What is a SOC?
A Security Operations Center (SOC) monitors systems and networks to detect, investigate, and respond to security threats.

## 2. What is a log?
A log is a record of an event that occurred on a system, application, or network device.

**Examples:**
- Successful and failed logins
- Process execution
- Firewall traffic
- DNS requests
- File changes
- Endpoint security alerts

## 3. What is a SIEM?
Security Information and Event Management (SIEM) technology collects and analyzes security events from multiple sources.

**Common functions:**
- Centralized log collection
- Event correlation
- Alert generation
- Dashboards and investigations
- Reporting and compliance support

Examples of SIEM products include Microsoft Sentinel, Splunk Enterprise Security, and IBM QRadar.

## 4. What is a security alert?
An alert is a notification that activity may require investigation.

Examples:
- Repeated failed logins
- Login from an unusual location
- Suspicious process execution
- Unexpected outbound network traffic
- Malware detection

An alert does not automatically mean an attack occurred. Analysts must validate the evidence.

## 5. Incident Response

A practical incident-response workflow:

1. Preparation: establish tools, procedures, and access.
2. Detection and analysis: validate alerts and determine scope.
3. Containment: limit further damage.
4. Eradication: remove the cause of the incident.
5. Recovery: restore systems safely.
6. Lessons learned: document the incident and improve controls.

Follow the organization's approved incident-response process.

## 6. Basic Log Investigation

When reviewing a suspicious event, ask:

- What happened?
- When did it happen?
- Which user or host was involved?
- What source and destination IP addresses were recorded?
- Which process or service was involved?
- Is the activity expected?
- What additional evidence is available?
- Does the event require escalation?

## 7. Example Investigation

**Scenario:** Several failed login attempts are followed by a successful login.

**Investigation:**
1. Check timestamps and affected accounts.
2. Compare source IP addresses.
3. Look for successful logins after the failures.
4. Review other activity by the same account.
5. Determine whether the login was authorized.
6. Escalate or contain according to policy.

**Possible explanations:** A forgotten password, a misconfigured application, or a password-guessing attempt. Additional evidence is needed to distinguish them.

## 8. Incident Report Template

- Incident ID:
- Date and time:
- Alert source:
- Affected host or account:
- Summary:
- Evidence:
- Investigation steps:
- Impact:
- Actions taken:
- Escalation:
- Recommended improvements:

## Learning Resources
- MITRE ATT&CK: https://attack.mitre.org/
- Microsoft security documentation: https://learn.microsoft.com/security/
- Splunk training: https://www.splunk.com/en_us/training.html

## Key Takeaway
A SOC analyst uses evidence to distinguish normal activity from suspicious behavior, documents findings, and follows incident-response procedures.
