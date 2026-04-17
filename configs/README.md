# Configurations

This folder contains configuration files used in the Wazuh SOC lab.

## Files

### `windows-ossec.conf`
Wazuh agent configuration for the Windows endpoint.

Purpose:
- Configure agent connectivity to the Wazuh manager
- Define Windows log collection
- Support Sysmon event forwarding into Wazuh

### `sysmonconfig-export.xml`
Sysmon configuration used on the Windows endpoint.

Purpose:
- Capture process creation events
- Capture network connection events
- Capture DNS query activity
- Improve endpoint visibility for PowerShell and related behaviors

## How these configs fit into the lab

- `windows-ossec.conf` forwards Windows telemetry from the endpoint to Wazuh
- `sysmonconfig-export.xml` increases visibility into endpoint activity
- Together, they support the PowerShell detection use cases documented in `/attacks`

## Notes

These configs were used in a controlled home lab environment for detection engineering and SOC workflow practice.
