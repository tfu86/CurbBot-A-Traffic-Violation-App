# Traffic Violation Detection Using Caption Data
*A GPT-4 powered civic tech tool for urban traffic monitoring and automated reporting*

## Overview
This project uses AI to detect traffic violations using caption metadata from urban traffic footage. Built with multi-agent LLM pipelines and orchestrated through n8n, this tool generates structured summaries—such as CSV reports and Slack alerts—to support city planners, analysts, and enforcement teams.

---

## Use Case

City agencies and urban planners often lack scalable tools for analyzing traffic violations from footage. This system uses automates review by using **caption metadata** to:

- Detect bus lane violations, illegal turns, and unauthorized parking
- Group and summarize infractions into structrued formats (CSV, Slack)
- Improve feedback loops for policy enforcement and public communication

---

## How It Works

- **Google Colab**: Hosts preprocessing and caption parsing logic  
- **GPT4 & Prompt Engineering**: User prompts agents for specific violation detection 
- **LLM Chaining**: Delegates violation detection and summarization tasks across agents 
- **n8n**: Orchestrates the pipeline: prompt generation, caption chunking, model calls, Slack output  

---

## Folder Structure

```bash
├── /data/         # Sample caption input (e.g., captions_sample.json)
├── /notebook/     # Python scripts and notebooks
├── /n8n/          # Exported n8n workflow
├── /screenshots/  # Output of workflow
├── README.md
```

---

## 🔬 Google Colab Notebook

[`caption_traffic_violation_pipeline_FINAL.ipynb`](notebook/caption_traffic_violation_pipeline_FINAL.ipynb)  
This notebook handles caption preprocessing and RAG-ready formatting.  
> **Note:** To run this, enable "Notebook Access" in Colab and add a secret named `HF_TOKEN`.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tfu86/CurbBot-A-Traffic-Violation-App/blob/main/notebook/caption_traffic_violation_pipeline_FINAL.ipynb)
---

## Dataset Access

This project uses caption metadata derived from the [OVD-Labs MRTMD dataset](http://43.128.62.24:91/OVD-Labs/MRTMD).  
- The full dataset is not included in this repo due to size and licensing restrictions.
- A sample (`captions_sample.json`) is provided in this repository for demo purposes only.
- All rights to the original dataset beling to the creators of the MRTMD dataset

Example format:
```json
{
  "video1_frame_317.jpg": "A car is turning right on a red bus-only signal",
  "video1_frame_318.jpg": "A motorcycle is stopped in the bus lane",
  "video1_frame_319.jpg": "A van is parked next to a fire hydrant"
}
```

---

## Outputs

The final output of the system includes:
- A structured Slack message summarizing violations by type
- A CSV of results grouped by filename and description

---

## Contributors:

- **Tiffany Fu**
- **Rachel Rose Lieberman**
- **Brihan Browne**

---

## 📘 About This Project

This tool was developed as part of the **AI Product Management Capstone** through Elvtr (2025).  
The capstone focused on building responsible, user-focused AI products using real-world workflows.  
This project applies agentic reasoning, RAG prompting, and civic tech use cases to demonstrate both product strategy and technical orchestration.
