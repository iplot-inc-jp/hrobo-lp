# HRobo LP — GitHub Pages 公開用

現在公開しているHRoboのLPを、デザインや文章・画像・PDFを変更せずにGitHub Pagesへ移すための一式です。HTML/CSS/JavaScriptのみなので、ビルドや追加ソフトのインストールは不要です。

**軽量版について：** ブラウザからまとめてアップロードしやすいよう、元のパッケージに入っていた未使用の参考画像を除きました。LPとサンクスページの表示に必要な画像・ロゴ、および7ページの紹介PDFは元ファイルのままで、画質やレイアウトは変わりません。

## ファイルの役割

- `index.html`：LPのトップページ
- `thank-you/index.html`：資料請求後のページ（`/thank-you/`）
- `thank-you.html`：同じサンクスページ（`/thank-you.html`）
- `assets/`：ロゴ・画像・HRoboサービス紹介資料PDF（全7ページ）
- `CNAME`：独自ドメイン `lp1.hrobo.jp` の指定
- `.nojekyll`：GitHub Pagesの自動Jekyll処理を無効にする設定

## GitHub Pagesで公開する手順

1. GitHubで新規リポジトリを作成します（例：`hrobo-lp`）。
2. ZIPを展開し、中にある**全ファイルとフォルダ**をリポジトリのルートにアップロードします。**ZIP自体をアップロードするのではありません。** `index.html` がリポジトリの最上位に来ることを確認してください。
3. リポジトリの **Settings → Pages** を開き、**Build and deployment → Deploy from a branch** を選択。Branchを `main`、フォルダを `/(root)` にして保存します。
4. **Custom domain** が `lp1.hrobo.jp` になっていることを確認します。`CNAME` ファイルが自動的に読み込まれない場合は同欄に入力して保存します。
5. `hrobo.jp` を管理するDNS担当者に、ホスト名 `lp1` の **CNAMEレコードの変更**を依頼します。設定先は `＜GitHubのユーザー名または組織名＞.github.io` です。**リポジトリ名は含めません。**
6. DNSの反映とSSL証明書の準備が終わったら、**Enforce HTTPS** を有効にして動作確認します。

**注意：** 以前ChatGPT Sites用として案内した `lp1.hrobo.jp → custom-domains.chatgpt.site` のCNAMEとは併用できません。GitHub Pagesで公開する際には、上記のGitHub Pages用CNAMEに**置き換えてください**。前のTXTレコードはGitHub Pagesの設定値としては使いません。GitHub側で独自ドメインの所有権確認を求められた場合、GitHubが提示する専用TXTレコードを別途設定します。

## 確認するURL

- LP：`https://lp1.hrobo.jp/`
- サンクスページ：`https://lp1.hrobo.jp/thank-you/`
- PDF：`https://lp1.hrobo.jp/assets/HRobo_Service_Guide.pdf`

DNS設定前は、GitHub Pagesが表示するデフォルトURLからも確認できます（カスタムドメイン指定による転送に注意）。また、GitHub Pagesを既存のGitHubプロジェクト配下 `https://＜ユーザー名＞.github.io/＜リポジトリ名＞/` でテストする場合も、画像・PDF・サンクスページのリンクが動くよう相対パスにしています。

Meta広告のインスタントフォームに設定する「送信後のリンク」は、移行完了後に `https://lp1.hrobo.jp/thank-you/` へ更新してください。LP自体にメール送信処理はありません。リードの取得はこれまでどおりMetaのインスタントフォーム側で行います。

## 最終チェック

- [ ] トップページの画像が表示される
- [ ] スマートフォンで文字・ボタンが崩れない
- [ ] サンクスページのボタンからPDF（7ページ）が開く
- [ ] PDF内の機能説明番号が01〜07になっている
- [ ] Meta広告の送信完了リンクを新URLに更新した
- [ ] HTTPSでアクセスできる

