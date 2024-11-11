# [Wasabi サポートページ](https://lowlayergirls.github.io/wasabi-help/) へようこそ！
このページは、[土井麻未(d0iasm) 著 「作って学ぶ　ブラウザのしくみ」（技術評論社, 2024）](https://gihyo.jp/book/2024/978-4-297-14546-0)の内容を補完する情報を掲載しています。

本ページや上記書籍についてのフィードバックは、[本サポートサイトの GitHub Issues](https://github.com/lowlayergirls/wasabi-help/issues)経由で著者までお知らせください。

## 関連リンク

- <https://github.com/d0iasm/sababook>
- <https://x.com/d0iasm>
- <https://github.com/hikalium/wasabi>
- [X(Twitter)上の反応](https://x.com/search?q=(%20%E4%BD%9C%E3%81%A3%E3%81%A6%E5%AD%A6%E3%81%B6%E3%80%80%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%81%AE%E3%81%97%E3%81%8F%E3%81%BF%20)%20OR%20%23%E4%BD%9C%E3%81%A3%E3%81%A6%E5%AD%A6%E3%81%B6%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%81%AE%E3%81%97%E3%81%8F%E3%81%BF%20OR%20saba_book&src=typed_query&f=live)

## wgetがみつからない

原因: wgetコマンドがインストールされていない。(macOS等)

解決策: wgetコマンドをHomebrew等のパッケージマネージャ経由でインストールするか、`wget`を`curl -O`（curlのあとに半角スペース、続いてハイフンと大文字アルファベットO）に置き換えて実行してみてください。

#### Sources
- <https://x.com/yuusukesan18/status/1855495837474046428>

## `the x86_64-unknown-none target may not be installed`

Note: Fixed by [this commit](https://github.com/hikalium/wasabi/commit/4796f62364ce8f24613dccba60618e1d35254b16) on 2024-11-11.

症状: 以下のようなエラーが`./run_on_wasabi.sh`を実行した際に発生し、失敗する。

```
error[E0463]: can't find crate for `core`
  |
  = note: the `x86_64-unknown-none` target may not be installed
  = help: consider downloading the target with `rustup target add x86_64-unknown-none`

For more information about this error, try `rustc --explain E0463`.
error: could not compile `sabi` (lib) due to 1 previous error
```

解決策: 以下のコマンドを実行してから再度試してみてください。
```
rustup target add x86_64-unknown-none
```

それでもだめな場合は、cargoがパスに正しく登録されていない可能性があります。rustupのインストールをやり直すか、パスを手動で追加して実行してみてください。
```
export PATH="$HOME/.cargo/bin:$PATH"
rustup target add x86_64-unknown-none
```

#### Sources
- <https://x.com/yuusukesan18/status/1855495837474046428>
- <https://x.com/Ysan_999/status/1855600717840646408>

## 環境構築のHello, Worldで、"No route" "Timed out"という WARN が出ている

Note: Fixed by [this commit](https://github.com/hikalium/wasabi/commit/abf27c6f587e777fce5c53234d45d997ed075996) on 2024-11-11.

これはOS側のコード由来のWarningなので、無視して大丈夫です。（OS側 ~~の修正を検討しています~~ を修正しました。）

エラーを無視して自作OS上で`saba`と実行すれば、Hello, worldが表示されます。

#### Sources
- <https://x.com/DAI199/status/1854942923919704066>
- <https://x.com/kmkkiii/status/1855163163236614502>

## run_on_wasabi.shを実行してもQEMUが起動しない

```
export DISPLAY=0
```

を実行してから再度試してみてください。OS側ビルドスクリプトでの修正を予定しています。

#### Sources
- <https://github.com/d0iasm/sababook/issues/2>

