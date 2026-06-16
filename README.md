# wazuh-lkrg

![Wazuh](https://img.shields.io/badge/wazuh-4.x-005571)
![Type](https://img.shields.io/badge/type-decoders%20%26%20rules-blue)
![License](https://img.shields.io/badge/license-MIT-green)

Custom Wazuh decoders and rules for [LKRG (Linux Kernel Runtime Guard)](https://lkrg.org/) — surface kernel integrity violations, privilege escalation attempts, and exploit detection events directly in your SIEM.

## What is LKRG

LKRG is a loadable kernel module that detects runtime integrity violations and exploitation attempts at the kernel level. It monitors:

- kernel code/data integrity
- process credential changes (privilege escalation)
- SELinux/AppArmor enforcement bypass attempts
- exploit technique detection (ROP, JOP, ret2usr, etc.)

It runs on mainline and distro kernels from RHEL7 onwards without kernel patching.

## Install

```bash
# Copy decoders
cp lkrg_decoders.xml /var/ossec/etc/decoders/

# Copy rules
cp lkrg_rules.xml /var/ossec/etc/rules/

# Reload rules without restart
wazuh-reload-rules
# or
systemctl restart wazuh-manager
```

## What gets detected

| LKRG event | Wazuh rule | Description |
|---|---|---|
| `LKRG: ALERT` | lkrg_alert | Kernel integrity violation |
| `LKRG: EXPLOIT` | lkrg_exploit | Exploitation attempt blocked |
| `LKRG: TASK` | lkrg_task | Process credential tampering |
| `LKRG: INIT` | lkrg_init | LKRG module load/unload |

## Credits

- Adam 'pi3' Zabrocki — LKRG author ([pi3.com.pl](http://pi3.com.pl))
- [LKRG project](https://lkrg.org/)
