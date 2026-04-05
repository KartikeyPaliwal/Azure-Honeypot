# Azure Honeypot with Microsoft Sentinel Attack Monitoring

## Project Overview
This project demonstrates deployment of a cloud-based honeypot in Microsoft Azure for monitoring unauthorized access attempts, collecting security logs, enriching attacker IP data, and visualizing attack origins through Microsoft Sentinel.

## Architecture
Internet → Azure VM → Windows Security Logs → Log Analytics Workspace → Microsoft Sentinel → GeoIP Enrichment → Attack Map

## Technologies Used
- Microsoft Azure
- Virtual Machine (Windows)
- Virtual Network (VNet)
- Network Security Group (NSG)
- Log Analytics Workspace
- Microsoft Sentinel
- Kusto Query Language (KQL)

## Project Steps

### 1. Azure Infrastructure Setup
- Created Azure subscription
- Created Resource Group
- Deployed Windows Virtual Machine
- Configured Virtual Network

### 2. Honeypot Exposure
- Allowed inbound traffic using NSG rule
- Disabled Windows Firewall for observation
- Exposed VM to internet traffic

### 3. Security Log Collection
- Generated failed login attempts
- Observed Event ID 4625 in Event Viewer

### 4. Sentinel Integration
- Created Log Analytics Workspace
- Connected Microsoft Sentinel
- Enabled Windows Security Events via AMA connector

### 5. Log Analysis using KQL
Used KQL query:

SecurityEvent
| where EventID == 4625

### 6. GeoIP Enrichment
Imported geoip watchlist and enriched attacker IP data.

### 7. Attack Map Visualization
Created Sentinel workbook to visualize attack source locations globally.

## Key Findings
- Multiple failed login attempts detected
- Event ID 4625 captured unauthorized login attempts
- Geographic attacker data successfully enriched

## Skills Demonstrated
- Cloud Security Monitoring
- SIEM Configuration
- Threat Detection
- KQL Querying
- Security Log Analysis

## Future Improvements
- Add automated alert rules
- Create incident playbooks
- Integrate threat intelligence feeds
  
## Screenshots

![System Architecture](screenshots/Honeypot__architecture.png)
