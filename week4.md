# Week 4 – Initial System Configuration & Security Implementation

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


Outcome

The SSH service restarted successfully and is running in an active state. This confirms that the OpenSSH server is operational and ready for secure remote access using SSH.

Evidence

Terminal output showing Active: active (running) for the SSH service.

Screenshot evidence captured to demonstrate successful SSH service status.

Reflection

This step reinforced the importance of securely managing remote access to a server. Verifying the SSH service status ensures that configuration changes are correctly applied and that the system is prepared for further security controls, such as disabling root login and restricting access via firewall rules.
