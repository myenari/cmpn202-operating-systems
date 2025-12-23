# Week 4 – Secure Remote Access (SSH)

## Aim
The aim of this week is to configure and verify secure remote access to the Ubuntu Server using SSH. This ensures the system can be managed remotely in a secure and controlled manner.

## Introduction
This week focuses on configuring foundational security controls on the Ubuntu Server virtual machine. The goal is to secure remote administration by enforcing secure SSH access, limiting privileges, and preparing the system for further security hardening in later phases.

---

## Step 1: Secure SSH Service Configuration and Verification

### Objective
To ensure secure remote access to the server by configuring the SSH service and verifying that it is running correctly. This step prepares the system for key-based authentication and secure administration.

---

### Actions Performed
- Accessed the Ubuntu Server virtual machine.
- Verified the SSH daemon configuration file (`/etc/ssh/sshd_config`).
- Confirmed SSH authentication settings.
- Restarted the SSH service to apply configuration changes.
- Verified that the SSH service is active and running.

---

### Commands Used
```bash
sudo systemctl restart ssh
sudo systemctl status ssh
```


## Evidence
Terminal output showing the SSH service running in an active state.
Screenshot evidence was captured to demonstrate successful SSH configuration.

## Outcome
The SSH service restarted successfully and remained active.  
This confirms that the server supports secure remote access via SSH.

## Reflection
This step reinforced the importance of verifying SSH services when managing a server.
Ensuring SSH is active allows secure administration while reducing exposure to insecure access methods.


## Step 2: Key-Based SSH Authentication

### Objective
To improve SSH security by using key-based authentication instead of password-based login.

### Action Performed
- Generated an SSH key pair on the client machine.
- Copied the public SSH key to the Ubuntu server.
- Verified that SSH login using the key was successful.

### Commands Used
```bash
ssh-keygen
ssh-copy-id mabdi@<server-ip>
ssh mabdi@<server-ip>
```

## Evidence
Terminal output showing successful SSH login without being prompted for a password.

## Outcome
SSH access was successfully configured using key-based authentication. This confirms that the server now supports more secure authentication methods.

## Reflection
Using SSH keys significantly improves security by eliminating password-based logins, reducing the risk of brute-force attacks and unauthorized access.

## Step 3: Firewall Configuration (UFW)

### Objective
To improve network security by restricting incoming traffic and allowing only essential services.

### Action Performed
- Enabled the Uncomplicated Firewall (UFW).
- Allowed SSH traffic to ensure remote access remained available.
- Verified firewall status to confirm correct configuration.

### Commands Used
```bash
sudo ufw allow ssh
sudo ufw enable
sudo ufw status
```

## Evidence
Terminal output showing the firewall is active and SSH traffic is allowed.

## Outcome
The firewall was successfully enabled and configured to allow SSH connections only. This reduces the system’s attack surface while maintaining secure remote administration.

## Reflection
Configuring a firewall is a fundamental security practice. Allowing only necessary services such as SSH helps protect the server from unauthorized network access.
