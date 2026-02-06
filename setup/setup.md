# Deployment Guide — Azure SOC Lab

## Prerequisites

* Azure subscription
* Microsoft Defender for Endpoint tenant
* Global administrator access

## Step 1 — Create Log Analytics Workspace

1. Azure Portal → Create resource
2. Select Log Analytics Workspace
3. Create workspace for Sentinel

## Step 2 — Enable Microsoft Sentinel

1. Open Microsoft Sentinel
2. Select created workspace
3. Enable Sentinel

## Step 3 — Deploy Windows Endpoint VM

1. Create Windows 10 Enterprise VM
2. Enable RDP access (restricted IP)
3. Use small VM size for cost efficiency

## Step 4 — Onboard VM into Defender

1. Download onboarding script from Defender portal
2. Run script as Administrator on VM
3. Verify device appears in Defender portal

## Step 5 — Connect Defender to Sentinel

1. Sentinel → Data connectors
2. Enable Microsoft Defender for Endpoint connector
3. Confirm data ingestion

## Step 6 — Validate Pipeline

1. Trigger EICAR test file
2. Confirm Defender alert
3. Verify Sentinel incident

## Step 7 — Configure Automation

1. Create Logic App playbook
2. Trigger on Sentinel incident
3. Add notification or tagging actions
