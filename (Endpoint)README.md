# Endpoint Security & Compliance Intelligence Pipeline

##  Strategic Objective & Business Value
In large-scale enterprise environments, maintaining endpoint health and patch parity is a critical line of defense against cyber vulnerabilities. I **engineered a centralized Endpoint Governance Dashboard** that provides SCCM Engineers and Subject Matter Experts (SMEs) with real-time visibility into the global estate’s security posture.

###  Key Achievements:
* **Automated Audit Readiness:** Transitioned the security team from manual, point-in-time health checks to a **fully automated, real-time compliance monitor**.
* **Risk Prioritisation:** Enabled SMEs to identify and remediate "Critical Update" failures within minutes, drastically reducing the organization's **Mean Time to Remediate (MTTR)**.
* **Data Fidelity:** Resolved data duplication and ambiguity issues, ensuring that engineers are working with the **Single Source of Truth** for device health.

---

##  Technical Architecture & Data Engineering
The SCCM database is notoriously complex, with device states often masked by cryptic error codes. I developed a multi-stage pipeline to decode and normalize this telemetry.



### 1. Advanced SQL & Python Orchestration
* **Complex Schema Merging:** Performed multi-table joins and recursive merges across SCCM’s relational schema to synthesize a holistic view of **Healthy vs. Non-Compliant** devices.
* **Error Code Decryption:** Engineered a lookup logic that maps raw system error codes to human-readable definitions (e.g., Scan Status, Patching Failures, and Health Errors), turning low-level logs into high-level insights.
* **Conflict Resolution Logic:** Developed a Python-based **Deduplication Engine**. SCCM often generates multiple records for a single device per day; I implemented logic to dynamically select the most recent, authoritative state record, ensuring data accuracy.

### 2. Cloud-Scale Integration
* **Automated Pipeline:** The end-to-end process—from SQL extraction to Python transformation—is fully automated and orchestrated.
* **Cloud Repository:** Transformed data is pushed to a secure Cloud storage layer, facilitating high-availability access for distributed stakeholders and real-time dashboard refreshes.

---

##  Analytical Insights for SCCM SMEs
The dashboard was specifically designed to empower Subject Matter Experts (SMEs) with **Precision Targeting**:



### Critical Intelligence Pillars:
* **Patch Compliance & Critical Updates:** A prioritized view of devices lacking high-severity security patches, allowing for immediate targeted remediation.
* **Device Health & Scan Status:** Identification of "Stale" or "Unreachable" clients that are failing to report heartbeats or scan results.
* **Compliance State Analysis:** A deep-dive into why devices are falling out of compliance, categorized by specific failure types decoded from the SCCM logs.

### Empowering the SME:
I worked closely with SMEs to ensure the dashboard facilitated a **"Drill-Down" workflow**:
1. **Macro View:** Observe the overall health percentage of the global estate.
2. **Filtered View:** Isolate specific business units or regions.
3. **Micro View:** Identify specific Device IDs requiring manual intervention, significantly reducing the "discovery time" for support engineers.

---

##  Technical Stack
* **Languages:** Python (Pandas, NumPy, SQLAlchemy), SQL (T-SQL)
* **Infrastructure:** SCCM (Microsoft Endpoint Configuration Manager), Cloud Data Storage
* **Business Intelligence:** Power BI / Tableau
* **Techniques:** Error Code Mapping, Temporal Deduplication, ETL Automation

---

##  Impact on Operations
Since deployment, the **SCCM Engineering Team** has reported a significant reduction in manual reporting overhead. The dashboard has become a cornerstone of the weekly **Security Patching Review**, allowing the team to focus 100% of their effort on remediation rather than data collection.
