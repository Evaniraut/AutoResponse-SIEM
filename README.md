# AutoResponse-SIEM
An integrated, real-time security monitoring system designed to detect, analyze, and automatically mitigate multi-stage cyber threats using an open-source security stack and machine learning risk scoring.

## Overview
The Proactive Threat Detection and Security Monitoring Tool is an integrated SOC framework designed to detect, analyze, and automatically respond to multi-stage cyberattacks in real-time. It addresses the operational challenges of traditional SIEMs such as isolated event analysis and manual response delays by introducing hybrid detection that correlates related security events into a continuous, observable attack chain.
## System Architecture
![System Architecture Diagram](Diagrams/System_Architecture_Diagram.png)

# Project Objectives
The development of this system was guided by the following core objectives:

* **Objectives Research and Scope Definition**: Investigating project requirements to establish a clear boundary for development.
* **Centralised Monitoring**: Designing and implementing a unified system to collect and analyse security data from different sources.
* **Detection and Risk Integration**: Combining specialised detection rules with dynamic risk scoring to identify and prioritise high-risk security events, effectively reducing alert fatigue.
* **Attack Event Correlation**: Employing advanced detection techniques to link multi-stage attack events into a single sequence (attack chain) and identify broader attack patterns.
* **Response Automation**: Mitigating identified threats through automated actions, specifically IP blocking and session termination through firewall integration.
* **Visualisation Development**: Building Kibana dashboards to provide real-time visibility into security logs, attack progressions, and calculated risk scores.
* **System Validation**: Conducting attack simulations to test and validate the system's accuracy in both detecting threats and executing responses.
* **Documentation and Future Planning**: Recording the system's design and testing outcomes while identifying potential future improvements.
