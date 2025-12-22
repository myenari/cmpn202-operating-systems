Week 3 – Application Selection for Performance Testing
Introduction

This phase focuses on selecting representative applications to evaluate system performance under different workload types. The aim is to understand how the Ubuntu Server virtual machine behaves under CPU, memory, disk, and network load before conducting detailed performance testing in later phases.

Application Selection Matrix

CPU-Intensive Application
Application: stress-ng
Justification: Stress-ng is used to generate high CPU load to evaluate processor utilisation, scheduling behaviour, and system stability under intensive computation.

Memory-Intensive Application
Application: stress-ng (memory and VM tests)
Justification: Memory stress tests allow observation of RAM usage, swap behaviour, and system responsiveness when memory resources are heavily utilised.

I/O-Intensive Application
Application: fio
Justification: Fio simulates disk read and write workloads to measure storage performance and identify potential I/O bottlenecks.

Network / Server Application
Application: Apache Web Server
Justification: Apache represents a real-world server workload involving network traffic and concurrent client requests, making it suitable for network and server performance evaluation.

Installation Documentation (SSH-Based)

All applications are installed remotely via SSH on the Ubuntu Server VM.

Update package lists:

sudo apt update


Install stress-ng:

sudo apt install stress-ng -y


Install fio:

sudo apt install fio -y


Install Apache web server:

sudo apt install apache2 -y

Expected Resource Profiles

CPU Tests: High CPU utilisation with minimal disk and network activity.

Memory Tests: Increased RAM usage with possible swap activity under heavy load.

I/O Tests: High disk read/write activity with moderate CPU usage.

Network Tests: Increased network throughput and concurrent connection handling.

Monitoring Strategy

System performance will be monitored using command-line tools such as top, htop, free, df, and iftop. These tools provide real-time insight into CPU usage, memory consumption, disk activity, and network traffic during workload execution.
