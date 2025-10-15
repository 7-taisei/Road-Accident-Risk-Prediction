# Kaggle "House Prices" 上位解法コードの学習・写経リポジトリ

## 1. 概要 (Overview)

このリポジトリは、Kaggleコンペティション「[Predicting Road Accident Risk](https://www.kaggle.com/competitions/playground-series-s5e10/overview)」の上位入賞者の解法を学習し、理解を深めるために写経したものです。

**これは私のオリジナルの成果物ではなく、学習目的のプロジェクトです。**

---

## 2. 出典 (Original Source & Credit)

このプロジェクトのコードは、以下の素晴らしいKaggle Notebookを参考にしています。オリジナルの作者に心から感謝いたします。

* **Kaggle Notebook:** [[0.05567] Road Accident Risk Prediction|Baseline](https://www.kaggle.com/code/darkdevil18/0-05567-road-accident-risk-prediction-baseline#%F0%9F%8F%97%EF%B8%8F-Model-Building)
* **Author:** [Dibya S. Barik](https://www.kaggle.com/darkdevil18)

---

## 3. このプロジェクトの目的 (Purpose of this Project)

* Kaggle上位者の実践的な特徴量エンジニアリングの手法を学ぶため。
* 勾配ブースティングモデル（LightGBM, XGBoost）の高度な使い方とチューニング方法を理解するため。
* 体系化された分析パイプライン（データ前処理 → モデリング → 評価）の構築方法をトレースするため。

---

## 4. 学びと考察 (Key Learnings & Insights)

この写経を通じて、特に以下の点について深い学びがありました。

### 4.1. 巧みな欠損値処理
単純に平均値や中央値で補完するのではなく、`GarageQual`（ガレージの品質）のような関連性の高い特徴量を用いて、`GarageYrBlt`（ガレージの築年数）の欠損値を補完するアプローチは非常に参考になりました。データの文脈を理解した上で処理することの重要性を学びました。

### 4.2. 目的変数と特徴量の対数変換
目的変数である`SalePrice`（住宅価格）の分布が歪んでいるため、対数変換（`np.log1p`）を適用していました。これにより、モデルが残差の正規性を仮定しやすくなり、予測精度が向上することを確認しました。一部の歪んだ数値特徴量にも同様の変換を適用するテクニックは、今後の自分の分析にも活かしたいです。

### 4.3. モデルのアンサンブル
単一の最強モデルを作るのではなく、特性の異なる複数のモデル（例: LightGBM, XGBoost, Ridge）の結果を組み合わせる「アンサンブル学習」が、最終的なスコア向上に大きく寄与していました。各モデルの予測値に重みをつけて加重平均を取る手法は、堅牢な予測モデルを構築する上で非常に有効だと理解しました。

---

## 5. （オプション）自分で行った追加実験 (My Own Experiments)

オリジナルのコードをベースに、理解を深めるために以下の追加実験を行いました。

* **追加の可視化:** `SalePrice`と各特徴量の相関をより詳しく見るために、ヒートマップだけでなく、特に相関の高かった上位10個の特徴量との散布図を作成しました。
* **別のモデルの試行:** オリジナルでは使用されていなかったCatBoostモデルを同じ前処理パイプラインに適用し、LightGBMとの性能比較を行いました。

---

## 6. 技術スタック (Tech Stack)

* **Language:** Python 3
* **Libraries:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, LightGBM, XGBoost
