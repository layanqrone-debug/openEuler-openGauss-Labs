# openEuler & openGauss DBA Training Labs 

Welcome to my hands-on practice repository for administering the **openGauss Database** running on the **openEuler Enterprise Linux** platform. This repository documents a structured learning path from basic service management to advanced database administration and troubleshooting scenarios.

---

## 💻 Environment Specifications
* **Operating System:** openEuler 22.03 LTS
* **Database Engine:** openGauss 5.0.2
* **Deployment Topology:** Single-node
* **Installation Method:** simpleInstall
* **Database Management Tool:** `gs_ctl`
* **Data Directory Path:** `/opt/software/data/single_node`

---

## 📂 Laboratory Index & Progress

### 🛠️ [Lab 01: Service Management](./Lab01-Service-Management)
Instance-level management and control loop cycles using the `gs_ctl` utility.
* **Initial Status Audit:** `gs_ctl -D /opt/software/data/single_node status`
* **Safe Service Shutdown:** `gs_ctl -D /opt/software/data/single_node stop`
* **Post-Shutdown Verification:** `gs_ctl -D /opt/software/data/single_node status`
* **Service Initialization:** `gs_ctl -D /opt/software/data/single_node start`
* **Final Runtime Check:** `gs_ctl -D /opt/software/data/single_node status`

### 🔌 [Lab 02: Database Connection](./Lab02-Database-Connection)
Establishing localized and terminal-based connections into the database engine.
* **Interactive CLI Tool:** Connecting to the active instance via `gsql`

### 👥 [Lab 03: Databases and User Management](./Lab03-User-and-DB-Management)
Implementation of Role-Based Access Control (RBAC) and logical storage separation.
* **User Provisioning:** Creating secured database users and roles.
* **Database Creation:** Allocating isolated target logical databases.
* **Privilege Delegation:** Granting schema-level and object-level permissions.
* **Session Testing:** Verifying access restrictions by logging in via the newly created users.

### 📊 [Lab 04: Schema, Tables, and Data Operations (DML/DDL)](./Lab04-Data-Operations)
Core structural designs and data manipulation execution within the environment.
* **Schema Definition:** Isolating object namespaces using `CREATE SCHEMA`.
* **Table Modeling:** Constructing relation schemas with appropriate data types.
* **Data Ingestion:** Inserting records into relations (`INSERT`).
* **Query Execution:** Fetching and filtering structured datasets (`SELECT`).
* **Data Modification:** Altering existing transactional records (`UPDATE`).
* **Data Purging:** Removing rows cleanly from target tables (`DELETE`).

### 🔍 [Lab 05: Comprehensive Health Checks & Output Analysis](./Lab05-System-Health-Checks)
Deep-dive diagnostics of the running infrastructure using native verification utilities.
* **System Inspections:** Executing cluster-wide system parameter health audits using `gs_check`.
* **Output Log Deconstruction:** Parsing generated status logs, identifying optimization thresholds, and analyzing warning flags rather than just executing the binary.

### 🚨 [Lab 06: Advanced DBA Troubleshooting Scenarios](./Lab06-DBA-Troubleshooting)
Simulating enterprise production environment breakdowns to practice system diagnosis and recovery.
* **Simulated Faults:** Intentional induced environment crashes, corrupt settings, or connectivity blocks.
* **DBA Root Cause Analysis (RCA):** Parsing error streams, reviewing logs, diagnosing underlying state failures, and executing precise remediation methods.
*
