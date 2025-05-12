# 📘 IndicTrans2 Fine-tuning for English to Indian Languages

## 🧠 Introduction

This project demonstrates how to fine-tune [AI4Bharat's IndicTrans2](https://github.com/AI4Bharat/IndicTrans2) multilingual translation model using **LoRA (Low-Rank Adaptation)** for efficient and parameter-light training. The goal is to enhance translation quality for **English to Telugu** and **English to Tamil**, leveraging a custom parallel corpus.

By employing LoRA, we can significantly reduce memory and compute requirements, making this project suitable for environments like Google Colab while maintaining high translation performance.

---

## 🚧 Challenges

- ⚙️ **Dependency Setup**: IndicTrans2 requires system-level installations and environment setup, which are complex in Colab notebooks.
- 🧩 **Low-Resource Hardware**: Training transformer models with limited computational power required optimization through LoRA.
- 📁 **Data Preparation**: Custom dataset formatting was needed to ensure compatibility with IndicTrans2 training scripts.
- ⏱️ **Training Optimization**: Achieving meaningful performance within 1000 steps while maintaining model stability.
- 📦 **Model Packaging**: Post-training steps like zipping and downloading the models were integrated for portability.

---

## ✅ Results

- Fine-tuned **IndicTrans2** models for:
  - English to **Telugu**
  - English to **Tamil**
- Used LoRA with:
  - Target Modules: `q_proj`, `k_proj`
  - Dropout: `0.1`
  - Rank `r`: `16`
  - Alpha: `32`
- Training Parameters:
  - Batch Size: `32`
  - Learning Rate: `2e-4`
  - Max Steps: `1000`
  - Optimizer: `adamw_torch`
- Output: Two zipped fine-tuned models (`fine_tuned_model_telugu.zip` and `fine_tuned_model_tamil.zip`), ready for inference or deployment.
- Improved model bleu score Here are images attached
- ![image](https://github.com/user-attachments/assets/37219021-3008-4df2-b1de-ff903d2de68e)


---

## 🏁 Conclusion

This project validates that **parameter-efficient tuning techniques** like **LoRA** can be effectively applied to large multilingual models for domain- or language-specific fine-tuning. The resulting models are lightweight, fast to train, and maintain a high-quality translation output.

Such methods are especially relevant for scaling NLP solutions in multilingual, resource-constrained settings such as education, public services, and rural accessibility.

---

## 🙏 Acknowledgment

- **AI4Bharat** for providing the base IndicTrans2 model and scripts.
- **Google Colab** for offering a free GPU-powered platform for training.
- **PEFT (Parameter-Efficient Fine-Tuning)** community for innovations like LoRA.
- **VIT-AP University** for academic and infrastructural support during the development of this project.

---

## 📂 Project Structure (Optional)

```
├── MainDataset/                  # Custom dataset used for training
├── IndicTrans2/                 # Cloned repository with huggingface_interface
│   └── huggingface_interface/
│       └── train_lora.py        # Training script
├── fine_tuned_model_telugu/     # Output model folder (Telugu)
├── fine_tuned_model_tamil/      # Output model folder (Tamil)
└── pdf_to_pdf.ipynb             # Notebook used for training and packaging
```

---

> ✨ Feel free to fork, improve, or reuse this fine-tuning pipeline for other Indian languages!

