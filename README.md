# Fine-Tuning Open-Weight LLMs with Unsloth (Full Cycle)

This project demonstrates **end-to-end fine-tuning, continued pretraining, reward modeling, and model deployment** workflows using [Unsloth](https://github.com/unslothai/unsloth).

We use open-weight models like **Phi-2** to complete a full training-to-deployment pipeline.

---

## 🚀 Project Overview

| Part | Description | Colab Link |
|-----|-------------|------------|
| a) Fine-Tuning | Fine-tune `microsoft/phi-2` on custom tasks (chat, summarization). | [Colab Notebook](https://colab.research.google.com/drive/1eekXJ8RgiYkOg_o1CmnpxJmdW81TG4Sw?usp=sharing) |
| b) Continued Pretraining | Pretrain further on synthetic made-up language examples. | [Colab Notebook](https://colab.research.google.com/drive/1KECKZFLTqQAqPnZN-JMflhjKc5GBZ18z?usp=sharing) |
| c) Chat Templates | Fine-tune on classification, conversation, and long-context tasks. | [Colab Notebook](https://colab.research.google.com/drive/1NU9wiNmIOkGt1HCazJUBEgaX7Rk_QjLB?usp=sharing) |
| d) Reward Modeling | Explained DPO and ORPO concepts (with fine-tuning plan). | [Colab Notebook](https://colab.research.google.com/drive/1S7pUkRCoYuxXnrl1d0VedIeDulxgnVzP?usp=sharing) |
| e) Continued Fine-Tuning from Checkpoint | Demonstrated training resumption after checkpoints. | [Colab Notebook](https://colab.research.google.com/drive/15CdcxZbIACalNsuc0S8q_MAZyP_8cSdS?usp=sharing) |
| f) Mental Health Chatbot Fine-Tuning | Fine-tuned Phi-2 to respond empathetically for mental health conversations. | [Colab Notebook (f+g)](https://colab.research.google.com/drive/1s0Pf5HdFyVgKawxVn8xnObxb-N0SsSIe?usp=sharing) |
| g) Model Export and Inference | Saved fine-tuned model, attempted inference, explained large model constraints. | [Colab Notebook (f+g)](https://colab.research.google.com/drive/1s0Pf5HdFyVgKawxVn8xnObxb-N0SsSIe?usp=sharing) |

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

- Unsloth
- Hugging Face Transformers
- Datasets (Yahma Alpaca, Anthropic hh-rlhf)
- Python 3.11
- Google Colab / Local CPU

---

## 🧠 Key Learnings

- Efficient fine-tuning with LoRA.
- Dataset preparation for various NLP tasks.
- Checkpoint saving, loading, and resuming.
- Reward modeling (conceptual explanation).
- Handling model size limitations for deployment.

---

## 📜 Important Notes

- Phi-2 (~2.7B parameters) is a relatively large model.  
  Local inference on low-resource machines (e.g., MacBook CPU) requires heavy model offloading or use of smaller models.
- Full training-to-inference workflow demonstrated successfully using cloud/Colab.

---

## 📬 Contact

For any questions regarding this project:
- GitHub Issues
- [Unsloth Discord](https://discord.gg/unsloth)
