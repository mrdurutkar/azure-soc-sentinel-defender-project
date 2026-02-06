# Architecture — Azure SOC Lab

## Overview

This lab implements a lightweight enterprise-style Security Operations Center (SOC) architecture in Microsoft Azure. The design integrates endpoint detection and response (EDR) with a centralized SIEM platform for monitoring and automated incident response.

## Architecture Diagram (Conceptual)

```
Windows Endpoint VM
        │
        ▼
Microsoft Defender for Endpoint (EDR)
        │
        ▼
Log Analytics Workspace
        │
        ▼
Microsoft Sentinel (SIEM)
        │
        ├── KQL Detection Rules
        └── Logic App Automation (SOAR)
```

## Components

### Windows Endpoint (Azure VM)

A Windows 10 Enterprise VM acts as the monitored endpoint. It generates telemetry and security alerts through Defender for Endpoint.

### Microsoft Defender for Endpoint (EDR)

Provides endpoint threat detection, automated investigation, and remediation capabilities.

### Log Analytics Workspace

Serves as the data ingestion layer between Defender and Sentinel.

### Microsoft Sentinel (SIEM)

Centralized security monitoring platform used for:

* Alert correlation
* Incident creation
* Threat hunting
* Dashboard visualization

### Azure Logic Apps (SOAR)

Automates incident response workflows triggered by Sentinel alerts.

## Security Flow

1. Endpoint activity triggers Defender detection
2. Defender generates an security alert
3. Alert is ingested into Sentinel
4. Sentinel creates an incident
5. Logic App automation executes response actions
6. SOC analyst investigates and closes incident

## Design Principles

* Least privilege access control
* Centralized monitoring
* Automated response
* Repeatable lab deployment
