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
```
### Key Components

| Component | Technology |
| :--- | :--- |
| **Multi-Agent Orchestration** | Microsoft Copilot Studio (Generative Orchestration) |
| **Data Layer** | Microsoft Dataverse (Custom GxP Triage Tables) |
| **Automation & Document Pipeline** | Power Automate Cloud Flows |
| **Telemetry Grounding** | Dataverse Public Views & Schema Optimization |
| **Output Engine** | Word Online (Business) Connector & Token Mapping |

## 🤖 The Agents

### Incident Agent (Hub Orchestrator)
The central brain. Uses Microsoft Copilot Studio generative orchestration to dynamically analyze intent and route requests seamlessly to the specialized spokes based on clear routing descriptions and strict boundary constraints.

### Intake Agent (Child)
Handles front-end conversation logging. It collects structured compliance metadata (transit routes, locations, and logistics partners) and initiates conversational data collection parameters before writing records to Dataverse.

### Compliance & SOP Sub-Agent (Child)
Functions as a theoretical regulatory knowledge domain. It evaluates specific excursion boundaries (e.g., temperature threshold bands, 4-hour windows) purely against reference standard operating procedures without making live transactional modifications.

### Investigation Agent (Connected)
The high-utility lookup and generation hub. It aggregates relational metrics across tables (e.g., "how many investigations exist for this incident ID?") and passes localized variable tokens to Power Automate to dynamically render and share the finalized, downloadable document.

---

## 🚀 How to Set Up (Quick Start)

The Distribution Incident Agent ecosystem is packaged completely within a Power Platform solution container for rapid deployment.

### Prerequisites
* A Power Platform environment with a Dataverse database enabled.
* Premium licensing for Microsoft Copilot Studio and Power Automate.

### Deployment Steps
1. **Import the Solution:** Go to [make.powerapps.com](https://make.powerapps.com), select your environment, navigate to **Solutions**, click **Import solution**, and upload `solution/IncidentAgent_1_0_0_Managed.zip`.
2. **Configure Connection References:** During the import process, link the connection references to your local Outlook, Word Online, and Dataverse connectors.
3. **Publish All Components:** Once the import completes successfully, click **Publish all customizations** to ensure the child agents and cloud flows are fully synchronized.
4. **Test the Pipeline:** Open the main `Incident Agent` within Copilot Studio and begin your conversational testing stream!

---

## 🏆 Agent Academy Curriculum Alignment

| Mission | Concept | How Applied |
| :--- | :--- | :--- |
| **Mission 01 & 02** | Agent Instructions | Built specialized agents with strict step-by-step instructions and clear operational guardrails. |
| **Mission 03** | Multi-Agent Systems | Leveraged the Hub-and-Spoke pattern to control traffic across 3 specialized sub-agents. |
| **Mission 06** | AI Safety & Moderation | Configured a customized AI Safety Greeting Notice and custom fallbacks for security and audit readiness. |
| **Mission 08** | Dataverse Grounding | Grounded lookups in multi-table Dataverse structures to provide natural language relational data auditing. |
| **Mission 09** | Document Generation | Developed an end-to-end automated template rendering flow for formal file downloads. |

---

incident-agent-copilot/
├── README.md
├── solution/
│   ├── AgentHackathon_1_0_0_1_managed.zip
│   └── AgentHackathon_1_0_0_2_unmanaged.xip
|
├── docs/
│   
     └── system-architecture.png

---

## 🎥 Demo Video

[Link to Your 3-5 Minute Demo Video Here]

---

## 👤 Author

**Rajesh G.** *Senior Associate Analyst — Automation & Analytics Solutions* * **LinkedIn:** [https://www.linkedin.com/in/rajeshkva/]
* **GitHub:** `@waytodreamrajesh`

---

## 📄 License

This project is submitted as an official entry for the **Microsoft Agent Academy Hackathon 2026**. Built with ❤️ utilizing Microsoft Copilot Studio, Power Automate, and Microsoft Dataverse.
