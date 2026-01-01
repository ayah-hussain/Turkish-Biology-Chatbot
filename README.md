# Turkish-Biology-Chatbot
A Turkish biology assistant to support high school students in their studies.
# 🧬 BiyoTutor-TR: Turkish Biology Chatbot

![License](https://img.shields.io/badge/license-MIT-blue)
![Python](https://img.shields.io/badge/python-3.9%2B-blue)
![Model](https://img.shields.io/badge/Model-1.5B_Parameters-green)

**BiyoTutor-TR** is a specialized conversational AI designed to act as a biology tutor for Turkish-speaking students. It provides accurate, context-aware explanations for biological concepts, ranging from cell biology to genetics and ecology.

This project involves fine-tuning a small language model (SLM) to enhance its domain-specific knowledge in biology while maintaining fluency in Turkish.

---

## 🚀 Features

* **Domain Expertise:** Specialized knowledge in biology (9th-12th grade curriculum focus).
* **Turkish Native:** Fine-tuned specifically for Turkish syntax and scientific terminology.
* **Interactive Tutoring:** Capable of answering questions, explaining complex processes (e.g., Photosynthesis, Mitosis), and providing quizzes.
* **Efficient:** Built on a lightweight 1.5B parameter model, optimized for inference on consumer hardware.

## 🛠️ Tech Stack

* **Language:** Python
* **Base Model:** [Insert Model Name, e.g., Qwen-1.5B-Chat / Gemma-2B]
* **Libraries:** `transformers`, `peft`, `bitsandbytes`, `torch`
* **Fine-Tuning:** LoRA (Low-Rank Adaptation) for parameter-efficient training.
* **Interface:** [e.g., Gradio / Streamlit] for the chat UI.

---

## 📂 Dataset

The model was fine-tuned on a curated dataset consisting of:
1.  **Turkish Biology Textbooks:** High-quality OCR and processed text.
2.  **Q&A Pairs:** Synthetic and real-world biology questions/answers in Turkish.
3.  **Instruction Tuning Data:** Formatted as `User: ... Assistant: ...`.

*(Note: If your dataset is public, link it here. If private, describe the size/source briefly.)*

---

## ⚙️ Installation

To run this project locally, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/biyotutor-tr.git](https://github.com/yourusername/biyotutor-tr.git)
    cd biyotutor-tr
    ```

2.  **Create a virtual environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

---

## 🧠 Model Training & Fine-Tuning

We utilized **LoRA** to fine-tune the model efficiently. Below are the key hyperparameters used during training:

| Parameter | Value |
| :--- | :--- |
| **Rank (r)** | 8 / 16 |
| **Alpha** | 16 / 32 |
| **Learning Rate** | 2e-4 |
| **Batch Size** | 4 |
| **Epochs** | 3 |
| **Quantization** | 4-bit (QLoRA) |

To reproduce the training:
```bash
python train.py --config configs/lora_config.yaml
