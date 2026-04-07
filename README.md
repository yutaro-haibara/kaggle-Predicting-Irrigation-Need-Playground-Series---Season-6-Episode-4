# kaggle-Predicting-Irrigation-Need-Playground-Series---Season-6-Episode-4
# 1.プロジェクト概要
    KaggleのPlaygroundコンペティション「Predicting Irrigation Need」において、土壌の状     態、気象データ、作物の種類などの特徴量から、灌漑の必要性（Irrigation Need: Low, Medium,    High）を予測する多クラス分類モデルを構築。
# 2.使用データ
　データソース:Kaggle Playground Series S6E4
  特徴量:
    土壌データ：'Soil_Type', 'Soil_pH', 'Soil_Moisture', 'Organic_Carbon',
               'Electrical_Conductivity'
    気象データ：'Temperature_C', 'Humidity', 'Rainfall_mm',
               'Sunlight_Hours', 'Wind_Speed_kmh'
    耕作データ：'Crop_Type', 'Crop_Growth_Stage',
       　　　　 'Season', 'Irrigation_Type', 'Water_Source', 'Field_Area_hectare',
    　　　 　　 'Mulching_Used', 'Previous_Irrigation_mm', 'Region'
    その他：'id'
       
  ターゲット:'Irrigation_Need'

# 3.手法
 特徴量エンジニアリング
 - Kaggle Discussionの活用: 議論（Discussion）で共有されたドメイン知識に基づき、水分需    給スコア（'high_score', 'low_score'）などの新しい特徴量を生成しました。
 - カテゴリ変数の処理: CatBoost等で扱えるようにカテゴリカル変数を定義しています。

 学習モデル
- Main Model: 'CatBoostClassifier' を使用。
- 検証戦略: Stratified K-Foldなどの交差検証（CV）を用いた精度評価。

# 4. 開発環境
- プラットフォーム: Google Colaboratory / Kaggle Notebook
- 主なライブラリ: 
  - 'pandas', 'numpy' (データ処理)
  - 'catboost' (モデル学習)
  - 'sklearn' (評価・検証)
  - 'kagglehub' (データ取得)

# 5. 実行手順
1. 'kagglehub' を使用してデータをダウンロードします。
2. ノートブック内の各セルを順に実行し、前処理から学習、予測までを行います。
3. 生成された 'submission.csv' をKaggleに提出します。
