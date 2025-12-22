Performance Testing Plan:
For performance and remote monitoring, I will use command-line monitoring tools such as top, htop, df -h, free -h,
and uptime to observe CPU usage, memory consumption, disk utilisation, and system load while the server is running.
Testing will be carried out during normal operation and while performing administrative tasks over SSH to assess system responsiveness
and stability. Network performance will be observed using basic connectivity checks and interface statistics to ensure reliable remote access.

Security Configuration Checklist:
SSH access is secured by disabling root login, enforcing strong passwords, and limiting access to authorised users only.
The firewall (UFW) is configured to allow SSH traffic while blocking all unnecessary ports. Mandatory access control is 
enabled using AppArmor to restrict application permissions. Automatic security updates are enabled to ensure the system remains protected
against known vulnerabilities.User privilege management follows the principle of least privilege, using sudo for administrative tasks.
Network security is maintained by isolating the virtual machine and monitoring active connections.

Threat Model and Mitigation:
One identified threat is unauthorised SSH access, which is mitigated through SSH hardening and firewall rules. 
Another threat is privilege escalation, reduced by strict user permissions and controlled sudo access. A further threat 
is outdated software vulnerabilities, mitigated by enabling automatic updates and regular system patching.
