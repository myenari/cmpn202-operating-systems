# Week 5 – Advanced Security and Monitoring Infrastructure

## Aim
The aim of this week is to implement advanced security mechanisms and monitoring capabilities on the Ubuntu server. This includes enforcing access control, enabling automatic security updates, detecting intrusion attempts, verifying security baselines, and monitoring system performance remotely.


## Introduction
In this week, additional security and monitoring features were configured to strengthen the server beyond basic SSH access. Tools such as AppArmor, unattended security updates, and Fail2Ban were used to enhance system protection, while custom scripts were created to verify the security baseline and monitor system performance. These measures help ensure the server remains secure, stable, and observable during operation.


## Step 1: Access Control (AppArmor)

-Commands Used
```bash
sudo aa-status
```

-Evidence
Terminal output confirmed that the AppArmor security module is loaded and active, with multiple profiles enforced. A screenshot was captured showing AppArmor running successfully on the Ubuntu server.

<img width="800" height="600" alt="week5_step1_unattended_upgrades" src="https://github.com/user-attachments/assets/dbe12aa0-729f-4fd7-b9bb-ed2afcf9eda0" />

-Outcome
AppArmor access control is enabled and operational on the system. This confirms that mandatory access control policies are actively restricting application behaviour to improve system security.

-Reflection
Using AppArmor provides an additional layer of security by limiting what applications can access, even if they are compromised. Verifying that AppArmor is active ensures the system follows the principle of least privilege and is better protected against misuse or attacks.

## Step 2: Automatic Security Updates

- Commands Used
```bash
sudo systemctl status unattended-upgrades
sudo systemctl enable unattended-upgrades
```

- Evidence
The terminal output shows that the unattended-upgrades service is enabled and running. A screenshot was captured displaying the service status with active (running).

<img width="800" height="600" alt="week5_step2_unattended_upgrades" src="https://github.com/user-attachments/assets/65b58522-b232-4898-9226-fd87021a58a1" />


- Outcome
Automatic security updates are successfully enabled on the Ubuntu server. This ensures that important security patches are installed automatically without requiring manual intervention.

- Reflection
Enabling unattended upgrades improves system security by reducing the risk of unpatched vulnerabilities. This approach is particularly important for servers, as it helps maintain a secure and stable system over time with minimal administrative effort.

## Step 3: Intrusion Detection (Fail2Ban)

- Commands Used
```bash
sudo apt install fail2ban -y
sudo systemctl start fail2ban
sudo systemctl enable fail2ban
sudo systemctl status fail2ban
```

- Evidence
Terminal output shows that the Fail2Ban service is active and running on the Ubuntu server. A screenshot was captured displaying the service status with `Active: active (running)`.

<img width="800" height="600" alt="week5_step3_fail2ban_active" src="https://github.com/user-attachments/assets/5bc40e47-035f-4aab-bbae-bf30ab5ed623" />

- Outcome
Fail2Ban was successfully installed and configured on the Ubuntu server. The service is active and running, providing automated protection against brute-force attacks by monitoring login attempts and blocking malicious IP addresses.

- Reflection
Implementing Fail2Ban highlights the importance of proactive security measures on servers. By automatically detecting and blocking repeated failed login attempts, Fail2Ban significantly reduces the risk of brute-force attacks and strengthens overall system security with minimal administrative effort.

## Step 4: Security Baseline Verification Script

- Commands Used
```bash
chmod +x security_baseline.sh
./security_baseline.sh
```

- Evidence
The terminal output shows the execution of the security baseline verification script.
The script confirms that:

SSH service is active and running

UFW firewall is enabled and active

Fail2Ban service is active and running

A screenshot was captured showing the successful execution of the script and the current security status of the server.

<img width="800" height="600" alt="week5_step4_security_-baseline" src="https://github.com/user-attachments/assets/8685d951-05a8-4740-ba2b-c0363860f720" />

- Outcome
The security baseline verification script ran successfully and confirmed that the key security services configured in previous steps are operational. This demonstrates that the server meets the required security baseline for secure remote administration and protection against common threats.

- Reflection
Running an automated security baseline script provides a reliable way to verify system security configuration consistently. It reduces human error, saves time during audits, and ensures that critical services such as SSH, firewall rules, and intrusion prevention remain active and correctly configured.

## Step 5: Remote Monitoring Script
- Commands Used
```bash
nano monitor-server.sh
chmod +x monitor-server.sh
./monitor-server.sh
```

- Evidence
The monitoring script was executed successfully on the Ubuntu server and produced output displaying current CPU usage, memory usage, and disk usage. A screenshot was captured showing the script output, confirming that the monitoring functionality works as intended.

<img width="800" height="600" alt="week5_step5_monitoring_script_output" src="https://github.com/user-attachments/assets/2bf1bafd-ca89-4ba8-a730-58fbd6acc1f7" />

- Outcome
The remote monitoring script executed successfully and displayed real-time system performance metrics, including CPU usage, memory usage, and disk usage. This confirms that the script can effectively monitor key system resources on the server.

- Reflection
Creating a remote monitoring script demonstrates the importance of continuously observing system performance on a server. Being able to view CPU, memory, and disk usage remotely helps identify potential performance issues early and supports informed decision-making when managing system resources.
