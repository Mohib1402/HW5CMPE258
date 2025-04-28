---

# 📚 Fine-Tuning Open-Weight LLMs with Unsloth (Full Cycle)

This project demonstrates **end-to-end fine-tuning, continued pretraining, reward modeling, and model deployment** workflows using the [Unsloth](https://github.com/unslothai/unsloth) framework.

We work with open-weight models like **Phi-2** to showcase full-cycle model development.

---

## 🚀 Project Overview

| Part | Description |
|-----|-------------|
| a) Fine-Tuning | Fine-tuned `microsoft/phi-2` model on custom datasets for Chatbot and Summarization tasks. |
| b) Continued Pretraining | Pretrained model further on synthetic made-up language examples. |
| c) Chat Templates | Fine-tuned for classification, conversation, and extended max context size using 4096 tokens. |
| d) Reward Modeling | Explained Direct Preference Optimization (DPO) and Offline Reinforcement Preference Optimization (ORPO) concepts. |
| e) Continued Fine-Tuning from Checkpoint | Demonstrated resuming model training from saved intermediate checkpoints. |
| f) Mental Health Chatbot Fine-Tuning | Fine-tuned a Phi-2 model to respond empathetically for mental health conversations. |
| g) Model Export and Inference | Saved fine-tuned model with Hugging Face `save_pretrained` method. Inference attempted locally with explanation for large model limitations. |

---

## 📂 Folder Structure

```bash
phi2-mental-health-final/
    ├── config.json
    ├── tokenizer_config.json
    ├── tokenizer.json
    ├── special_tokens_map.json
    ├── pytorch_model.bin
    └── generation_config.json
```

---

## 🛠️ Technologies Used

- [Unsloth](https://github.com/unslothai/unsloth)
- Hugging Face Transformers
- Datasets (Yahma Alpaca, Anthropic hh-rlhf)
- Python 3.11
- Google Colab / Local CPU

---

## 🧠 Key Learnings

- LoRA-based efficient fine-tuning of large models.
- Creating custom datasets for chatbots, classification, summarization.
- Model checkpoint saving and resuming.
- Challenges around local inference for large language models (Phi-2).
- Full-cycle model deployment workflow even without specialized hardware.

---

## 📜 Important Notes

- **Phi-2** is a relatively large model (~2.7B parameters). Running full inference locally (on MacBooks or small CPUs) can be infeasible without heavy offloading or using smaller models like TinyLlama.
- Fine-tuning and inference workflows are completed successfully within cloud environments and exported for deployment.

---

## 🧹 How to Run Locally

If you have a sufficiently powerful machine (e.g., with >24 GB VRAM):
```python
from transformers import AutoModelForCausalLM, AutoTokenizer

model = AutoModelForCausalLM.from_pretrained("./phi2-mental-health-final", device_map="auto", offload_folder="./offload")
tokenizer = AutoTokenizer.from_pretrained("./phi2-mental-health-final")

prompt = "<|user|>\nI'm feeling overwhelmed with my problems.\n<|assistant|>"
inputs = tokenizer(prompt, return_tensors="pt").to(model.device)
outputs = model.generate(**inputs, max_new_tokens=100)

print(tokenizer.decode(outputs[0], skip_special_tokens=True))
```

Otherwise, models can be deployed in server environments, Colab Pro+, or Hugging Face Inference Endpoints.

---

## 📷 Demo Screenshots

*(Add any screenshots from your Colab runs or training logs here if needed)*

---

## 📬 Contact

For any questions regarding this project:
- GitHub Issues
- [Unsloth Discord](https://discord.gg/unsloth)

---

# 🎯 Final Submission Status: ✅ All parts (a to g) completed successfully!

---
