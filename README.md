# Fine-Tunning
# 🤖 Customer Complaint Classifier

A fine-tuned DistilBERT model that automatically categorizes customer complaints into Billing, Technical, and Shipping categories.

---

## 📊 Results

| Training Examples | Accuracy |
|---|---|
| 24 examples | 60% |
| Expanded dataset | 93.33% |

### Real Predictions
```
"I was charged twice please refund" → Billing  (99.82%)
"My app keeps crashing"             → Technical (99.80%)
"My package has not arrived"        → Shipping  (87.25%)
```

---

## 📁 Project Structure

```
complaint_classifier/
├── train.py                      ← training code
├── predict.py                    ← prediction code
├── complaint_classifier.pth      ← saved model weights
└── requirements.txt
```

---

## 🎯 What It Does

Automatically classifies customer complaints into 3 categories:

- 💳 **Billing** — payment issues, refunds, wrong charges
- 💻 **Technical** — app crashes, login issues, bugs
- 📦 **Shipping** — delivery delays, lost packages, wrong items

---

## 🧠 How It Works

```
Customer complaint text
        ↓
DistilBERT tokenizer
        ↓
Frozen DistilBERT base (pretrained knowledge)
        ↓
Custom classification head (trained on our data)
        ↓
Category + Confidence score
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| DistilBERT | Pretrained language model |
| HuggingFace Transformers | Model loading |
| PyTorch | Training loop |
| Feature Extraction | Fine-tuning technique |

---

## 📦 Installation

```bash
pip install torch transformers scikit-learn
```

---

## 🚀 How To Run

### Train Model
```bash
python train.py
```

### Predict
```bash
python predict.py
```

### Predict In Code
```python
from predict import predict

predict("I was charged twice please refund")
# Output: Billing (99.82%)

predict("App keeps crashing on my phone")
# Output: Technical (99.80%)

predict("My package has not arrived")
# Output: Shipping (87.25%)
```

---

## 🔑 Key Learnings

### 1. More Data > Everything
```
24 examples  → 60% accuracy
Expanded     → 93% accuracy

No architecture change
No hyperparameter tuning
Just more training examples
```

### 2. Feature Extraction
```
Froze all DistilBERT layers (66M parameters)
Trained only classification head
Perfect for small datasets
Prevents overfitting
```

### 3. Fine-Tuning vs Training From Scratch
```
From scratch → needs millions of examples
Fine-tuning  → works with hundreds of examples
DistilBERT already knows language
We just taught it our specific categories
```

---

## ⚠️ Limitations

- Trained on limited domain-specific data
- May struggle with ambiguous complaints
- Only handles English text
- 3 categories only

---

## 🔮 Future Improvements

- [ ] Add more complaint categories
- [ ] Expand training dataset
- [ ] Deploy as Streamlit web app
- [ ] Add Telegram bot integration
- [ ] Fine-tune entire model (unfreeze all layers)

---

## 👨‍💻 Author

Kanhaiya — Self-taught Deep Learning Engineer

GitHub: github.com/kanhaiya-ml

#DeepLearning #NLP #PyTorch #HuggingFace
