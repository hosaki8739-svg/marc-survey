[README (1).md](https://github.com/user-attachments/files/28453187/README.1.md)
# marc-survey
MARCプログラム事前アンケート（GitHub Pages + GAS）

## セットアップ手順

### 1. GitHubリポジトリの作成
1. GitHubで新規リポジトリ `marc-survey` を作成
2. このファイル群をプッシュ
3. Settings → Pages → Source を `main` ブランチに設定

### 2. Googleスプレッドシートの準備
1. Googleスプレッドシートを新規作成
2. シート名を「回答」に変更
3. 拡張機能 → Apps Script を開く
4. `gas_code.gs` の内容を貼り付けて保存
5. デプロイ → 新しいデプロイ → ウェブアプリ
   - 実行者：自分
   - アクセス：全員
6. デプロイURLをコピー

### 3. index.htmlの設定
`index.html` の以下の箇所にGASのデプロイURLを貼り付ける：
```javascript
const GAS_URL = 'YOUR_GAS_DEPLOYMENT_URL_HERE';
```

### 4. 公開URL
```
https://[GitHubユーザー名].github.io/marc-survey/
```

## 一時保存の仕組み
- 氏名入力 → 「一時保存」ボタン → localStorageに保存
- 再アクセス時に氏名を入力すると自動復元
- 全角・半角スペースは除去して照合（表記ゆれ対応）
- 送信完了後にlocalStorageから削除
