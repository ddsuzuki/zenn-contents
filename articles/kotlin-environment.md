---
title: "WindowsでKotlinの開発環境構築 at IntelliJ"
emoji: "👹"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [kotlin]
published: true
---

# はじめに
## Zennで情報発信をし始めた経緯
会社の研修の一環として、「定期的にZennを用いて情報発信をしていく」ということで始めたものです。
定期的な情報のアウトプットを行うことで、より学び得た内容の理解を深めていき、エンジニアとしてのスキル向上に繋げていこうと思っています。
記念すべき最初の記事のテーマは、**「Kotlinの環境構築」** となります。
誤字脱字や知識不足など、つたない点があると思いますが、温かく見守っていただけますと幸いです。

## なぜKotlinを選んだのか
学生時代、卒業研究の一環でとある官公庁と合同でiOSアプリケーションを作成したことがありましたが、エンジニアとしての案件を含めAndroidアプリケーションを作成したことがありませんでした。
エンジニアとして働いた時から、Android向けモバイルアプリケーションの制作に興味関心を持っていました。
いい機会だと思い、あまり触ったことのない「Kotlin」を用いて、何かしらのアプリケーションを制作してみようと思い選定しました。
いいアイディアが思いつき、形にできたらストアに公開してみようと思いますので、見かけた際はインストールいただけますと幸いです。

# Kotlinの環境構築
## JDKの導入
Kotlinは、JVM(Java Virtual Machine)で動作するプログラミング言語です。
その為、JVMをインストールを行っていない場合、インストールが必要となります。

### ①JDKのダウンロード
以下のOracleの公式サイトにアクセスし、インストールするOSに応じたインストローラをダウンロードします。
今回は、Windowsにインストールしますので、Windowsタブの「x64 Installer」のダウンロードリンクを押下することでダウンロードできます。
![OracleのJDKダウンロードサイト](https://storage.googleapis.com/zenn-user-upload/32a498280346-20221126.png)
https://www.oracle.com/java/technologies/downloads/

### ②JDKのインストール
ダウンロードした「jdk-xx_windows-x64_bin.exe」を押下することで、インストールウィザードが立ち上がります。
![JDKインストールウィザード](https://storage.googleapis.com/zenn-user-upload/21b5915d6f45-20221126.png)

「次」を押下するとインストールフォルダを選択する画面が表示されます。
デフォルトでは、「C:\Program Files\Java\【JDKのバージョン】」にインストールされますので、必要に応じて変更してください。
![JDKインストールウィザード2](https://storage.googleapis.com/zenn-user-upload/0085e970b78e-20221126.png)

「次」を押下すると選択したフォルダにJDKがインストールされます。
インストール完了画面が表示されましたら、**「JDKの導入」完了です。** 

## IntelliJの導入
続いて、IntelliJというIDE(統合開発環境)を導入します。
IntelliJを開発しているJetBrainsという会社は、Kotlinの開発元となりますので、公式のIDEといっても過言ではありません。
そのことから、IntelliJは無料でJavaやKotlinをサポートしているため、IntelliJを選んどけば安心かと思います。

### ①IntelliJのダウンロード
以下の公式サイトにアクセスし、ダウンロードボタンを押下します。
![IntelliJ公式サイト](https://storage.googleapis.com/zenn-user-upload/ff3e3a7d69d3-20221126.png)
https://www.jetbrains.com/ja-jp/idea/

Communityのダウンロードボタンを押下します。
Communityは無償で、Ultimateは有償ですが、無償でもKotlinやJavaはサポートされているので問題ありません。
![IntelliJ公式サイト2](https://storage.googleapis.com/zenn-user-upload/48c6ba34827f-20221126.png)

### ②IntelliJのインストール
ダウンロードしたexeファイルを押下することで、インストールウィザードが立ち上がります。
![IntelliJインストールウィザード](https://storage.googleapis.com/zenn-user-upload/323ca85f90c3-20221126.png)

「Next」を押下するとインストールフォルダを選択する画面が表示されます。
デフォルトでは、「C:\Program Files\JetBrains\IntelliJ IDEA Community Edition 【バージョン日付】」にインストールされますので、必要に応じて変更してください。
![IntelliJインストールウィザード2](https://storage.googleapis.com/zenn-user-upload/e27063e5e8c9-20221126.png)

それ以外の設定はデフォルトのまま「Next」を押下し、「Install」を押下します。
インストール完了画面が表示されましたら、**「IntelliJの導入」完了です。** 

## 実際にKotlinを実行してみる
### ①IntelliJのセットアップ(日本語化)
IntelliJを起動すると以下のWelcome画面が表示されます。
![IntelliJ Welcome](https://storage.googleapis.com/zenn-user-upload/ab9cd0237c88-20221126.png)

IDEのデフォルト言語が英語の為、日本語化プラグインを導入します。
「Plugins」タブを押下し、「japan」と入力し検索、「Japanese Language Pack / 日本語 言語パック」の「Install」ボタンを押下します。
![IntelliJ 日本語化](https://storage.googleapis.com/zenn-user-upload/2e790ff866dc-20221126.png)

再起動すると、日本語化されたWelcome画面が表示されていれば日本語化完了です。
![](https://storage.googleapis.com/zenn-user-upload/0bdf0e14ac54-20221126.png)

### ②Kotlinのプロジェクトを作成
IntelliJの「新規プロジェクト」より、以下の内容を設定し、「作成」を押下します。
- 任意のプロジェクト名を「名前」のテキストボックスに入力
- 言語を「Kotlin」に設定 (デフォルトは「Java」になっています)
- JDKがインストールしたJDKのバージョンに設定されていることを確認
![](https://storage.googleapis.com/zenn-user-upload/e22321e4b9d8-20221126.png)

下記のような画面が表示され、「Main.kt」というファイルが作成されていれば、Kotlinのプロジェクト作成が完了です。
また、「.kt」という拡張子は、Kotlinの拡張子となります。
![](https://storage.googleapis.com/zenn-user-upload/297e561d36b1-20221126.png)

### ③実行
さっそく、Kotlinを実行してみましょう。
ファイルを新規に作成して実行するのもいいですが、最初からサンプルプログラムが用意されておりますので、それを実行します。
右上の再生ボタンを押下すると、コンパイルされ、下のコンソールに「Hello World!」が表示されたことが確認できます。

![](https://storage.googleapis.com/zenn-user-upload/e21ca48f2e75-20221126.png)

# まとめ
今回はWindowsとIntelliJを用いて、Kotlinの開発環境を構築しました。
構築手順はとても簡単ですので、読者の皆様もIntelliJとKotlinを用いたAndroidアプリ開発に挑戦してみてはいかがでしょうか。
それでは、ここまでお読みいただきました読者の皆様、ありがとうございました。

# 参考サイト
https://www.sejuku.net/blog/98706
https://shotanukumizu-1000.hatenablog.com/entry/20210909
https://pleiades.io/pages/pleiades_jetbrains_manual.html