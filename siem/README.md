# SIEM Design

## Purpose
The SIEM is the central component of the SOC homelab. Its purpose is to:
- Collect security telemetry from endpoints and servers
- Detect suspicious or malicious activity
- Generate alerts for investigation
- Support incident response and reporting

## SIEM Platform
**Wazuh** is used as the SIEM and endpoint detection platform.

### Why Wazuh
- Open-source and enterprise-aligned
- Supports Linux and Windows endpoints
- Built-in file integrity monitoring (FIM)
- Authentication and process monitoring
- MITRE ATT&CK mapping
- Active community and documentation

## Monitored Assets
- Windows 10 Endpoint
- Ubuntu Linux Server
- Wazuh Manager (self-monitoring)

## Log Collection Overview
| Source | Log Types |
|------|----------|
| Windows Endpoint | Authentication, process creation, PowerShell activity |
| Linux Server | SSH authentication, sudo usage, system logs |
| SIEM Server | Manager health, agent status |

## Detection Approach
- Baseline normal behaviour
- Detect deviations (failed logins, new users, privilege escalation)
- Correlate events across systems
- Escalate alerts into incidents

## Output
- Alerts visible in dashboards
- Evidence used in incident response reports
- Metrics to support ISO/IEC 27001 controls
