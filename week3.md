# Week 3 – Application Selection for Performance Testing

## Introduction
This phase focuses on selecting representative applications to evaluate system performance under different workload types. The goal is to understand how the Ubuntu Server virtual machine behaves under CPU, memory, disk, and network load in preparation for later performance testing phases.

---

## Application Selection Matrix

### CPU-Intensive Application
**Application:** stress-ng  
**Workload Type:** CPU-intensive  
**Justification:**  
Stress-ng is used to generate high CPU load and stress processor scheduling and computation. It is suitable for observing CPU utilisation, load averages, and system stability under intensive processing.

---

### Memory-Intensive Application
**Application:** stress-ng (memory tests)  
**Workload Type:** RAM-intensive  
**Justification:**  
Memory stress tests allocate and consume large amounts of RAM, allowing observation of memory usage, swap behaviour, and system responsiveness when memory resources are heavily utilised.

---

### I/O-Intensive Application
**Application:** fio  
**Workload Type:** Disk I/O-intensive  
**Justification:**  
Fio simulates disk read and write workloads and is used to identify disk performance limits and potential I/O bottlenecks under sustained storage activity.

---

### Network / Server Application
**Application:** Apache Web Server  
**Workload Type:** Network-intensive / Server workload  
**Justification:**  
Apache represents a real-world server application handling network traffic and concurrent client requests, making it suitable for evaluating network throughput and server responsiveness.

---

## Installation Documentation (SSH-Based)

All applications are installed remotely on the Ubuntu Server VM using SSH.

```bash
sudo apt update
sudo apt install -y stress-ng fio apache2

Expected Resource Profiles

The expected resource usage for each application is outlined below. These profiles define anticipated system behaviour before testing begins.

stress-ng (CPU): High CPU utilisation across available cores, increased load average, minimal disk activity.

stress-ng (Memory): High RAM consumption, potential swap usage if memory limits are exceeded, moderate CPU usage.

fio: High disk read/write activity, increased I/O wait times, moderate CPU usage.

Apache Web Server: Moderate CPU usage, increased network throughput, stable memory usage under normal request loads.

Monitoring Strategy

System performance will be monitored remotely via SSH using command-line tools during application execution.

CPU & Load: top, htop, uptime

Memory Usage: free -h, vmstat

Disk I/O: iostat, df -h

Network Activity: iftop, ss, Apache access logs

These tools will allow real-time observation of system behaviour and provide baseline measurements for later analysis phases.
