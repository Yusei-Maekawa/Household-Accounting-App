# 家計簿アプリ

このプロジェクトは、個人または家族で家計簿を管理するためのWebアプリケーションです。
支出・収入の記録、グラフ化、目標設定、レシート画像のOCR機能などを提供します。
PWA（Progressive Web App）対応により、モバイルでもネイティブアプリのような体験を提供します。

## 🏗️ システムアーキテクチャ

### **Django版（学習重視）**
- **フロントエンド**: React/Next.js PWA
- **バックエンド**: Django REST Framework
- **データベース**: PostgreSQL + Redis
- **インフラ**: Docker + Railway/Vercel

### **Firebase版（最新技術）**
- **フロントエンド**: React/Next.js PWA
- **バックエンド**: Firebase Services
- **データベース**: Cloud Firestore
- **インフラ**: Firebase Hosting

## 🛠️ 技術スタック

### フロントエンド
- **React 18**: UIライブラリ
- **Next.js 14**: フルスタックReactフレームワーク
- **TypeScript**: 型安全性
- **PWA**: オフライン対応・プッシュ通知
- **Chart.js**: グラフ表示
- **Material-UI (MUI)**: UIコンポーネント
- **Camera API**: レシート撮影機能

### バックエンド（Django版）
- **Python 3.11**: プログラミング言語
- **Django 4.2**: Webフレームワーク
- **Django REST Framework**: API作成
- **PostgreSQL**: メインデータベース
- **Redis**: キャッシュ・セッション管理
- **Celery**: 非同期タスク処理
- **Tesseract OCR**: レシート文字認識

### バックエンド（Firebase版）
- **Firebase Authentication**: ユーザー認証
- **Cloud Firestore**: NoSQLデータベース
- **Cloud Storage**: ファイルストレージ
- **Cloud Functions**: サーバーレス処理
- **Google Vision API**: 高精度OCR

### 開発・デプロイ環境
- **Docker**: コンテナ化
- **Docker Compose**: 開発環境構築
- **GitHub Actions**: CI/CD
- **Vercel**: フロントエンドホスティング
- **Railway**: バックエンドホスティング
- **Supabase**: PostgreSQL ホスティング

## 🚀 機能一覧

### 基本機能
- ✅ **ユーザー認証**: JWT/Firebase Auth
- ✅ **取引管理**: 収入・支出の記録・編集・削除
- ✅ **カテゴリ管理**: カスタムカテゴリ作成
- ✅ **予算管理**: 月次・年次予算設定
- ✅ **レポート機能**: 期間別・カテゴリ別集計

### 高度な機能
- ✅ **グラフ表示**: 円グラフ・棒グラフ・線グラフ
- ✅ **カレンダー表示**: 日別取引確認
- ✅ **OCRレシート読み取り**: 自動データ入力
- ✅ **家族共有**: 招待コードで家計簿共有
- ✅ **多通貨対応**: 複数通貨での管理
- ✅ **データエクスポート**: CSV・PDF出力

### PWA機能
- ✅ **オフライン対応**: ネットワーク不要で基本操作
- ✅ **プッシュ通知**: 予算アラート・定期通知
- ✅ **ホーム画面追加**: スマホアプリのような体験
- ✅ **レスポンシブデザイン**: 全デバイス対応

## 📦 開発環境構築

### 前提条件
```bash
# 必要なソフトウェア
- Docker Desktop
- Node.js 18+
- Python 3.11+
- Git
```

### Django版のセットアップ
```bash
# リポジトリクローン
git clone https://github.com/Yusei-Maekawa/Household-Accounting-App.git
cd Household-Accounting-App

# Docker環境起動
docker-compose up -d

# データベース初期化
docker-compose exec backend python manage.py migrate
docker-compose exec backend python manage.py createsuperuser

# フロントエンド起動
cd frontend
npm install
npm run dev

# アクセス
# フロントエンド: http://localhost:3000
# Django Admin: http://localhost:8000/admin
# API: http://localhost:8000/api/
```

### Firebase版のセットアップ
```bash
# Firebase CLI インストール
npm install -g firebase-tools

# Firebase ログイン
firebase login

# Firebase プロジェクト初期化
firebase init

# 環境変数設定
cp .env.example .env.local
# Firebase 設定情報を .env.local に記述

# 開発サーバー起動
npm run dev

# Firebase Emulator起動（ローカル開発）
firebase emulators:start
```

## 🏗️ プロジェクト構造

```
Household-Accounting-App/
├── 📁 architectureGraph/          # システム設計図
│   ├── transition.puml           # 画面遷移図
│   ├── er.puml                  # データベース設計図
│   ├── system_architecture.puml # システムアーキテクチャ
│   └── firebase_architecture.puml
├── 📁 django-version/            # Django版実装
│   ├── 📁 backend/               # Django API
│   │   ├── 📁 apps/
│   │   ├── 📁 config/
│   │   ├── requirements.txt
│   │   └── Dockerfile
│   ├── 📁 frontend/              # Next.js PWA
│   │   ├── 📁 src/
│   │   ├── 📁 public/
│   │   ├── package.json
│   │   └── next.config.js
│   └── docker-compose.yml
├── 📁 react-sample-app/          # 🆕 既存React環境
│   ├── 📁 src/                   # Reactソースコード
│   │   ├── 📁 components/        # 再利用可能コンポーネント
│   │   ├── 📁 pages/             # ページコンポーネント
│   │   ├── 📁 hooks/             # カスタムフック
│   │   ├── 📁 utils/             # ユーティリティ関数
│   │   ├── 📁 styles/            # スタイリング
│   │   ├── App.js                # メインアプリ
│   │   └── index.js              # エントリーポイント
│   ├── 📁 public/                # 静的ファイル
│   │   ├── index.html
│   │   ├── manifest.json         # PWA manifest
│   │   └── 📁 icons/             # PWAアイコン
│   ├── package.json              # 依存関係
│   ├── package-lock.json
│   └── README.md
├── 📁 firebase-version/          # Firebase版実装
│   ├── 📁 src/
│   ├── 📁 functions/
│   ├── firebase.json
│   └── package.json
├── 📁 docs/                      # ドキュメント
└── README.md
```

## 🎯 開発スケジュール

### Phase 1: 基盤構築（✅ 一部完了）
- [x] システム設計・アーキテクチャ設計
- [x] 画面遷移図・ER図作成
- [x] **React環境構築** (react-sample-app)
- [ ] Django プロジェクト初期化
- [ ] React→PWA対応実装
- [×] Docker 環境構築

### Phase 2: 既存環境活用・機能拡張
- [ ] **react-sample-app**をベースに家計簿UI実装
- [ ] PWA機能追加（Service Worker、Manifest）
- [ ] Django バックエンドAPI作成
- [ ] React-Django連携
- [ ] 基本CRUD機能実装

### Phase 3: 高度な機能
- [ ] グラフ表示機能（Chart.js追加）
- [ ] OCRレシート読み取り
- [ ] 家族共有機能
- [ ] 予算管理機能
- [ ] レポート機能

### Phase 4: Firebase版実装
- [ ] Firebase プロジェクト設定
- [ ] 既存React環境をFirebase対応
- [ ] リアルタイム同期機能
- [ ] Cloud Functions実装

### Phase 5: 本番デプロイ
- [ ] CI/CD パイプライン構築
- [ ] 本番環境デプロイ
- [ ] パフォーマンス最適化
- [ ] セキュリティテスト

## 🛠️ 必要なツール

### 開発環境
- **Docker Desktop**: コンテナ環境
- **Visual Studio Code**: コードエディタ
- **Git**: バージョン管理
- **Postman**: API テスト
- **PlantUML**: 設計図作成

### フロントエンド開発
- **Node.js 18+**: JavaScript ランタイム
- **npm/yarn**: パッケージマネージャー
- **React DevTools**: デバッグツール

### バックエンド開発
- **Python 3.11+**: プログラミング言語
- **pip**: パッケージマネージャー
- **PostgreSQL**: データベース
- **Redis**: インメモリDB

## 📚 学習リソース

### 公式ドキュメント
- [React公式ドキュメント](https://react.dev/)
- [Next.js公式ドキュメント](https://nextjs.org/docs)
- [Django公式ドキュメント](https://docs.djangoproject.com/)
- [Django REST Framework](https://www.django-rest-framework.org/)
- [Firebase公式ドキュメント](https://firebase.google.com/docs)
- [Docker公式ドキュメント](https://docs.docker.com/)

### 参考サイト
- [PWA開発ガイド](https://web.dev/progressive-web-apps/)
- [Material-UI](https://mui.com/)
- [Chart.js](https://www.chartjs.org/)

## 💰 コスト試算

### 開発環境
- **完全無料**: ローカル開発・学習

### 本番環境（個人利用）
- **Django版**: $0-5/月（Railway無料枠使用）
- **Firebase版**: $0/月（無料枠で十分）
- **独自ドメイン**: $12/年（オプション）

## 🤝 コントリビューション

プロジェクトへの貢献を歓迎します！

1. **Issue**: バグ報告・機能要望
2. **Pull Request**: コード改善・新機能追加
3. **Discussion**: 設計議論・質問

### 開発ルール
- **ブランチ戦略**: Git Flow
- **コミット**: Conventional Commits
- **コードレビュー**: 必須
- **テスト**: ユニットテスト・E2Eテスト

## 📄 ライセンス

MIT License

---

**🎯 このプロジェクトで学べること**
- フルスタック Web 開発
- モダンな技術スタック
- システム設計・アーキテクチャ
- Docker・CI/CD
- 最新のクラウド技術（Firebase）
- PWA開発

