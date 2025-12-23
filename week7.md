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

### Commands Used
### Evidence
### Outcome
### Reflection

## Step 5: Overall Risk Assessment and Evaluation
