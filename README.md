# Traffic Violation Detection Using Caption Data
*A GPT-4 powered tool for urban traffic monitoring and automated reporting*

This project uses AI to identify traffic violations—like illegal turns, bus lane blocking, and unauthorized parking—by analyzing caption data from city traffic cameras. No images are used. Built with multi-agent LLM pipelines and automated workflows in n8n, this tool summarizes violations and sends structured outputs (e.g., Slack messages, CSV reports) for use by planners, analysts, or enforcement teams.

---

## Use Case

City planners and law enforcement teams often lack tools to efficiently analyze traffic footage at scale. This app uses **caption metadata** to:

- Detect bus lane violations, illegal turns, and unauthorized parking
- Group and summarize infractions into CSV or Slack/email outputs
- Enable faster policy feedback and public communication

---

## How It Works

- **RAG & Prompt Engineering**: Tailors prompts dynamically based on input metadata  
- **LLM Chaining**: Multi-agent reasoning using GPT-4  
- **n8n Integration**: Orchestrates prompt generation, caption chunking, model calls, Slack output  
- **Colab**: Hosts preprocessing and caption parsing logic  
- **Replit**: (Optional) Prototyped front-end UI for demo purposes  

---

## 🔬 Google Colab Notebook

[`caption_traffic_violation_pipeline_FINAL.ipynb`](notebook/caption_traffic_violation_pipeline_FINAL.ipynb)  
This notebook handles caption preprocessing and RAG-ready formatting.  
> **Note:** To run this, enable "Notebook Access" in Colab and add a secret named `HF_TOKEN`.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tfu86/CurbBot-A-Traffic-Violation-App/blob/main/notebook/caption_traffic_violation_pipeline_FINAL.ipynb)
---

## Dataset Access

This project uses caption metadata from the [OVD-Labs MRTMD dataset](http://43.128.62.24:91/OVD-Labs/MRTMD).  
- The full dataset is not included in this repo due to size and licensing.
- A sample (`captions_sample.json`) is provided in this repository for demo purposes only.

Example format:
```json
{
  "video1_frame_317.jpg": "A car is turning right on a red bus-only signal",
  "video1_frame_318.jpg": "A motorcycle is stopped in the bus lane",
  "video1_frame_319.jpg": "A van is parked next to a fire hydrant"
}
```

---

## Folder Structure

```bash
├── /colab/        # Python scripts and notebooks
├── /n8n/          # Exported n8n workflow(s)
├── /data/         # Sample caption input (e.g., captions_sample.json)
├── /replit/       # (Optional) Frontend prototype code
├── README.md
```

---

## Outputs

The final output of the system includes:
- A structured Slack message summarizing violations by type
- A CSV of results grouped by filename and description
- Optional email/social copy via GPT-4 summarization

---

## Contributors:

- **Tiffany Fu** – Data Lead  
- [Your teammates or collaborators here]

---

## 📜 License

MIT License — feel free to fork and expand responsibly. This repo contains only caption metadata and does not redistribute any original images.

---

## 📘 About This Project

This tool was developed as part of the **AI Product Management Capstone** through Elvtr (2025).  
The capstone focused on building responsible, user-focused AI products using real-world workflows.  
This project applies agentic reasoning, RAG prompting, and civic tech use cases to demonstrate both product strategy and technical orchestration.
