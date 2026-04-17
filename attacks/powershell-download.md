# PowerShell Download Test

## Objective

Detect suspicious download behavior using PowerShell and a Kali-hosted web server.

## Source

Windows 10 endpoint

## Supporting Infrastructure

Kali Linux hosted a benign file using a Python HTTP server.

## Kali Command

```bash
mkdir -p ~/wazuh-lab-files
cd ~/wazuh-lab-files
echo "This is a benign lab file for Wazuh testing." > test.txt
python3 -m http.server 80
```

## Windows Command

```powershell
powershell -Command "Invoke-WebRequest http://192.168.56.40/test.txt"
```

## Expected Detection

* Rule ID: 100501
* Description: Custom: PowerShell download detected

## Evidence

![Kali Attack Source](screenshots/kali-attack-source.png)
![PowerShell Attack Command](screenshots/powershell-attack-command.png)
![Command Line Evidence](screenshots/powershell-commandline-evidence.png)
![Detection Alerts](screenshots/custom-detection-alerts.png)

## Result

Wazuh successfully detected suspicious PowerShell download activity from the Windows endpoint.

