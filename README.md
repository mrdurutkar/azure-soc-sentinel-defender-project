# Azure SOC Lab — Microsoft Sentinel + Defender for Endpoint

## Overview

This project demonstrates an enterprise-style Security Operations Center (SOC) lab built in Microsoft Azure. The lab integrates **Microsoft Defender for Endpoint (EDR)** with **Microsoft Sentinel (SIEM)** to simulate real-world threat detection, investigation, and automated incident response.

The objective of this project is to design and validate an lightweight cloud SOC architecture that ingests endpoint security alerts, correlates incidents, and automates response workflows using **KQL** and **Azure Logic Apps**.

---

## Architecture

**Data flow:**

Windows Endpoint (Azure VM)
→ Microsoft Defender for Endpoint (EDR)
→ Log Analytics Workspace
→ Microsoft Sentinel (SIEM)
→ Automated Incident Response (Logic Apps)

This architecture mirrors modern enterprise SOC environments where endpoint telemetry feeds into centralized SIEM platforms for detection and response.

---

## Key Features

* Windows endpoint onboarding into Microsoft Defender for Endpoint
* Integration of Defender alerts into Microsoft Sentinel
* Custom **KQL detection queries** for threat hunting
* Automated incident response using **Azure Logic Apps**
* Validation of malware detection using safe attack simulations
* Incident investigation and SOC workflow analysis

---

## Technologies Used

* Microsoft Azure
* Microsoft Sentinel (SIEM)
* Microsoft Defender for Endpoint (EDR)
* Azure Logic Apps (SOAR automation)
* Kusto Query Language (KQL)
* Windows 10 Enterprise endpoint

---

## Implementation Summary

### 1. Environment Setup

* Created Azure Log Analytics workspace
* Enabled Microsoft Sentinel
* Deployed Windows endpoint VM
* Onboarded VM into Defender for Endpoint

### 2. SIEM Integration

* Connected Microsoft Defender for Endpoint data connector in Sentinel
* Verified alert ingestion into Sentinel logs
* Configured incident creation rules

### 3. Detection Engineering

* Developed custom KQL queries to detect suspicious endpoint behavior
* Implemented scheduled analytics rules
* Performed threat hunting exercises

### 4. Automation

* Built Logic App playbooks triggered by Sentinel incidents
* Automated alert notification and response actions

---

## Validation & Testing

To validate the SOC pipeline:

* Executed safe malware simulation using the EICAR test file
* Generated Defender alerts
* Confirmed ingestion into Sentinel
* Investigated incidents through SOC dashboards

Screenshots and evidence are available in the `/screenshots` directory.

---

## Skills Demonstrated

* Cloud SOC architecture design
* SIEM/EDR integration
* Detection engineering with KQL
* Incident response automation
* Endpoint security management
* Azure identity and RBAC configuration
* Security monitoring and investigation workflows

---

## Project Structure

```
azure-soc-sentinel-defender-lab/
├── README.md
├── architecture/
├── setup/
├── detections/
├── screenshots/
└── lessons-learned.md
```

---

## Lessons Learned

* Tenant alignment is critical for Defender–Sentinel integration
* RBAC roles affect data connector access
* Sentinel ingests Defender alerts, not raw telemetry
* Proper automation improves incident response efficiency

---

## Future Improvements

* Multi-cloud log ingestion (AWS/GCP)
* Advanced threat hunting scenarios
* Extended SOAR automation workflows
* Custom SOC dashboards and reporting

---

## Author

**MrDurutkar**
Cloud Security & Infrastructure Portfolio

---

## Disclaimer

This lab environment is built for educational and portfolio purposes. All attack simulations used safe testing methods and did not involve real malware.
