# Technical Stack and Project Requirements

This document outlines the software, infrastructure, and specific Python dependencies used in the development of the Proactive Threat Detection and Security Monitoring Tool.

## 1. Core Tools and Infrastructure
The system is built as a hybrid detection and response platform. The lab environment is hosted on **Oracle VirtualBox** to ensure an isolated and safe simulation of cyberattacks.

* **Attacker Node:** Kali Linux (pre-loaded with penetration testing tools like Nmap and Impacket).
* **Victim Endpoint:** Windows 10 (Target for generating Security and Sysmon logs).
* **SIEM Platform:** Wazuh Server (Handles centralized monitoring, log analysis, and custom rules).
* **Firewall/Gateway:** pfSense (Responsible for network segmentation and automated IP blocking).
* **Analytics & Visualization:** Ubuntu for ELK Stack (Elasticsearch, Logstash, Kibana) and Vega for advanced correlation graphs.

## 2. Detection and Analysis Techniques
The system uses a multi-layered approach to identify and mitigate threats:

* **Detailed Telemetry:** Integration of Sysmon with Windows Event Channels for deep process-level visibility.
* **Custom Rule Logic:** A specialized set of Wazuh rules (IDs 200011–200020) mapped to the MITRE ATT&CK framework to classify attack stages.
* **Hybrid Risk Scoring:** A combination of Machine Learning (Random Forest) probability and Contextual Scoring (behavioral progression and historical activity).
* **Session Correlation:** Linking multiple related events into a single attack sequence using a unique `chain_key`.
* **Automated Containment:** Real-time IP blocking and firewall state termination on pfSense via SSH key-based automation.

## 3. Python Library Dependencies
The custom intelligence and automation layer is developed in Python. Ensure these are installed in your environment:

### A. Data Generation & Augmentation
Used for processing and expanding the AIT-ADS dataset to one million records.
* `pandas`
* `numpy`

### B. Model Training
Used to train the Random Forest Classifier on behavioral features like velocity and severity.
* `pandas`
* `sklearn` (scikit-learn)
* `joblib`
* `time`

### C. Evaluation
Used for calculating performance metrics including precision, recall, and F1-score.
* `pandas`
* `joblib`
* `sklearn.metrics`

### D. Real-time ML Alert Processing (`ml.py`)
The core engine that monitors `alerts.json`, extracts fields, and generates dynamic risk scores.
* `json`, `re` (regex)
* `pandas`, `joblib`
* `subprocess`, `os`
* `time`, `datetime`, `collections`

### E. Automated Response (`response.py`)
Handles the secure integration with pfSense and triggers incident documentation.
* `json`, `os`
* `subprocess` (for SSH automation)
* `datetime`, `sys`, `site`
* `generate_report` (Internal module)

### F. Forensic PDF Reporting (`generate_report.py`)
Automates the creation of professional incident reports.
* `reportlab`
* `os`
* `datetime`
