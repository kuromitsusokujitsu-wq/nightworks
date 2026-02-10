# on the line JAPAN - 編集可能な静的サイト

このプロジェクトは、**人が直接編集できる静的HTML/CSS/JSサイト**です。React、Vite、バンドラーなどの複雑なビルドツールは一切使用していません。

## 📁 ファイル構造

```
editable-static-site/
├── index.html                    # メインHTMLファイル（編集可能）
├── assets/
│   ├── css/
│   │   └── style.css            # スタイルシート（編集可能）
│   ├── js/
│   │   └── main.js              # JavaScriptロジック（編集可能）
│   └── images/                  # 画像ファイル
│       ├── hero-bg.jpg
│       ├── icon-stable.png
│       ├── icon-reliable.png
│       ├── icon-support.png
│       ├── icon-avoid-risk.png
│       └── ...
└── README.md                     # このファイル
```

## 🚀 ローカルでの確認方法

### 方法1：Python 3を使用（推奨）

```bash
# プロジェクトディレクトリに移動
cd editable-static-site

# Webサーバーを起動
python3 -m http.server 8000

# ブラウザで開く
http://localhost:8000
```

### 方法2：Node.jsを使用

```bash
# グローバルにhttp-serverをインストール（初回のみ）
npm install -g http-server

# Webサーバーを起動
http-server

# ブラウザで開く
http://localhost:8080
```

### 方法3：Live Serverを使用（VS Code）

1. VS Codeで「Live Server」拡張機能をインストール
2. `index.html`を右クリック
3. 「Open with Live Server」を選択

## ✏️ 編集方法

### HTMLの編集（index.html）

```html
<!-- テキストを編集 -->
<h1 class="hero-title">風俗を始めとする</h1>

<!-- リンクを変更 -->
<a href="https://lin.ee/ZbPbnAH" target="_blank">LINEでお問い合わせ</a>

<!-- 画像を変更 -->
<img src="./assets/images/icon-stable.png" alt="stable">
```

### CSSの編集（assets/css/style.css）

```css
/* 色を変更 */
.hero-title {
    color: #ffffff;  /* ← ここを編集 */
}

/* フォントサイズを変更 */
h1 {
    font-size: 3rem;  /* ← ここを編集 */
}

/* 背景色を変更 */
.strengths-section {
    background-color: #f8f9fa;  /* ← ここを編集 */
}
```

### JavaScriptの編集（assets/js/main.js）

```javascript
/**
 * カスタム関数を追加
 */
function myCustomFunction() {
    console.log('My custom function');
}

// イベントリスナーを追加
document.addEventListener('click', myCustomFunction);
```

## 🎨 主要なセクション

### 1. ヘッダー・ナビゲーション
- ファイル：`index.html` の `<header>` タグ
- スタイル：`style.css` の `.header` クラス

### 2. ヒーローセクション
- ファイル：`index.html` の `.hero-section`
- スタイル：`style.css` の `.hero-section`
- 背景画像：`./assets/images/hero-bg.jpg`

### 3. 強みセクション
- ファイル：`index.html` の `.strengths-section`
- スタイル：`style.css` の `.strength-cards`

### 4. FAQセクション
- ファイル：`index.html` の `.faq-section`
- スタイル：`style.css` の `.faq-item`
- ロジック：`main.js` の FAQアコーディオン処理

### 5. 企業情報セクション
- ファイル：`index.html` の `.company-info-section`
- Google Maps埋め込み：`<iframe>`

### 6. フッター
- ファイル：`index.html` の `<footer>`
- スタイル：`style.css` の `.footer`

## 🔧 よく使う編集パターン

### テキストを変更する

```html
<!-- 変更前 -->
<h2>当社の強み</h2>

<!-- 変更後 -->
<h2>弊社の特徴</h2>
```

### 色を変更する

```css
/* 変更前 */
.cta-button {
    background-color: #06C755;  /* 緑 */
}

/* 変更後 */
.cta-button {
    background-color: #0066cc;  /* 青 */
}
```

### 画像を変更する

```html
<!-- 変更前 -->
<img src="./assets/images/hero-bg.jpg" alt="ヒーロー画像">

<!-- 変更後 -->
<img src="./assets/images/new-hero.jpg" alt="ヒーロー画像">
```

### リンク先を変更する

```html
<!-- 変更前 -->
<a href="https://lin.ee/ZbPbnAH">LINEでお問い合わせ</a>

<!-- 変更後 -->
<a href="https://example.com/contact">お問い合わせ</a>
```

### セクションを追加する

```html
<!-- 新しいセクションを追加 -->
<section class="new-section">
    <div class="container">
        <h2 class="section-title">新しいセクション</h2>
        <p>ここにコンテンツを追加</p>
    </div>
</section>
```

対応するCSSを追加：

```css
.new-section {
    background-color: #ffffff;
    padding: 4rem 0;
}
```

## 📱 レスポンシブ対応

このサイトはモバイル・タブレット・デスクトップに対応しています。

```css
/* モバイル（480px以下） */
@media (max-width: 480px) {
    h1 { font-size: 1.5rem; }
}

/* タブレット（768px以下） */
@media (max-width: 768px) {
    .features-grid {
        grid-template-columns: 1fr;
    }
}

/* デスクトップ（1024px以上） */
@media (min-width: 1024px) {
    .container {
        max-width: 1280px;
    }
}
```

## 🎯 ローカル確認時のチェックリスト

```
□ すべてのテキストが正しく表示されている
□ 画像がすべて読み込まれている
□ リンクが正しく動作している
□ モバイルメニューが開閉できる
□ FAQアコーディオンが動作している
□ スムーズスクロールが機能している
□ 色・フォント・レイアウトが意図通り
```

## 🚀 ロリポップへのアップロード

### ステップ1：ファイルを準備

```
public_html/ontheline/
├── index.html
├── .htaccess
└── assets/
    ├── css/
    │   └── style.css
    ├── js/
    │   └── main.js
    └── images/
        └── ...
```

### ステップ2：FileZillaでアップロード

1. FileZillaを起動
2. ホスト、ユーザー名、パスワードを入力
3. `public_html/ontheline/` フォルダに接続
4. ファイルをドラッグ&ドロップでアップロード

### ステップ3：権限を設定

```
index.html：644
.htaccess：644
assets：755
css：755
js：755
images：755
```

### ステップ4：ブラウザで確認

```
http://aux-office.com/ontheline/
```

## 🔗 参考リンク

- [HTML リファレンス](https://developer.mozilla.org/ja/docs/Web/HTML)
- [CSS リファレンス](https://developer.mozilla.org/ja/docs/Web/CSS)
- [JavaScript リファレンス](https://developer.mozilla.org/ja/docs/Web/JavaScript)
- [Google Fonts](https://fonts.google.com/)

## 📝 注意事項

- **難読化・圧縮なし**：すべてのコードは人が読める形式です
- **外部依存なし**：React、Vue、Angularなどのフレームワークは使用していません
- **相対パス参照**：すべてのファイルは相対パス（`./`）で参照しています
- **実DOM**：すべてのHTMLは実際のDOM要素として記述されています

## 🆘 トラブルシューティング

### 画像が表示されない

```html
<!-- 確認：相対パスが正しいか -->
<img src="./assets/images/hero-bg.jpg" alt="ヒーロー画像">
```

### スタイルが反映されない

1. ブラウザのキャッシュをクリア（Ctrl + Shift + Delete）
2. CSSファイルの保存を確認
3. ブラウザをリロード（Ctrl + R）

### JavaScriptが動作しない

1. ブラウザの開発者ツール（F12）でエラーを確認
2. `main.js` の保存を確認
3. ブラウザをリロード

## 📧 サポート

ご質問やご不明な点がございましたら、お気軽にお問い合わせください。

---

**on the line JAPAN Co., Ltd.**  
© 2026 All Rights Reserved.
