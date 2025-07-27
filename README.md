# 📝 Customer Support Ticket Classification

##  Objective
The goal of this project is to **automatically classify customer support tickets** into predefined categories based on their descriptions.  
This helps improve customer service efficiency by routing tickets to the correct department automatically.

---

## ⚙️ Methodology 

 **Data Preprocessing**
- Loaded and cleaned the dataset (`customer_support_tickets.csv`).
- Selected relevant columns: `Ticket ID`, `Ticket Description`, and `Ticket Type`.
- Dropped missing values.

 **Exploratory Step**
- Used a zero-shot classification model (`facebook/bart-large-mnli`) from Hugging Face Transformers to see how well an off-the-shelf model could predict ticket types without training.

 **Label Encoding & Splitting**
- Encoded ticket types as numeric labels using `LabelEncoder`.
- Split data into training (80%) and testing (20%) sets.

 **Model & Tokenization**
- Used the `bert-base-uncased` model for fine-tuning.
- Tokenized ticket descriptions with truncation and padding.

 **Training**
- Fine-tuned using Hugging Face `Trainer` API with:
  - Batch size: 8
  - Learning rate: 2e-5
  - Epochs: 3
  - Weight decay: 0.01

 **Evaluation**
- Evaluated model performance on the test set.
- Computed accuracy, precision, recall, and F1-score.

---

## 📊 Key Results / Observations
- Fine-tuned BERT model achieved **strong performance** in classifying support tickets into correct categories.
- The initial zero-shot approach provided reasonable predictions, showing the potential of pretrained language models even without fine-tuning.
- Fine-tuning further improved accuracy and F1-score on unseen data.

---

##  Tech Stack
- Python
- Pandas
- scikit-learn
- Hugging Face Transformers
- Hugging Face Datasets

---

## 📁 Dataset
- `customer_support_tickets.csv`

---

##  How to Run
1. Install dependencies:
   ```bash
   pip install pandas scikit-learn datasets transformers
