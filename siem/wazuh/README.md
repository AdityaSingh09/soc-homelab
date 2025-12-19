# Wazuh Platform Design

## Architecture
- Wazuh Manager running on Ubuntu Server
- Wazuh agents installed on Windows and Linux endpoints
- Centralised alerting and log storage

## Planned Components
- Wazuh Manager
- Wazuh Agents (Windows, Linux)
- Web dashboard (for analyst access)

## Agent Responsibilities
- Collect authentication events
- Monitor file integrity
- Track process execution
- Forward security telemetry to the manager

## Security Considerations
- Agents communicate only with the SIEM server
- No external log forwarding
- Credentials and keys are not stored in this repository

## Future Enhancements
- Custom rules
- Active response (controlled)
- Alert severity tuning
