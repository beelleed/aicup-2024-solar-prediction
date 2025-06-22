# ☀️ AICUP 2024 太陽能發電預測 | Solar Power Forecasting (AICUP 2024)

## 📌 專案簡介 | Project Overview

本專案為 AICUP 2024（由行政院科技會報辦公室與趨勢科技主辦）太陽能發電預測競賽之**完整實作**，  
涵蓋資料處理、特徵工程、模型訓練（含隨機森林）、推論預測與結果輸出，適用於學術展示與模型說明。

This repository provides a **complete solution** for the [AICUP 2024 Solar Power Forecasting Challenge](https://tbrain.trendmicro.com.tw/Competitions/Details/36), organized by Trend Micro and T-Brain.  
It includes preprocessing, feature engineering, **training with Random Forest**, inference, and result generation.

---

## 🧠 問題描述 | Task Description

預測未來時間與地點的太陽能發電功率。  
Predict solar power generation (`Power(mW)`) based on timestamp and location information.

---

## 🛠️ 使用技術 | Technologies Used

- Python (pandas, numpy, matplotlib, seaborn)
- Scikit-learn (RandomForestRegressor)
- Google Colab / Jupyter Notebook
- 時間序列特徵工程、模型儲存與讀取、月份分群預測流程

---

## 🚀 專案流程 | Pipeline

### 📍 1. 資料解析與特徵建構 | Data Parsing & Feature Engineering

- 將比賽提供的序號轉為時間與地點
- 建立 sin/cos 時間週期性特徵（如 sin_hour、cos_month）

### 🌤️ 2. 天氣特徵模型訓練與推論 | Weather Feature Modeling (Random Forest)

- 每月分群訓練隨機森林模型
- 預測風速、氣壓、溫度、濕度、光照度等特徵

### 🔋 3. 發電功率模型訓練與推論 | Power Output Modeling (Random Forest)

- 使用預測天氣特徵，訓練每月發電模型
- 進行 minute-level 發電功率推論

### 📦 4. 彙整與輸出 | Aggregation & Submission

- 每 10 分鐘及地點平均預測結果
- 匯出符合競賽上傳格式的 CSV 檔案

---

## 📊 報告成果摘要 | Summary from Final Report

本專案基於 AICUP 2024 提交之報告，詳細記錄資料修正策略與模型實驗流程：

- 處理風速感測器異常與光照值超出最大上限問題  
- 透過回歸模型補足異常感測值  
- 採用多模型比較：Random Forest、LSTM、XGBoost、Linear Regression  
- 建立月份分群模型以提升預測精準度  
- 模型評估以 MAE 為指標，最終使用 RF 模型為主  
- 比賽總成績：第 **33 名 / 934 組**

本專案即為該流程的精簡重製版本，去除敏感輸出後公開於 GitHub。

---

## 🧷 安全聲明 | Data & Submission Safety

- ✅ 未公開任何測試資料或實際答案
- ✅ 未輸出任何模型評估指標（如 MAE、R²）
- ✅ 可公開於履歷、GitHub、報告展示等

No test labels or private data are included. All metrics and outputs are safe for public release.

---

## 🔧 執行環境建議 | Environment

- Python ≥ 3.8
- 建議使用 Google Colab 或 Jupyter Notebook
- 必要套件：
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## 👤 作者 | Authors
本專案由三位隊員合作完成，參與 AICUP 2024 太陽能發電預測挑戰，最終於 934 支參賽隊伍中獲得第 33 名。

This project was developed collaboratively by a 3-member team for the AICUP 2024 competition.
We achieved 33rd place out of 934 teams in the final leaderboard.