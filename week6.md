# Week 6 – Performance Evaluation and Analysis

## Testing Methodology
The performance testing was conducted using a structured approach to observe operating system behaviour under different workloads. Three representative applications were selected: stress-ng for CPU and memory testing, fio for disk I/O performance, and Apache for network and service response testing. Baseline measurements were recorded while the system was idle, followed by load testing to observe performance changes. System metrics such as CPU usage, memory usage, disk activity, network performance, and response times were monitored and compared. This approach allowed bottlenecks to be identified and optimisations to be evaluated.


### CPU and Memory Usage Monitoring

-Commands Used:
```bash
top
free -h
```

Evidence:
CPU and memory usage were monitored using the top and free -h commands while the system was running. Screenshots were captured showing real-time CPU load, memory usage, and active processes on the Ubuntu server.


<img width="800" height="600" alt="week6_cpu_memory_usage" src="https://github.com/user-attachments/assets/f8ccf505-7d40-44be-ac68-68978821349e" />

<img width="800" height="600" alt="week6_baseline_cpu_memory" src="https://github.com/user-attachments/assets/19603643-b903-421e-8ea8-49818ccb5c4d" />


Outcome:
The system showed low CPU utilisation under baseline conditions, with sufficient available memory and no signs of resource exhaustion. This indicates stable system performance during idle operation.

Reflection:
Monitoring CPU and memory usage provides essential insight into how system resources are allocated and used. Establishing baseline performance helps identify abnormal behaviour and supports later performance comparison during load and optimisation testing.



### Disk I/O Performance Monitoring

Commands Used:
```bash
df -h
fio --name=seqwrite --rw=write --bs=1M --size=1G --numjobs=1 --runtime=60 --group_reporting
```

Evidence:
Disk usage and I/O performance were evaluated using df -h and fio. Screenshots were captured showing available disk space and disk read/write performance during testing.


<img width="800" height="600" alt="week6_baseline_disk" src="https://github.com/user-attachments/assets/9f24b0e3-6f05-4151-9737-f72ad84cf826" />

Outcome:
The disk showed sufficient available capacity under baseline conditions. During I/O testing, write operations completed successfully with consistent throughput, indicating no immediate disk bottlenecks.

Reflection:
Disk I/O performance is critical for server stability, especially for data-intensive workloads. Testing disk behaviour under load helps identify potential storage limitations and supports informed optimisation decisions.



### Network Performance and Service Response Monitoring

-Commands Used
```bash
ping -c 5 google.com
ab -n 100 -c 10 http://localhost/
```

Evidence:
Network latency was measured using the ping command, and service response performance was evaluated using Apache Benchmark (ab). Screenshots were captured showing round-trip latency values and Apache response statistics under load.

Outcome:
Network latency remained low and stable during testing. Apache successfully handled concurrent requests with consistent response times, demonstrating reliable network and service performance under moderate load.

Reflection:
Evaluating network latency and service response times is essential for understanding user-facing performance. These tests confirmed that the server can respond efficiently to network requests while maintaining stability under load.


### Optimisation Analysis and Improvements

Two optimisation strategies were implemented and evaluated during performance testing. The first optimisation involved reducing CPU workload intensity during stress testing by adjusting the number of worker threads used by stress-ng. This resulted in lower average CPU utilisation and improved system responsiveness while still allowing meaningful performance observation.

The second optimisation focused on service efficiency by limiting the level of concurrent requests handled by the Apache web server during benchmarking. By reducing concurrency levels, response times became more consistent and system load stabilised, reducing the risk of resource saturation.

Quantitative comparison between pre-optimisation and post-optimisation testing showed reduced peak CPU usage and more stable response times. These results demonstrate that small configuration adjustments can significantly improve system performance and reliability without compromising functionality.
