# Scrum Methodology and Sprint Breakdown

This project followed the **Scrum framework** (an Agile methodology) to ensure iterative development, continuous testing, and the ability to adapt to complex integration challenges between the SIEM, ML engine, and firewall.

## The Scrum Lifecycle
1.  **Product Backlog:** All tasks were identified and prioritized, including environment setup, log parsing logic, and automated response scripts.
2.  **Sprint Planning:** Specific goals were set for 2-week increments to ensure a steady progression from infrastructure to intelligent automation.
3.  **Sprint Development:** The core build phase where features were implemented incrementally.
4.  **Sprint Review & Retrospective:** Each phase concluded with a demonstration of functionality (e.g., successful log ingestion or attack detection) and an evaluation of challenges like configuration errors.

## Sprint Breakdown (Sprints 1–6)
*   **Sprint 1: Environment Setup & Infrastructure**
    Created an isolated lab using Oracle VirtualBox. Configured VMs for Kali Linux (Attacker), Windows 10 (Target), Wazuh (SIEM), Ubuntu (ELK), and pfSense (Firewall).
*   **Sprint 2: Integration & Log Processing**
    Established the log pipeline. Integrated Wazuh with the ELK Stack using Filebeat to ensure logs were indexed and searchable in real-time .
*   **Sprint 3: Event Correlation & Detection**
    Developed the "core intelligence." Configured custom Wazuh rules and implemented the Python-based ML engine for dynamic risk scoring and automated response logic.
*   **Sprint 4: Dashboard Development & Optimization**
    Built visual analytics in Kibana and Vega. Focused on MITRE-based threat maps, risk heatmaps, and fine-tuning alert thresholds to reduce false positives.
*   **Sprint 5: Testing & Validation**
    Conducted multi-layered testing (Unit and System). Simulated multi-stage attacks to verify that the automated response only triggers on high-confidence threats.
*   **Sprint 6: Documentation & Finalization**
    Completed the technical documentation, forensic report templates, and final system performance analysis.

