# Detection Engineering — KQL Queries

This section contains custom KQL queries used for threat detection and hunting.

## Suspicious PowerShell Activity

```
DeviceProcessEvents
| where FileName == "powershell.exe"
| where ProcessCommandLine has_any ("EncodedCommand","DownloadString","Invoke-WebRequest")
| project TimeGenerated, DeviceName, ProcessCommandLine
```

## Malware Alerts from Defender

```
SecurityAlert
| where ProviderName contains "Defender"
| sort by TimeGenerated desc
```

## Unusual Process Execution

```
DeviceProcessEvents
| summarize count() by FileName
| order by count_ desc
```

## Recent Endpoint Events

```
DeviceEvents
| sort by Timestamp desc
| take 50
```

## Threat Hunting Example

```
DeviceNetworkEvents
| where RemotePort == 4444
| project Timestamp, DeviceName, RemoteIP
```

## Analytics Rule Usage

These queries were converted into Sentinel scheduled analytics rules to automatically generate incidents when suspicious behavior is detected.
