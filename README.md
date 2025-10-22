# janscan_ele_cxldkwauh098_v01
# JANコードスキャナー 📱

スマートフォンで使えるJANコード（バーコード）読み取りツールです。

## 機能

✅ スマホカメラでJANコードをスキャン  
✅ 手動入力での検索  
✅ GitHubのCSVファイルと連携  
✅ 新規JANコード・型番の一括登録（最大10件同時）  
✅ レスポンシブデザイン

## セットアップ手順

### 1. GitHubリポジトリの作成

1. GitHubにログイン
2. 新しいリポジトリを作成
3. リポジトリ名を決める（例: `jan-code-database`）
4. Public または Private を選択
5. 「Create repository」をクリック

### 2. ファイルのアップロード

以下の2つのファイルをリポジトリにアップロード：

- `jan-scanner.html` - メインのアプリケーション
- `jan-codes.csv` - JANコードと型番のデータベース

**方法1: Webインターフェース**
- リポジトリページで「Add file」→「Upload files」
- ファイルをドラッグ&ドロップ
- 「Commit changes」をクリック

**方法2: Git コマンド**
```bash
git clone https://github.com/あなたのユーザー名/jan-code-database.git
cd jan-code-database
# jan-scanner.html と jan-codes.csv をコピー
git add .
git commit -m "Initial commit"
git push
```

### 3. GitHub Personal Access Token の作成

1. GitHub設定ページへ: https://github.com/settings/tokens
2. 「Generate new token」→「Generate new token (classic)」
3. Note: 「JAN Scanner」など、わかりやすい名前を入力
4. Expiration: トークンの有効期限を設定
5. Select scopes: **`repo`** にチェック（全ての repo 権限）
6. 「Generate token」をクリック
7. **表示されたトークンをコピー**（後で見られません！）

### 4. GitHub Pages の有効化（オプション）

HTMLファイルをウェブで公開したい場合：

1. リポジトリの「Settings」タブ
2. 左メニューから「Pages」
3. Source: 「Deploy from a branch」
4. Branch: 「main」を選択
5. 「Save」をクリック
6. 数分後、`https://あなたのユーザー名.github.io/jan-code-database/jan-scanner.html` でアクセス可能

### 5. アプリの設定

1. `jan-scanner.html` をブラウザで開く
2. 「⚙️ GitHub設定」ボタンをクリック
3. 以下を入力：
   - **GitHubユーザー名**: あなたのGitHubユーザー名
   - **リポジトリ名**: 作成したリポジトリ名（例: `jan-code-database`）
   - **CSVファイルパス**: `jan-codes.csv`
   - **Personal Access Token**: 手順3で作成したトークン
4. 「保存」をクリック

## 使い方

### スキャン機能

1. 「スキャン」タブを選択
2. 「📷 カメラを起動」ボタンをクリック
3. カメラが起動したら、JANコードをスキャン
4. 自動的に型番が表示されます

**手動検索**
- JANコードを直接入力して「検索」ボタンをクリック

### 登録機能

1. 「登録」タブを選択
2. JANコードと型番を入力（最大10件）
3. 行を追加したい場合は「➕ 行を追加」をクリック
4. 「💾 一括登録」をクリック
5. GitHubのCSVファイルに自動的に追加されます

## CSVファイルの形式

```csv
jan_code,model_number
4901234567890,ABC-001
4902345678901,XYZ-100
```

- 1行目: ヘッダー（必須）
- 2行目以降: JANコード,型番

## 動作環境

- **スマートフォン**: iOS Safari, Android Chrome
- **PC**: Chrome, Firefox, Edge, Safari
- **カメラアクセス**: HTTPS接続が必要（GitHub Pagesは自動的にHTTPS）

## トラブルシューティング

### カメラが起動しない
- HTTPSで接続していることを確認
- ブラウザのカメラ権限を許可
- GitHub Pagesを使用するとHTTPS接続が保証されます

### データが読み込めない
- GitHub設定が正しいか確認
- Personal Access Tokenの権限が`repo`になっているか確認
- CSVファイルがリポジトリに存在するか確認

### 登録ができない
- Personal Access Tokenの有効期限が切れていないか確認
- リポジトリへの書き込み権限があるか確認

## セキュリティ注意事項

⚠️ **Personal Access Tokenは重要な情報です**
- 他人に共有しないでください
- ブラウザのローカルストレージに保存されます
- 定期的にトークンを更新することをおすすめします

## ライセンス

MIT License

## 作成者

Created with Claude AI
