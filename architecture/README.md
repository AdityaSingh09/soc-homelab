# Architecture

## Goal
Build a virtual enterprise-style SOC lab that supports:
- Centralised logging and monitoring (SIEM)
- Safe attack simulation (red team actions in a closed lab)
- Incident response workflows and evidence collection
- ISO/IEC 27001-aligned documentation

## Components
- **Host:** Personal homelab PC (virtualisation host)
- **Hypervisor:** Proxmox VE
- **SOC / SIEM:** Ubuntu Server running Wazuh
- **Endpoint (Windows):** Windows 10 VM (telemetry + alerts)
- **Server (Linux):** Ubuntu Server VM (SSH/services target)
- **Attacker:** Kali Linux VM (simulated attacks)

## High-level network model
This lab uses an isolated virtual network (no internet-facing services).
- All VMs communicate only inside the lab subnet
- Management access is via the host machine (web UI/SSH)
- Logs flow from endpoints/servers into the SIEM

## Log & alert flow
1. Windows + Linux send security telemetry to **Wazuh Manager**
2. Wazuh generates alerts and stores searchable events
3. Dashboards are used for triage and investigation
4. Evidence is captured (screenshots + sanitized logs) and linked to IR reports

## Data flows (summary)
- **Telemetry:** Endpoint/Server → SIEM
- **Attacks:** Attacker → Endpoint/Server
- **Response:** Analyst (you) → SIEM dashboards → IR report

## Diagrams
Planned diagrams (stored in `architecture/diagrams/`):
- SOC architecture overview
- Network segmentation (optional)
- Logging pipeline

## Sanitization rules (public repo)
- Use example IP ranges only (e.g., 10.10.10.0/24)
- Avoid real hostnames/usernames
- Never publish secrets, keys, tokens, or full raw logs
