# Kaggle "Predicting Road Accident Risk" 

## 1. 概要 (Overview)

このリポジトリは、Kaggleコンペティション「[Predicting Road Accident Risk](https://www.kaggle.com/competitions/playground-series-s5e10/overview)」
での分析コードです。

---

## 2.参考文献と謝辞（References & Special Thanks）

このプロジェクトのコードは、以下の素晴らしいKaggle Notebookを参考にしています。オリジナルの作者に心から感謝いたします。

* **Kaggle Notebook:** [[0.05567] Road Accident Risk Prediction|Baseline](https://www.kaggle.com/code/darkdevil18/0-05567-road-accident-risk-prediction-baseline#%F0%9F%8F%97%EF%B8%8F-Model-Building)
* **Author:** [Dibya S. Barik](https://www.kaggle.com/darkdevil18)
    * *EDAの方法について参考にさせていただきました。*

* **Kaggle Notebook:** [Accident Risk Prediction hStacking - [0.0555]]
  (https://www.kaggle.com/code/mridul990601/accident-risk-prediction-hstacking-0-0555)
* **Author:**[Mridul_990601](https://www.kaggle.com/mridul990601)
    * *特徴量エンジニアリングについて参考にさせていただきました*
---

## 3. このプロジェクトの目的 (Purpose of this Project)

* 実践的な特徴量エンジニアリング・EDAの手法を学ぶため。
* 勾配ブースティングモデル（LightGBM, XGBoost）の使い方を理解するため。
* 分析の一連の流れを理解するため。

---

## 4. 学びと考察 (Key Learnings & Insights)

このコンペティション通じて、特に以下の点について深い学びがありました。

### 4.1. EDAの方法
単一の説明変数についてのみならず、二変量解析・多変量解析についての手法とそれによって得られる情報の取り扱い方について理解することができました。また、これを次に書く特徴量エンジニアリングへのつなげ方についても学習することができました。

### 4.2. データ整形と特徴量エンジニアリング
エンコーディングの種類とその選択の方法、EDAから仮説を立てることができることについての特徴量エンジニアリングについて理解することができました。

### 4.3. モデルのアンサンブル
複数のモデルの結果に対してアンサンブルすることで精度が向上するということを理解することができました。

---

## 5.　データセット

今回のcompetitionのデータセットは以下のリンクより入手可能です。
[Dataset](https://www.kaggle.com/competitions/playground-series-s5e10/data)

---

## 7. 技術スタック (Tech Stack)

* **Language:** Python 3
* **Libraries:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, LightGBM, XGBoost
