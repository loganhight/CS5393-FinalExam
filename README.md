
# **CS 5393 - Advanced Python Final Exam**

# **Stock Price Prediction using RNNs**

- **Author**: Logan Hight
- **Date**: April 20, 2025

## **Overview**

This project implements and evaluates multiple **Recurrent Neural Network (RNN)** architectures for **daily stock price forecasting**, with a focus on comparing **LSTM**, **GRU**, and GRU variants enhanced with additional features and activation functions. The analysis includes modeling, performance evaluation, and statistical validation, followed by deployment recommendations suitable for real-world applications.

---

## **Project Structure**

```
CS5393-FinalExam/
│
├── graphs/                         # Visualized input data
│   └── AAPL_Closing_Price_2010-2023.png
│
├── models/                         # Model architecture visualizations
│   ├── GRU_ELU.png
│   ├── GRU_LeakyReLU.png
│   ├── GRU_Multi.png
│   ├── GRU_SELU.png
│   ├── GRU.png
│   ├── GRU_ReLU.png
│   ├── LSTM.png
│
├── performance_evaluations/       # Plots and visualizations of performance
│   ├── Absolute_Error_Distribution.png
│   ├── RMSE_MAE_Comparison.png
|   ├── Training_Prediction_Time_Comparison.png
│   ├── *_actual_vs_predicted.png
│
├── training_curves/               # Training loss/MAE per model
│   ├── LSTM_training.png
│   ├── GRU_training.png
│   ├── GRU_Multi_training.png
│   ├── GRU_ELU_training.png
│   ├── GRU_ReLU_training.png
│   ├── GRU_LeakyReLU_training.png
│   ├── GRU_SELU_training.png
│
├── presentation/                  # Class presentation PPTX
├── report/                        # Final report in PDF format
│
├── CS_5393_Final_Exam.ipynb       # Main project notebook
├── CS_5393_Final_Exam_Rendered.html
├── README.md
├── requirements.txt               # Required libraries                      
```

---

## **Problem Overview**

The objective is to build a stock price prediction system using deep learning, comparing:

1. LSTM baseline (close price only)
2. GRU baseline (close price only)
3. GRU with additional feature: Volume
4. GRU with modified activation functions:
   - ReLU
   - Leaky ReLU
   - ELU
   - SELU

Each model is evaluated quantitatively and statistically, using RMSE, MAE, Training Time, Prediction Time, and multiple significance tests.

---

## **Evaluation Metrics**

- **RMSE (Root Mean Squared Error):** Penalizes large errors more severely. Appropriate for high-risk environments like trading.
- **MAE (Mean Absolute Error):** Measures average dollar deviation. Useful for executive-level interpretability.
- **Training & Prediction Time:** Crucial for deployment feasibility. Lower runtime improves scalability and enables real-time or frequent model retraining in dynamic markets.
- **Boxplots & Prediction Plots:** Help visualize distributional differences and model responsiveness.
- **Statistical Tests:**
  - Paired t-tests  
  - Wilcoxon signed-rank tests  
  - One-way ANOVA

---

## **Installation and Setup**

1. Clone the repository or download the ZIP.

2. Set up your Python environment:

```bash
python -m venv venv
source venv/bin/activate        # or venv\Scripts\activate on Windows
pip install -r requirements.txt
```

3. Launch the notebook:

```bash
jupyter notebook CS_5393_Final_Exam.ipynb
```

---

## **Execution Instructions**

- Run all cells sequentially from top to bottom.
- The notebook includes:
  - Data loading and visualization
  - Preprocessing with MinMaxScaler
  - Model definition, training, and evaluation
  - Metrics aggregation and plotting
  - Statistical testing

> All output figures should be saved under `models/`, `training_curves/`, and `performance_evaluations/`.

---

## **Final Recommendation**

After extensive testing and evaluation:

- **GRU with ELU activation** is recommended for deployment due to its:
  - Low RMSE and MAE
  - Fast inference time
  - Stable training
  - Accurate price tracking
  - Superior statistical significance profile

This model is appropriate for production in business scenarios such as:

- Automated forecasting dashboards
- Trading signal engines
- Risk assessment tools
