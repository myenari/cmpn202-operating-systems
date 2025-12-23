# Week 4 – Secure Remote Access (SSH)

## Aim
The aim of this week is to configure and verify secure remote access to the Ubuntu Server using SSH. This ensures the system can be managed remotely in a secure and controlled manner.

## Introduction
This week focuses on configuring foundational security controls on the Ubuntu Server virtual machine. The goal is to secure remote administration by enforcing secure SSH access, limiting privileges, and preparing the system for further security hardening in later phases.

---

## Step 1: Secure SSH Configuration (Key-Based Authentication)

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

