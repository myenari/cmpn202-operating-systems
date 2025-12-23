# Week 6 – Evaluation and Analysis

## Aim
The aim of this week is to evaluate the effectiveness of the security and monitoring mechanisms implemented on the Ubuntu server. 
This includes analysing their impact on system performance, identifying strengths and limitations, and considering potential improvements.

## Introduction
In previous weeks, several security controls and monitoring tools were implemented on the Ubuntu server, including SSH hardening, firewall rules, AppArmor,
automatic updates, Fail2Ban, and custom verification and monitoring scripts. This week focuses on evaluating how effective these measures are in securing the system
and assessing their impact on overall performance and usability.

## Section 1: Evaluation of Security Controls
The implemented security controls significantly improved the server’s protection against common threats. SSH hardening reduced the risk of unauthorized access,
while Fail2Ban provided automated defence against brute-force attacks. AppArmor enforced mandatory access control policies, limiting the actions applications 
could perform even if compromised. Together, these controls created a layered security approach that strengthened the overall system posture.

## Section 2: Performance Impact Analysis
The performance impact of the implemented security measures was minimal. Monitoring results showed that CPU, memory, and disk usage remained within acceptable levels
during normal operation. Services such as Fail2Ban and AppArmor run efficiently in the background and did not introduce noticeable performance degradation, demonstrating 
that strong security can be achieved without significantly affecting system performance.

## Section 3: Effectiveness and Limitations
While the security mechanisms were effective, there are limitations to the current configuration. AppArmor profiles were not customised for specific applications,
which could further enhance security. Additionally, the monitoring scripts provide only snapshot-based information rather than continuous monitoring.
Advanced tools such as centralised logging or real-time dashboards could improve visibility and response capabilities.

## Section 4: Reflection and Improvements
This evaluation highlighted the importance of balancing security, performance, and usability. Implementing layered security controls improved protection without 
compromising performance. Future improvements could include fine-tuning AppArmor profiles, implementing alert-based monitoring, and automating reporting to further
strengthen system management and security oversight.
