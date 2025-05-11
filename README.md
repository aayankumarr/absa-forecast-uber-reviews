# Aspect-Based Sentiment Forecasting on Uber Reviews 🚗📈

This repository presents an end-to-end pipeline for performing **Aspect-Based Sentiment Analysis (ABSA)** followed by **time-series forecasting** of sentiment trends using deep learning. The project focuses on Uber reviews and aims to provide actionable insight into how user sentiment evolves over time for various service aspects like `driver`, `app`, `service`, etc.

---

## 📌 Project Highlights

-  **Aspect Extraction** using BERT-Tagger and Contrastive Attention
-  **Sentiment Classification** using fine-tuned RoBERTa (aspect + sentence)
-  **Sentiment Index Computation** (positive - negative score)
-  **Time-Series Forecasting** using LSTM for each aspect
-  **Evaluation Metrics**: MSE, MAE, RMSE, R²
-  **Clean Visualizations** of predictions, loss curves, and flowcharts

---


---

## ⚙️ Workflow

### 1. **Aspect Extraction**
- Performed and compared  3 techniques:
  - BERT-based BIO tagging model
  - Contrastive Attention (RBF kernel-based scoring)
  - POS-Tagging based

### 2. **Aspect-Based Sentiment Classification**
- Input: `[CLS] aspect [SEP] review [SEP]`
- Model: `RobertaForSequenceClassification`
- Output: Sentiment label (`positive`, `neutral`, `negative`) and confidence scores

### 3. **Sentiment Index Calculation**
- `Sentiment Index = positive_score - negative_score`
- Aspect-wise, date-wise aggregation to form time series

### 4. **Forecasting Using LSTM,GRU AND RNN. COMPARED WITH SOTA TCN**
- Forecasts future sentiment index values per aspect

### 5. **Evaluation & Visualization**
- Metrics: MSE, MAE, RMSE, R²
- Plots: Actual vs Predicted curves, Loss curves, Architecture Flowchart

---

## 📊 Example Output

| Aspect | Date       | Actual Sentiment Index | Forecasted Index |
|--------|------------|------------------------|------------------|
| driver | 2024-12-01 | 0.65                   | 0.62             |
| app    | 2024-12-01 | -0.45                  | -0.40            |

---

## 📁 Requirements

```bash
pip install -r requirements.txt


