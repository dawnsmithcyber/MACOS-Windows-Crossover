# MACOS-Windows-Crossover
Documentation of a cloud-native security rebuild focusing on Azure Sentinel, Defender, and KQL. This project highlights cross-platform management (macOS-Windows), Azure CLI troubleshooting, and cost-optimization (FinOps) strategies to ensure a secure, hardware-independent environment for threat hunting.
# Azure Security Lab: Optimization & Sentinel Readiness

## 📌 Project Overview
Following a hardware-driven pivot to a cloud-native workflow, I performed a comprehensive "clean slate" audit of my Azure environment. This project established a stable, cost-effective foundation for a new SIEM lab while eliminating "ghost" billing from orphaned resources.

## 💻 Cross-Platform Management (macOS-Windows Crossover)
* **Host System:** macOS (MacBook Air)
* **Target Environment:** Windows-based Azure Infrastructure (Sentinel & Defender)
* **Tooling:** Leveraged the **Azure CLI for macOS** and **Microsoft Remote Desktop** to bridge the gap between local hardware and cloud-based Windows resources. 
* **The Strategy:** This crossover allows for a flexible, hardware-independent workflow regardless of the local operating system, ensuring that security operations remain functional even during hardware transitions.

## 🛠️ Key Actions Taken

### 1. Azure CLI Configuration & Troubleshooting
* **Challenge:** Initial scoping errors and authentication hurdles when using the CLI on macOS.
* **Solution:** Successfully mapped the CLI to the correct subscription context and resolved Resource Group requirement errors.
<img width="560" height="242" alt="Terminal_2" src="https://github.com/user-attachments/assets/5078969b-ac10-4193-8c64-d76c8aad6e5e" />
* **Result:** Full command-line control over cloud resources, complementing the visual management of the Azure Portal.
<img width="767" height="449" alt="Confirmation_nocharges" src="https://github.com/user-attachments/assets/cde23811-d8e3-45a6-8950-676fc61f141f" />

## 🔍 Troubleshooting Log: The "Missing Brew" Path
While setting up the local environment on macOS, I encountered a common hurdle for new system installs:

* **The Issue:** Attempting to install the Azure CLI via `brew` resulted in a `zsh: command not found: brew` error. 
* **The Diagnosis:** Identified that the Homebrew package manager was not yet initialized or installed in the local shell environment.
* **The Fix:** 1.  Executed the Homebrew installation script via `/bin/bash -c`.
    2.  Authenticated via `sudo` to grant the necessary directory permissions.
    3.  Verified the "Pouring" of dependencies (Python 3.13, SQLite, etc.) to ensure a clean build.
* **The Result:** Successfully bridged the gap between the local macOS terminal and the Azure Cloud API.

### 2. Orphaned Resource & "Ghost" Billing Audit
To ensure a $0.00 starting balance and prevent "hidden" costs, I conducted a deep scan of:
* **Managed Disks:** Verified a "No disks to display" status to confirm no orphaned storage volumes.
* **Network Interfaces (NICs) & Public IPs:** Audited and removed unassociated assets from previous deployments.
<img width="764" height="149" alt="Success" src="https://github.com/user-attachments/assets/3344facd-008f-467b-9d62-823a1f999a5d" />
**Verification:** Performed a dual-layer audit using both the **Azure Portal (GUI)** and **Terminal (CLI)** for a definitive "Source of Truth."

### 3. Financial Guardrails (FinOps)
* **Budget Alert:** Configured a hard threshold of **$5.00 USD/month**.
* **Automation:** Set up automated email triggers at **100% of actual spend**.
<img width="1262" height="555" alt="Budgets_set" src="https://github.com/user-attachments/assets/cd56fbc7-d9e0-44be-92c3-c4a17d914a53" />
* **Purpose:** Ensures total visibility and prevents cost overruns during intensive KQL query testing or log ingestion.

## 🏆 The Win
I have successfully established a **secure, cost-controlled, and hardware-independent environment**. I am now fully prepared to leverage **Azure Sentinel** and **Microsoft Defender for Cloud**, with the flexibility to manage the stack via the **Azure Portal** or **Terminal**.

## 🚀 Next Steps: Project-SkyWatch Rebuild
* **Deployment:** Provisioning a B-series VM (Burstable) for optimal cost-to-performance.
* **Log Ingestion:** Configuring Data Connectors to stream telemetry into Log Analytics.
* **Threat Hunting:** Developing custom KQL queries to monitor for brute-force and persistence techniques.
---
