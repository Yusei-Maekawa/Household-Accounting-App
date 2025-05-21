# 家計簿アプリ

このプロジェクトは、個人または複数人で家計簿を管理するためのアプリケーションです。支出・収入の記録、グラフ化、目標設定、レシート画像のアップロードなどの機能を提供します。モバイルアプリとしては、Flutterを使用してiOSとAndroid両方に対応したアプリを開発します。

## 技術スタック

### フロントエンド
- **HTML/CSS**: 基本的なマークアップとスタイリング
- **JavaScript (TypeScript)**: インタラクティブな要素を追加
    - フレームワーク: **React**

### バックエンド
- **Python**（フレームワーク: **Django**）
    - Django REST Framework (DRF) を使用してAPIを作成
    - PostgreSQLまたはMySQLを使用してデータベース管理

### モバイルアプリ
- **Flutter (Dart)**: クロスプラットフォーム開発
    - Flutterを使用してiOSとAndroid両方に対応

### データベース
- **PostgreSQL**（または **MySQL**）
    - リレーショナルデータベースで収支データを管理

### クラウドサービス
- **Firebase**: リアルタイムデータベースと認証機能
    - Firebase Authenticationでユーザー認証を管理
    - Firebase Storageを使ってレシート画像を保存

### 認証とユーザー管理
- **Firebase Authentication**: GoogleアカウントやFacebookアカウントでの認証機能を提供

## 機能一覧

- **月ごとの支出・収入の管理**
- **支出のグラフ化**
- **支払い方法の選択**
- **カレンダー形式での表示**
- **レシートを撮って追加する方法 (OCRを利用予定)**
- **個人利用と複数人（家族等）での共有**
- **多通貨対応**
- **月ごとの目標設定**
- **税金、保険料などの計算**
- **複数デバイスで同期してデータを扱える**
- **アプリのデプロイ**
    - **Firebase**: モバイルアプリの認証とリアルタイムデータベース　

## 開発スケジュール

### 1. 準備と設計 
- 要件定義
- システム設計とデザイン作成

### 2. フロントエンド開発 (React) 
- ユーザーインターフェース(UI)の作成
- Reactを使用してページ遷移やインタラクティブな要素を実装

### 3. バックエンド開発 (Django) 
- API設計と実装
- ユーザー認証機能、データベース設計
- Django REST FrameworkでAPI作成

### 4. モバイルアプリ開発 (Flutter) 
- アプリのUI作成
- バックエンドAPIとの連携
- データ同期、レシートアップロード機能の実装

### 5. 統合とテスト 
- バグ修正
- システムテスト、デバッグ



## 必要なツール

- **フロントエンド開発**:
    - Visual Studio Code (VSCode)
    - Node.js (ReactやTypeScriptを使用するため)
    - npm/yarn (依存関係の管理)

- **バックエンド開発**:
    - Python 3.x
    - Django
    - PostgreSQL または MySQL

- **モバイルアプリ開発**:
    - Flutter SDK
    - Android Studio または VSCode
    - Xcode (iOS開発の場合)

## 開発リソース

- **React公式ドキュメント**: https://reactjs.org/
- **Django公式ドキュメント**: https://www.djangoproject.com/
- **Flutter公式ドキュメント**: https://flutter.dev/
- **Firebase公式ドキュメント**: https://firebase.google.com/docs
- **PostgreSQL公式ドキュメント**: https://www.postgresql.org/docs/

## コントリビューション

このプロジェクトへの貢献を歓迎します！バグの修正、機能の追加、改善提案などがあれば、プルリクエストを送ってください。

---

