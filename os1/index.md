# 「作って学ぶ OSのしくみ(I)」サポートページ
このページは、[hikalium 著 「作って学ぶ　OSのしくみ(I)」（技術評論社, 2025）](https://gihyo.jp/book/2025/978-4-297-14859-1)の内容を補完する情報を掲載しています。

本ページや上記書籍についてのフィードバックは、[本サポートサイトの GitHub Issues](https://github.com/lowlayergirls/wasabi-help/issues)経由で著者までお知らせください。

ハッシュタグは [#OSのしくみ](https://x.com/search?q=%23OS%E3%81%AE%E3%81%97%E3%81%8F%E3%81%BF%20OR%20%E4%BD%9C%E3%81%A3%E3%81%A6%E5%AD%A6%E3%81%B6OS%E3%81%AE%E3%81%97%E3%81%8F%E3%81%BF&src=typed_query&f=live) です。

<img src="./cover.png" width="200px">

## 関連リンク

- <https://github.com/hikalium/wasabi/tree/wasabi4b>
- <https://github.com/hikalium/wasabi>

# 正誤情報

[『［作って学ぶ］OSのしくみ』正誤表](./errata)

# 補足情報

## `rust-analyzer`の設定について

Rustのコードを書く際には`rust-analyzer`というLSPサーバーが非常に便利です。筆者もいつも大変お世話になっています。
しかし、本書のリポジトリで`rust-analyzer`がうまく動作しない場合があるようですので、その解決策をご紹介します。

本書のリポジトリでは再現性を確保するため、Rustツールチェインのバージョンを`rust-toolchain.toml`に記載のとおり固定しています。そのため、より新しいバージョンのRustツールチェインに同梱されている`rust-analyzer`を使用すると、エラーが発生する可能性があります。多くのエディタにおいて`rust-analyzer`拡張機能は、`rust-toolchain.toml`の内容にかかわらず、最新の（もしくは拡張機能に同梱されているバージョンの）`rust-analyzer`をデフォルトで使用するようになっているため、以下のようなエラーメッセージが表示されることがあります。

```
[coc.nvim] Workspace `/home/hikalium/repo/wasabi/Cargo.toml` is using an outdated toolchain version `1.77.0-nightly` but rust-analyzer only supports `1.78.0` and higher.
Consider using the rust-analyzer rustup component for your toolchain or upgrade your toolchain to a supported version.
```

これを回避するためには、本書のリポジトリで使用されているツールチェインに適合したバージョンの`rust-analyzer`をLSPサーバーとして使用するよう、エディタに指示してあげる必要があります。

まず、以下のコマンドをwasabiリポジトリの内部で実行して、`rust-analyzer`の実行ファイルパスを確認します。

```
$ rustup component add rust-analyzer && rustup which rust-analyzer
info: component 'rust-analyzer' for target 'x86_64-unknown-linux-gnu' is up to date
/home/hikalium/.rustup/toolchains/nightly-2024-01-01-x86_64-unknown-linux-gnu/bin/rust-analyzer
```

その後、このファイルパスをエディタの設定に追記します。

- Neovimで`coc.nvim`経由で`coc-rust-analyzer`を利用している場合は、エディタを開いて`:CocConfig`もしくは`:CocLocalConfig`を実行して開かれたファイルを
- VSCodeで[`rust-analyzer`拡張機能](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust-analyzer)を利用している場合は、wasabiレポジトリの配下で`.vscode/settings.json`を

開き、次のアイテムを追加します：

```
{
  "rust-analyzer.server.path": "/home/hikalium/.rustup/toolchains/nightly-2024-01-01-x86_64-unknown-linux-gnu/bin/rust-analyzer"
}
```

設定を保存したのちエディタを再起動すれば、wasabiに対しても`rust-analyzer`が問題なく動作するようになるはずです。

See also: <https://github.com/lowlayergirls/wasabi-help/issues/9>

## 本書を読む前に、Rust言語に関して理解しておいた方がいい内容はありますか？

本書はRust初心者の方でも、それ以外のプログラミング言語の経験がある方であれば問題なく読めることを目指して書かれているため、事前学習は必ずしも必要ではありません。どうしても事前に予習したい場合や、読んでいる途中で参考書が欲しくなってきたら、以下の資料を参考にするとよいでしょう。

- [The Rust Programming Language 日本語版](https://doc.rust-jp.rs/book-ja/)
  - こちらはRust言語の公式チュートリアル（[英語版](https://doc.rust-lang.org/stable/book/)）を日本語に翻訳したものです。Rustの基礎を学ぶ際にちょうどよい、信頼できる情報源となっています。
- [Comprehensive Rust 日本語版](https://google.github.io/comprehensive-rust/ja/)
  - こちらの資料は、Rustの利用を推進している会社のひとつであるGoogle社のソフトウェアエンジニアが、社内のRust講座で使用するために書き上げたドキュメントをオープンソース化したものです。こちらも[英語版](https://google.github.io/comprehensive-rust/)が原文となっています。講義形式の内容になっているため、時間を区切ってコツコツ進めたい場合に便利です。また、この資料を利用して講義を運営する人向けのアドバイスも書かれているため、複数人で学習する際にも役立つかもしれません。

また、本書とあわせて、もしくは本書の次に読むと理解が深まると思われる資料はこちらです。

- [並行プログラミング入門 ―Rust、C、アセンブリによる実装からのアプローチ](https://www.oreilly.co.jp//books/9784873119595/)
  - こちらの書籍は、人類には早すぎた「並行プログラミング」という複雑な問題を、様々な言語による実装を交えつつ解説してくれる良書です。
- [Writing an OS in Rust 日本語版](https://os.phil-opp.com/ja/)
  - こちらの一連のブログ記事は、RustでOSを実装する際に必要となる知見が非常に多く掲載されており、筆者も大いにお世話になった情報源です。本書でも、いくつかの箇所でこのブログに言及しています。こちらも[原文](https://os.phil-opp.com/)は英語ですが、有志により翻訳されているため日本語で読むことができます。
  - こちらのブログ記事を題材にした輪読会に筆者は以前参加しており、その際の録画アーカイブが[YouTubeのプレイリスト](https://www.youtube.com/playlist?list=PL8U-_gKA4tWtNXVnqYRmn8En5Nh6xzADO)にまとめてありますので、睡眠用BGM等としてお役立てください。

さらに発展的なOS自作に関わる情報を手に入れたい方は、筆者だけでなくたくさんの自作OS開発者が集うコミュニティ[osdev-jp](https://osdev.jp/)のSlackへの参加を検討してもよいでしょう。参加方法は[こちら](https://osdev.jp/joinus.html)に記載されています。また、定期的に「自作OSもくもく会」や「作業会」という[イベント](https://osdev-jp.connpass.com/)が開催されておりますので、そちらに参加して本を読み進めるというのもありかもしれません。これらのイベント等の動画アーカイブは[YouTubeのプレイリスト](https://www.youtube.com/@osdev-jp/playlists)にありますので、こちらもあわせて参考にしてみてください。

## rustfmtでuseの内容を自動でバラしてほしい

初版第1刷p.139で、useを行ごとにバラすようにしているよう説明しています。
これを自動でやってくれる方法があると読者より教えていただいたので共有します。
[(Thanks @lapla-cogito!)](https://github.com/lowlayergirls/wasabi-help/issues/7)

`rustfmt.toml`で
`imports_granularity = "Item"`と設定すれば、自動でバラしてくれるようです。
