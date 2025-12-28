# Flowerly Friends Collection - Website

Flowerly Friends Collectionの公式ウェブサイトです。

## 📁 プロジェクト構造

```
.
├── content/
│   ├── txt/           # 編集用TXTファイル（セクション順）
│   └── images/        # 画像ファイル（セクション別フォルダ）
├── assets/
│   └── css/
│       └── styles.css
├── index.html         # メインHTMLファイル
└── package.json
```

## 📝 コンテンツ管理

### TXTファイル一覧（セクション順）
`content/txt/` フォルダ内のファイルを編集してコンテンツを管理：

- **01_header.txt** - ヘッダー情報（ヒーローテキスト、主催者、入場料）
- **02_past-events.txt** - これまでのフラコレ
- **03_schedule.txt** - スケジュール
- **04_venue.txt** - 開催場所
- **05_goods.txt** - グッズ販売
- **06_members.txt** - 出展メンバー
- **07_artwork-sales.txt** - 作品販売
- **08_supporters.txt** - 支援者の皆様
- **09_support-goods.txt** - フラコレ応援グッズ
- **10_staff.txt** - 運営メンバー

### 画像フォルダ一覧（セクション順）
`content/images/` フォルダ内に各セクション用の画像を格納：

- **01_header/** - ロゴ、ヒーロー画像
- **02_past-events/** - 過去のイベント写真
- **03_schedule/** - スケジュール関連画像
- **04_venue/** - 会場写真、地図
- **05_goods/** - グッズ商品画像
- **06_members/** - メンバープロフィール画像
- **07_artwork-sales/** - 販売作品画像
- **08_supporters/** - 支援者関連画像
- **09_support-goods/** - 応援グッズ画像
- **10_staff/** - スタッフプロフィール画像

### TXTファイルの記法
```
# セクション名
内容を記述

# 別のセクション
別の内容
```

## 🔄 更新フロー

1. **TXTファイル編集**: `content/txt/01_header.txt` などを編集
2. **画像追加**: 必要に応じて `content/images/01_header/` などに画像を配置
3. **反映依頼**: Codex に「01_header.txtを反映して」と依頼（または手動反映）
4. **HTML反映**: Codex の支援で `index.html` を更新

## 🚀 ローカル確認

### ファイルを直接開く
```bash
open index.html
```

### ローカルサーバーで確認
```bash
npm run serve
# http://localhost:8080 でアクセス
```

## 📑 サイト構造

- トップページ: `index.html`
  - 予約販売: `pre-sale.html`
  - フラコレ応援グッズ: `support.html`

## 🏷️ 販売ステータス表記

- **Sold out**: 作品が完全に売れ、入金確認まで完了している状態
- **売約済み**: 申し込みは入っているが、まだ入金が確定していない状態（キャンセルとなる可能性あり）

## 💡 特徴

- ✅ シンプルな静的HTML
- ✅ TXTファイルで簡単コンテンツ管理
- ✅ Codex による反映支援（自動ではなく支援）
- ✅ サーバー不要で動作
- ✅ 高速表示

## 🧭 GitHub フロー

このリポジトリは「開発用（`labo` リモート）」と「本番用（`production` リモート）」の二段階で運用しています。

- **開発用**: 日常的な修正は `git push labo main` で反映。Codex の指示や個別の修正もまずこちらへ。
- **本番用**: `git fetch production` → `git diff labo/main production/main` で差分確認し、必要なら `git merge production/main`（もしくは `git rebase production/main`）を実行後、`git push production main` で公開。
- 本番更新の流れ：
  1. `git push labo main` で開発リモートを更新
  2. `git fetch production` / `git diff labo/main production/main` で差分確認
  3. 本番に追随する場合は `git merge production/main` または `git rebase production/main`
  4. `git status` で作業ツリーがクリーンか確認したら `git push production main`

### 🎯 特別な反映トリガー
ユーザーが「`#n追加したので更新してproductionにも反映`」のようなフレーズを伝えた場合は、開発用の`labo`リモートに`git push labo main`を行い、続けて`production`リモートに`git push production main`で最新コミットを反映する流れを優先します。

この手順で開発用と本番用を分離した運用を維持できます。

## 📋 管理担当

**コンテンツ編集**: ユーザー（TXTファイル編集）
**HTML反映**: Codex（支援・手動反映）
