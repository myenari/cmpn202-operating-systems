# Week 2 – Security Planning and Testing Methodology

## Performance Testing Plan

For performance and remote monitoring, command-line tools will be used to observe system behaviour while the Ubuntu Server is running. CPU usage, memory consumption, disk utilisation, and system uptime will be monitored using tools such as top, free -h, df -h, and uptime. Testing will be carried out during normal administrative tasks performed over SSH to assess responsiveness, stability, and overall system performance. This approach ensures the server remains reliable while being managed remotely.

## Security Configuration Checklist

- SSH access is secured by disabling root login and enforcing strong password authentication.
- The firewall (UFW) is configured to allow only SSH traffic while blocking all other incoming connections.
- Mandatory access controls are enforced using AppArmor to restrict application permissions.
- Automatic security updates are enabled to ensure vulnerabilities are patched promptly.
- User privilege management follows the principle of least privilege, with administrative tasks performed using sudo.
- Network security is maintained by isolating the virtual machine and monitoring active connections.

## Threat Model

One identified threat is unauthorised SSH access, which is mitigated through SSH hardening, firewall rules, and restricted user privileges. Another threat is privilege escalation, reduced by enforcing sudo access controls and mandatory access policies. A further threat is unpatched vulnerabilities, which is mitigated by enabling automatic system updates and regular patching to maintain system security.

