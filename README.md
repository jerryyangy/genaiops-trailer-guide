# GenAI Operations (GenAIOps) Solution Summary & Hands-On Guide

> **Source Repository:** [Microsoft Learning: mslearn-genaiops](https://microsoftlearning.github.io/mslearn-genaiops/)

---

## 📌 Executive Summary

The **`mslearn-genaiops`** repository provides hands-on exercises for building, deploying, evaluating, monitoring, and optimizing Generative AI agents using **Microsoft Foundry** and **Azure AI Services**.

It establishes an end-to-end **GenAIOps framework**—applying classical DevOps and MLOps practices (version control, automated evaluation, telemetry tracing, and CI/CD) specifically to Generative AI workloads.

---

## 🏗️ Architecture & Key Components

| Component | Role in GenAIOps |
| :--- | :--- |
| **Microsoft Foundry (AI Services Hub/Project)** | Core workspace for managing models, prompts, agents, and cloud evaluators. |
| **Azure Developer CLI (`azd`)** | Infrastructure as Code (IaC) deployment via Bicep templates. |
| **Git / GitHub Actions** | Versioning prompts/agents and triggering automated evaluation pipelines. |
| **Application Insights & Log Analytics** | Runtime monitoring, token usage tracking, and distributed tracing. |
| **Python SDK** | Programmatic agent instantiation, prompt execution, and cloud evaluations. |

---

## 🛠️ Step-by-Step Lab Execution & Code Guide

### 1. Environment & Infrastructure Setup

#### Prerequisites
* Visual Studio Code
* Azure Subscription with Microsoft Foundry access
* Python 3.9+
* Azure CLI (`az`) and Azure Developer CLI (`azd`)

#### Execution Steps

```bash
# 1. Clone the repository template
git clone [https://github.com/](https://github.com/)<your-username>/mslearn-genaiops.git
cd mslearn-genaiops

# 2. Authenticate with Azure CLI & Azure Developer CLI
azd auth login
az login

# 3. Configure Git user credentials
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"

# 4. Provision Azure resources using Azure Developer CLI
azd up
# Select Environment Name (e.g., dev-trail-guide), Subscription, and Region (e.g., swedencentral)

# 5. Export environment variables to .env
azd env get-values > .env
