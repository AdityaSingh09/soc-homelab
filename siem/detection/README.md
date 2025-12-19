# Detection Engineering

## Detection Philosophy
Detections are designed to:
- Be explainable
- Map to real attack techniques
- Minimise false positives
- Support learning and practice

## Detection Categories
- Authentication abuse
- Privilege escalation
- Suspicious process execution
- Malware indicators
- Network reconnaissance

## Rule Structure
Each detection rule includes:
- Description
- Trigger condition
- Severity level
- MITRE ATT&CK technique mapping
- Related attack simulation scenario

## Example Mapping
| Scenario | Detection | MITRE ATT&CK |
|--------|-----------|--------------|
| SSH brute force | Multiple failed logins | T1110 |
| Suspicious PowerShell | Encoded commands | T1059 |
| New admin user | Privilege escalation | T1078 |

## Testing Method
- Execute attack from Kali
- Confirm alert generation
- Capture evidence
- Tune thresholds if needed
- Document outcome in incident report
