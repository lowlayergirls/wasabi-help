- [正誤表（最終更新日：2024/11/27）](#----------2024-11-27-)
- [初版第1刷をお持ちの方（第2刷で修正済み）](#---1---------2-------)
  * [p.vii 「アプリケーションをWasabiOSで動かす」1段落目](#pvii-----------wasabios-----1---)
  * [p.viii 1つ目のリスト下から6行目](#pviii-1---------6--)
  * [p.viii 3段落1行目](#pviii-3--1--)
  * [p.ix 4段落1行目](#pix-4--1--)
  * [p.28 「ストレージ」1段落5行目](#p28--------1--5--)
  * [p.48 「スキームの確認」2つ目のリスト上から3行目](#p48----------2---------3--)
  * [p.57 1つ目のリスト7行目](#p57-1------7--)
  * [p.75 2つ目のリスト3行目](#p75-2------3--)
  * [p.77 2行目](#p77-2--)
  * [p.84 「文字列の前処理」2段落3行目](#p84----------2--3--)
  * [p.84 「文字列の前処理」2段落4行目](#p84----------2--4--)
  * [p.84 2つ目のリスト5行目](#p84-2------5--)
  * [p.84 3つ目のリスト5行目](#p84-3------5--)
  * [p.126 「AttributeValueUnquoted状態の実装」1段落1行目](#p126--attributevalueunquoted------1--1--)
  * [p.130 1つ目のリスト3行目](#p130-1------3--)
  * [p.134 1つ目のコマンド1行目](#p134-1-------1--)
  * [p.188 1つ目のコマンド1行目](#p188-1-------1--)
  * [p.215 1つ目のリスト10行目](#p215-1------10--)
  * [p.216 1つ目のリスト5行目](#p216-1------5--)
  * [p.216 1つ目のリスト7行目](#p216-1------7--)
  * [p.241 1つ目のコマンド7，8行目](#p241-1-------7-8--)
  * [p.438 「ローカルサーバの構築」2段落1行目](#p438-------------2--1--)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>


# 正誤表（最終更新日：2024/11/27）

本書に下記のとおり誤りがございました。お詫びして訂正いたします。

# 初版第1刷をお持ちの方（第2刷で修正済み）

## p.vii 「アプリケーションをWasabiOSで動かす」1段落目

- 誤：

アプリケーションをWasabiOSで動かすためには、cargo buildコマンドでビルドしたアプリケーションのバイナリを、WasabiOSが提供するrun_with_app.shというスクリプトを使用して走らせる必要があります。これらを自動的に行ってくれる便利なシェルスクリプトを用意したので、以下のスクリプトを自分のプロジェクトに追加してください。または、d0iasm/saba/run_on_wasabi.shからコピーすることもできます。

- 正：

アプリケーションをWasabiOSで**動かすには**、cargo buildコマンドでビルドしたアプリケーションのバイナリを、WasabiOSが提供するrun_with_app.shというスクリプトを使用して走らせる必要があります。これらを自動的に**行う**シェルスクリプトを用意したので、以下のスクリプトを**後ほどcargoコマンドによって作成するプロジェクトのトップディレクトリに追加してください。d0iasm/saba/run_on_wasabi.shからコピーもできます。**

## p.viii 1つ目のリスト下から6行目

- 誤：wget https://raw.githubusercontent.com/hikalium/wasabi/main/external_app_template/
- 正：wget https://raw.githubusercontent.com/hikalium/wasabi/**for_saba**/external_app_template/**↵**

## p.viii 3段落1行目

- 誤：

また、もしスクリプトが途中で失敗したら、rm -rf buildなどによりダウンロードしたWasabiOSのソースコードを削除してみてください。

- 正：

**もし**スクリプトが途中で失敗したら、rm -rf buildなど**で**ダウンロードしたWasabiOSのソースコードを**削除してください**。**環境によってはwgetの導入が必要です。**

## p.ix 4段落1行目

- 誤：スクリプトを走らせると、QEMUのアプリケーションが開始します（図0-1）。
- 正：　**スクリプト**を走らせると、QEMUのアプリケーション**上でOS**が開始します（図0-1）。

## p.28 「ストレージ」1段落5行目

- 誤：少なくとも合計で3,000個までのCookieを保存
- 正：少なくとも合計で3,000個**の**Cookieを保存

## p.48 「スキームの確認」2つ目のリスト上から3行目

- 誤：fn is_http(&mut self) -> bool {
- 正：fn is_http(**&self**) -> bool {

## p.57 1つ目のリスト7行目
- 誤：let url = "http://example.com:8888/index.html?a=123&b= 456".to_string();
- 正：let url = "http://example.com:8888/index.html?a=123&**b=456**".to_string();

「3&b= 456」の半角スペースを削除

## p.75 2つ目のリスト3行目
- 誤：use crate::alloc::string::ToString;
- 正：use **alloc**::string::ToString;

## p.77 2行目
- 誤：コネクション確率
- 正：コネクション**確立**

## p.84 「文字列の前処理」2段落3行目
- 誤：改行シーケンス（\n\r）
- 正：改行シーケンス（**\r\n**）

## p.84 「文字列の前処理」2段落4行目
- 誤：\n\rはWindows
- 正：**\r\n**はWindows

## p.84 2つ目のリスト5行目
- 誤：raw_response.trim_start().replace("\n\r", "\n");
- 正：raw_response.trim_start().replace("**\r\n**", "\n");

## p.84 3つ目のリスト5行目
- 誤：raw_response.trim_start().replace("\n\r", "\n");
- 正：raw_response.trim_start().replace("**\r\n**", "\n");

## p.126 「AttributeValueUnquoted状態の実装」1段落1行目
- 誤：シングルクオートで囲まれたタグ
- 正：**クオート**で囲まれ**ていない**タグ

## p.130 1つ目のリスト3行目
- 誤：either↵StartTag
- 正：either StartTag

間の矢印を削除し半角スペースに

## p.134 1つ目のコマンド1行目
- 誤：$ mv saba_core
- 正：$ **cd** saba_core

## p.188 1つ目のコマンド1行目
- 誤：$ mv saba_core
- 正：$ **cd** saba_core

## p.215 1つ目のリスト10行目
- 誤：(self.consume_numeric_token());
- 正：(self.consume_numeric_t**oken());**

「oken());」の部分を太字に

## p.216 1つ目のリスト5行目
- 誤：floating_digit
- 正：f**loating_digit**

「loating_digit」の部分を太字に

## p.216 1つ目のリスト7行目
- 誤：c.to_digit(10).unwrap() as f64
- 正：c.to_digit(10).unwrap() **as f64**

「as f64」の部分を太字に

## p.241 1つ目のコマンド7，8行目
- 誤：

```
├── layout_object.rs
├── layout_point.rs
├── layout_size.rs
└── layout_view.rs
```

- 正：

```
├── layout_object.rs
└── layout_view.rs
```

## p.438 「ローカルサーバの構築」2段落1行目
- 誤：OSを起動させたあと、
- 正：OSを起動させ**、sabaと入力しアプリケーションを開始した**あと、



