# SSH Brute Force + Active Response

## Objective

Simulate a brute-force SSH attack from Kali Linux and validate automated blocking with Wazuh Active Response.

## Source

Kali Linux attacker machine

## Target

Ubuntu Wazuh manager (`192.168.56.10`)

## Attack Command

```bash id="a8m2kf"
hydra -l root -P ~/test.txt -t 4 ssh://192.168.56.10
```

## Detection

Wazuh triggered:

* Rule ID: 5551
* Description: PAM: Multiple failed logins in a small period of time

## Active Response

The `firewall-drop` command was used to automatically block the attacking IP.

## Evidence

![Kali Attack Source](screenshots/kali-attack-source.png)
![SSH Auth Log Evidence](screenshots/ssh-auth-log-evidence.png)
![SSH Brute Force Alert](screenshots/ssh-bruteforce-alert.png)
![Active Response Triggered](screenshots/active-response-triggered.png)
![Active Response JSON](screenshots/active-response-json.png)
![Firewall Blocked IP](screenshots/firewall-blocked-ip.png)

## Result

Wazuh detected repeated failed SSH authentication attempts and automatically blocked the attacker IP (192.168.56.40) using Active Response.
