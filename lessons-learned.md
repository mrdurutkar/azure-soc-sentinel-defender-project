# Lessons Learned

## Identity & Tenant Architecture

Tenant alignment is critical. Defender and Sentinel must exist within the same Entra tenant for seamless integration.

## RBAC Permissions

Proper Azure RBAC roles are required to configure Sentinel connectors and automation.

## Alert Ingestion Behavior

Sentinel ingests Defender alerts, not raw endpoint telemetry. Testing requires generating actual alerts.

## Automation Value

Logic Apps significantly improve SOC response efficiency by automating repetitive actions.

## Practical SOC Insights

This lab demonstrates how modern SOC environments combine EDR and SIEM for centralized detection and response.
