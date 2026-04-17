# Nmap Reconnaissance Test

## Objective

Simulate attacker reconnaissance from Kali Linux against the Windows endpoint.

## Source

Kali Linux attacker machine

## Target

Windows 10 endpoint (`192.168.56.20`)

## Commands

```bash id="qk7z1n"
nmap -sS 192.168.56.20
nmap -Pn -p 135,139,445,3389 192.168.56.20
```

## Evidence

![Nmap Reconnaissance](screenshots/reconnaissance-nmap.png)
![Nmap Filtered Ports](screenshots/reconnaissance-nmap-filtered.png)

## Result

The Windows endpoint responded to reconnaissance activity, demonstrating attacker enumeration behavior in the lab environment.
