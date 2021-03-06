# Muisto Python製静的サイトジェネレータ
「Muisto」はPython製の静的サイトジェネレータ（SSG）です。Markdownでファイルを書いてコマンドを実行すると自動で素敵なサイトを作ってくれます✨
## インストール方法
以下はMacの場合。事前にBrewをインストールしておいてください。

```bash:
$ brew install mecab mecab-ipadic git curl xz
$ git clone https://github.com/mamoruitoi/muisto.git
$ cd muisto/muisto/
$ sudo pip install -e .
```

## 機能
### 見出しを見やすく
見出しを形態素解析して文節に分解することで、どことは言いませんが[こういうサイト](https://about.google/?fg=1&utm_source=google-JP&utm_medium=referral&utm_campaign=hp-header)のように文章が中途半端に改行されることを防ぎます。この処理には形態素解析ライブラリMeCabが必要です（前段のコマンドでインストールされます）。
### Muisto Codes
記事に「Muisto Codes」というコードを埋め込むことで日付やタイトル、変換テーマを設定することができます。
#### 全ファイルで使えるもの
- **@cover: "hoge.png"**  
./img/hoge.pngをカバー画像に設定します。
- **@date: "0900-0418-2020"**  
日付を2020年4月18日午前9時に設定します。
- **@mode: "blog"**  
モードをblogに設定します。config.mdでモードごとにデフォルトの設定を決めることができます。config.mdでモードごとに設定を書くと、各ファイルにはモード名を書くだけでそのデフォルト設定が適用されます。また、モードごとに記事のインデックスページが自動で生成されます。
- **@place: "Tokyo"**  
記事を書いた場所をTokyoに設定します。
- **@tags: "Muisto|Web|Design"**  
記事に「Muisto」「Web」「Design」という3つのタグを付けます。
- **@writer: "Mamoru Itoi"**  
書いた人をMamoru Itoiに設定します。
- **@theme: "muisto_light"**  
記事のテーマをmuisto_lightに設定します（今のところこれしかないけど気が向いたら追加する）。
#### config.mdでだけ使えるもの
- **@icon: "nights_stay"**  
ナビゲーションバーに表示する、そのモードの[マテリアルアイコン](https://material.io/resources/icons/?style=baseline)をnights_stayに設定します。
- **@color: "#aaa"**  
ナビゲーションバーに表示するモードごとのインデックスページへのリンクの色を#aaaに設定します。
- **@twitter: "MamoruItoi"**  
TwitterのアカウントをMamoruItoiに設定します。
- **@github: "mamoruitoi"**  
GitHubのアカウントをmamoruitoiに設定します。
- **@logo: "oblivion-logo.png"**  
サイトのロゴを./img/oblivion-logo.pngに設定します。
- **@fav: "favicon.ico"**  
サイトのファビコンを./img/favicon.icoに設定します。
- **@url: "https://mamoruitoi.github.io/"**  
サイトのURLを設定します。**必ず最初に設定してください。また、最後のスラッシュまで含めてください。**
- **@name: "Oblivion"**  
サイトの名前をOblivionに設定します。
また、config.md内で@titleを使うとサイトのサブタイトルを設定できます。
