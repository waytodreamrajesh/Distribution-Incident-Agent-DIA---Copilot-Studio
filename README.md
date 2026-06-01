# Distribution Incident Agent (DIA) 🌡️

### Autonomous Cold-Chain Logistics Deviation Triage System

Built on Microsoft Copilot Studio | Operative Track — Microsoft Agent Academy Hackathon 2026

---

## 📋 What is the Distribution Incident Agent?

The **Distribution Incident Agent (DIA)** is a fully autonomous, multi-agent compliance ecosystem designed to handle complex temperature deviations and data lineage across pharmaceutical supply chains.

When a logistics deviation occurs during cold-chain transit, DIA automatically:
*   **Intercepts & Validates:** Intercepts raw telemetry data via natural language query or system integration.
*   **Triggers Intake Workflows:** Maps location metadata, transit routes, and logistics service providers natively.
*   **Computes Cross-Table Lineage:** Interrogates Microsoft Dataverse relational structures to instantly calculate connections across multiple tables (e.g., counting linked Investigation, PQIAS, or ECAPAS workflows).
*   **Enforces GxP Compliance SOPs:** Evaluates excursion parameters against strict regulatory standard operating procedures.
*   **Generates Audit-Ready Documentation:** Automatically triggers a Power Automate transaction pipeline to compile a standardized, structured Investigation Report.
*   **Secures File Distribution:** Safely serves a secure, clickable report download link directly within the conversational interface without workflow time-outs.

From a raw temperature excursion flag to an audit-ready, multi-table compliance report in under 60 seconds. Zero manual database navigation required.

---

## 🎯 The Problem It Solves

Pharmaceutical cold-chain logistics deviation triage is a high-stakes, manual bottleneck. When a temperature excursion happens, quality assurance (QA) teams must manually extract siloed telemetry logs, evaluate data lines against complex GxP SOP tables, determine cross-system records lineage, and write initial triage paperwork. This process often takes hours, presents severe audit trail risks, and slows down the critical 60–90 day stability testing execution pipeline.

**DIA eliminates this friction entirely** by transforming a complex relational data audit into a single, seamless conversational stream.

---

## 🏗️ Architecture

### Hub & Spoke Multi-Agent System

```text
       [User Interaction / System Request]
                       │
                       ▼
         Incident Agent (Hub Orchestrator)
                       │
      ┌────────────────┼────────────────┐
      ▼                ▼                ▼
┌────────────┐   ┌────────────┐   ┌─────────────────────┐
│   Intake   │   │ Compliance │   │ Investigation Agent │
│   Agent    │   │ & SOP Sub- │   │ (Connected Lookup & │
│  (Child)   │   │   Agent    │   │  Report Generation) │
└─────┬──────┘   └────────────┘   └──────────┬──────────┘
      │                                      │
      ▼                                      ▼
[Power Automate]                      [Power Automate]
 (Create Record)                       (DocX Gen Flow)
      │                                      │
      └────────────────┬─────────────────────┘
                       │
                       ▼
          Microsoft Dataverse Layer
   (rg_logisticsincident, rg_investigation,
        rg_pqias, rg_ecapas tables)
