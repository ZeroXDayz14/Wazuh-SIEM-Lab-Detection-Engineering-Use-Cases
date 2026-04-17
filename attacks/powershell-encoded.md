# Encoded PowerShell Test

## Objective

Detect obfuscated PowerShell execution using an encoded command.

## Source

Windows 10 endpoint

## Command

```powershell id="r1k9zx"
powershell -enc VwByAGkAdABlAC0ASABvAHMAdAAgACIAVABlAHMAdAAiAA==
```

## Expected Detection

* Rule ID: 100502
* Description: Custom: Encoded PowerShell detected

## Evidence

![PowerShell Attack Command](screenshots/powershell-attack-command.png)
![Detection Alerts](screenshots/custom-detection-alerts.png)

## Result

Wazuh successfully detected encoded PowerShell execution using custom alert logic.
