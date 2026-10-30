# 薬転職ナビ（Cloudflare Pages 用）

薬剤師転職の比較サイト初期稿。静的 HTML のみ。

## ページ構成

| パス | 内容 |
|------|------|
| `/` | トップ |
| `/compare/` | 3社比較（ファルマスタッフ・ファゲット・アイリード） |
| `/guides/full-time/` | 正社員向け |
| `/guides/nationwide/` | 全国枠（セルワーク） |
| `/about/` | 運営者情報（氏名・連絡先は要記入） |
| `/privacy/` | プライバシーポリシー |

アフィリエイト URL は `#a8-...` のプレースホルダー。提携後に差し替え。

## GitHub → Cloudflare Pages

1. GitHub で **新しい空リポジトリ**を作成
2. この `site/` フォルダの中身をリポジトリの **ルート**に置く
3. Cloudflare Pages で **Connect GitHub** → そのリポを選択
4. 設定例:
   - Framework preset: **None**
   - Build command: （空）
   - Build output directory: `/` または空（ルートが公開）
5. 独自ドメインを後から接続

### 初回 push 例

```bash
cd pharmacist-career/site
git init
git add .
git commit -m "Initial pharmacist comparison site"
git branch -M main
git remote add origin git@github.com:YOUR_USER/YOUR_REPO.git
git push -u origin main
```

## ローカル確認

```bash
cd pharmacist-career/site
python3 -m http.server 8787
# http://127.0.0.1:8787/
```

## 提携申請前チェック

- [ ] `/about/` に運営名・連絡先を記入
- [ ] 比較表・各社説明が読める
- [ ] 独自ドメインまたは Pages の URL が公開されている
- [ ] A8 で4社（＋セルワーク）を申請
