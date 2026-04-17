# PowerShell Execution Test

## Source

Windows 10 endpoint

## Command

```powershell
powershell -Command "Write-Host test"
```

## Evidence

![PowerShell Command](../screenshots/powershell-attack-command.png)
![Detection Alerts](../screenshots/custom-detection-alerts.png)

## Result

Wazuh successfully detected PowerShell process execution using Sysmon logs and the custom rule.

