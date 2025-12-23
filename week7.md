# Week 7 – Security Audit and System Evaluation

## Aim
## Introduction

## Step 1: System Security Audit (Lynis)

### Commands Used:
```bash
sudo lynis audit system
```

-Evidence:
A full system security audit was conducted using Lynis. The scan completed successfully and reported a Hardening Index score of 61. The output confirmed that multiple security controls are enabled, while also identifying areas for further hardening. A screenshot of the completed Lynis audit showing the hardening index and summary results was captured as evidence.

<img width="800" height="600" alt="week7_step1_lynis_audit" src="https://github.com/user-attachments/assets/9a1c9e49-d547-446a-8bf8-b7198c05da67" />


-Outcome:
The Lynis audit provided an overview of the system’s current security posture. The results indicate that the system has
a reasonable baseline level of security, but additional hardening opportunities exist to further reduce risk and improve compliance with security best practices.


-Reflection:
Using Lynis helped identify security strengths and weaknesses in a structured and automated way. This audit improves understanding of system hardening techniques and highlights the importance of continuous security assessment in maintaining a secure operating system.


## Step 2: Network Security Assessment (Nmap)

-Commands Used
```
sudo aa-status
```

-Evidence
Terminal output confirms that the AppArmor security module is loaded and active. Multiple application profiles are shown as enforced, demonstrating that mandatory access control policies are applied on the system. A screenshot was captured showing AppArmor running successfully.

<img width="800" height="600" alt="week7_step2_apparmor" src="https://github.com/user-attachments/assets/74019af5-2ddd-4cfa-b160-358cf1fcbc64" />


-Outcome
Access control mechanisms are enabled and functioning correctly. AppArmor is actively enforcing security profiles, helping to restrict application behaviour and reduce the potential impact of compromised processes.

-Reflection
Verifying AppArmor ensures that the system follows the principle of least privilege. Enforced access control profiles provide an additional security layer beyond traditional permissions, improving the overall security posture of the operating system.


## Step 3: Access Control Verification

-Commands Used:
```
sudo aa-status
sudo systemctl status ssh
```

-Evidence:

<img width="800" height="600" alt="week7_step3_access_control_ssh" src="https://github.com/user-attachments/assets/e07440ab-882a-4118-809c-16deee2267f7" />

-Outcome:
Access control mechanisms are correctly enforced on the system. AppArmor is active and restricting application behaviour, while SSH access is controlled through a running and monitored service.

-Reflection:
Verifying access control confirms that only authorised services and users can interact with the system. Enforced AppArmor profiles and a properly running SSH service reduce the attack surface and improve overall system security.

## Step 4: Service Audit and Justification

-Commands Used:
systemctl list-units --type=service --state=running

-Evidence:
The output lists all active system services currently running on the server. A screenshot was captured showing essential services such as SSH, networking, logging, and security-related services.


<img width="800" height="600" alt="week7_step4_running_services" src="https://github.com/user-attachments/assets/e6bfad1e-2e03-4d89-96ac-ab8a5ffb4459" />


-Outcome:
Only necessary services were found to be running on the system. Core services such as SSH are required for remote administration, while background services support networking, logging, and system stability. No unnecessary or unexpected services were identified.

-Reflection:
Auditing running services helps minimise the system attack surface by ensuring that only required services are enabled. Regular service reviews reduce security risks and support best-practice system hardening.

## Step 5: Overall Risk Assessment and Evaluation

The security audit and system evaluation identified that the Ubuntu server has a solid baseline security configuration. Core protections such as SSH access control, AppArmor enforcement, and limited running services reduce the system’s attack surface. The Lynis audit highlighted areas for improvement, indicating that while the system is reasonably hardened, additional configuration changes could further enhance security.

Potential risks include misconfiguration of services, weak authentication settings, or unpatched vulnerabilities if updates are not maintained. These risks can be mitigated through regular security audits, timely system updates, stricter access controls, and continuous monitoring. Overall, the system demonstrates a good balance between usability and security, with clear opportunities for future hardening and optimisation.
