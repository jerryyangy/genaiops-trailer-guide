# GenAI Operations (GenAIOps) Summary

## Overview
The **`mslearn-genaiops`** hands-on guide covers end-to-end GenAIOps patterns for building, versioning, evaluating, monitoring, and optimizing generative AI agents using **Microsoft Foundry** and **Azure AI Services**.

---

## Key Lifecycle Stages & Tools

### 1. Environment & Infrastructure Setup
* **Tools:** Azure Developer CLI (`azd`), Azure CLI (`az`), Bicep, Git.
* **Key Steps:** 
  * Provision Azure AI resources programmatically via `azd up`.
  * Export environment configurations (`.env`) for local/SDK development.

### 2. Prompt Management & Agent Versioning
* **Tools:** Python SDK (`azure.ai.projects`), Git.
* **Key Practice:** Treating prompts as code (version-controlled text files) rather than hardcoded strings, tagging releases in Git (`v1`, `v2`, `v3`) along with programmatic agent updates.

### 3. Prompt Optimization & Automated Evaluation
* **Tools:** Cloud Evaluators, GitHub Actions.
* **Key Practice:** 
  * Systematic local testing against ground-truth datasets.
  * Automated CI/CD evaluation pipelines (`evaluate-agent.yml`) triggered on Pull Requests to score metrics like groundedness, coherence, and safety.

### 4. Production Monitoring & Tracing
* **Tools:** Application Insights, Log Analytics.
* **Key Practice:** Implementing distributed tracing to observe latency, token consumption, error rates, and side-by-side performance comparisons across agent versions.

### 5. Advanced Optimization (Fine-Tuning)
* **Techniques:** Supervised Fine-Tuning (SFT), Direct Preference Optimization (DPO), and Reinforcement Fine-Tuning (RFT) when prompt engineering hits performance limits.

---

## Core Takeaways
* **Infrastructure as Code:** Fast, reproducible environment setup via Bicep/`azd`.
* **Prompt as Code:** Version-controlled prompts integrated directly into development workflows.
* **Quality Gates:** PR automated evaluations prevent regression in production.
* **Observability:** Full telemetry across token usage, latencies, and agent responses.
