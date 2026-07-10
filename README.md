# peft-lora-t5-formality-transfer
# 🚀 Parameter-Efficient Fine-Tuning of T5 using LoRA for Text Formality Transfer

<p align="center">

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-2.x-red?logo=pytorch)
![Transformers](https://img.shields.io/badge/HuggingFace-Transformers-yellow?logo=huggingface)
![PEFT](https://img.shields.io/badge/PEFT-LoRA-green)
![Google Colab](https://img.shields.io/badge/Platform-Google%20Colab-orange?logo=googlecolab)
![Status](https://img.shields.io/badge/Status-Completed-success)

</p>

---

## 📌 Overview

This project demonstrates **Parameter-Efficient Fine-Tuning (PEFT)** of **Google's T5-Base** model using **LoRA (Low-Rank Adaptation)** for the task of **Text Formality Transfer**.

Instead of fine-tuning all 220M+ parameters of T5, this project trains lightweight LoRA adapters, significantly reducing computational requirements while maintaining strong performance.

The resulting model transforms informal text into grammatically correct and professional language, making it suitable for applications such as:

- Email rewriting
- Professional communication
- Chatbot response refinement
- Writing assistants
- Text normalization

The trained LoRA adapter has been published on Hugging Face for easy inference and reuse.

---

# 🎯 Problem Statement

Informal text is widely used across chats, social media, and messaging platforms.

Examples include:

```
can u send it asap
```

or

```
thanks bro
```

Such text is unsuitable for professional communication.

This project fine-tunes a language model capable of automatically converting informal English into formal English while preserving the original meaning.

---

# ✨ Features

- Fine-tuned Google's T5-Base model
- Parameter-Efficient Fine-Tuning (PEFT)
- LoRA adapters
- Hugging Face Transformers
- PyTorch training pipeline
- Google Colab compatible
- Published on Hugging Face Hub
- Reproducible training workflow

---

# 🏗 Model Architecture

```
                Dataset
                   │
                   ▼
            Text Tokenization
                   │
                   ▼
          Google T5-Base Model
                   │
        LoRA Adapter Injection
                   │
                   ▼
            Fine-Tuning Process
                   │
                   ▼
        Trained LoRA Adapter
                   │
                   ▼
      Formal Text Generation
```

---

# 🛠 Tech Stack

| Category | Technology |
|-----------|------------|
| Language | Python |
| Framework | PyTorch |
| Transformers | Hugging Face Transformers |
| PEFT | LoRA |
| Dataset | Hugging Face Datasets |
| Evaluation | BLEU, ROUGE, BERTScore |
| Notebook | Google Colab |
| Model Hosting | Hugging Face Hub |

---

# 📂 Dataset

The project uses a **Text Formality Transfer** dataset containing paired examples of informal and formal sentences.

Example:

| Informal | Formal |
|----------|---------|
| can u help me | Could you help me? |
| thanks bro | Thank you. |
| send it asap | Please send it as soon as possible. |

The dataset was preprocessed using the Hugging Face Datasets library before training.

---

# ⚙ Training Configuration

| Parameter | Value |
|-----------|-------|
| Base Model | google-t5/t5-base |
| Fine-Tuning | PEFT |
| Method | LoRA |
| Framework | Hugging Face Transformers |
| Optimizer | AdamW |
| Training Platform | Google Colab |
| GPU | NVIDIA Tesla T4 |

---

# 📈 Evaluation Results

| Metric | Base Model | Fine-Tuned LoRA |
|---------|-----------:|---------------:|
| BLEU | **0.0795** | **0.3070** |
| ROUGE-1 | **0.3105** | **0.6203** |
| BERTScore F1 | **0.5613** | **0.7442** |

### Performance Improvement

✅ BLEU improved by **286%**

✅ ROUGE-1 doubled

✅ Significant improvement in semantic similarity

---

# 💬 Sample Predictions

### Example 1

Input

```
can u send it today
```

Prediction

```
Could you please send it today?
```

---

### Example 2

Input

```
thanks bro
```

Prediction

```
Thank you very much.
```

---

### Example 3

Input

```
i'll call u later
```

Prediction

```
I will call you later.
```

---

### Example 4

Input

```
lemme know
```

Prediction

```
Please let me know.
```

---

# 🚀 Installation

Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/peft-lora-t5-formality-transfer.git

cd peft-lora-t5-formality-transfer
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# 🧠 Running Inference

Example

```python
from transformers import AutoTokenizer, AutoModelForSeq2SeqLM
from peft import PeftModel

base_model = AutoModelForSeq2SeqLM.from_pretrained("google-t5/t5-base")

model = PeftModel.from_pretrained(
    base_model,
    "arinnnnn/peft_lora_t5_base_v1_final"
)

tokenizer = AutoTokenizer.from_pretrained("google-t5/t5-base")

text = "can u help me"

inputs = tokenizer(text, return_tensors="pt")

outputs = model.generate(**inputs)

print(tokenizer.decode(outputs[0], skip_special_tokens=True))
```

---

# 🤗 Hugging Face Model

**Model Repository**

https://huggingface.co/arinnnnn/peft_lora_t5_base_v1_final

---

# 📒 Google Colab Notebook

https://colab.research.google.com/drive/1t70ecj8YqnhC2JenzOMjD6-YYmhUg_zr

---

# 📊 Applications

- Professional Email Generation
- AI Writing Assistants
- Chatbot Response Enhancement
- Grammar Correction
- Customer Support Automation
- Text Normalization
- NLP Research

---

# 🔮 Future Improvements

- QLoRA implementation
- FLAN-T5 fine-tuning
- Larger datasets
- Human evaluation
- Gradio web interface
- FastAPI deployment
- Quantized inference
- Docker deployment

---

# 📚 References

- Hugging Face Transformers
- Hugging Face PEFT
- LoRA: Low-Rank Adaptation of Large Language Models
- Google T5
- PyTorch

---

# 👨‍💻 Author

**Arin Shemeem**

B.Tech Electronics and Communication Engineering

CUSAT (Cochin University of Science and Technology)

AI • Machine Learning • NLP • Deep Learning

Hugging Face: https://huggingface.co/arinnnnn

---

# ⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub.

It helps others discover the project and motivates further improvements.

---
