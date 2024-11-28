# [Wasabi サポートページ](https://lowlayergirls.github.io/wasabi-help/) へようこそ！
このページは、[土井麻未(d0iasm) 著 「作って学ぶ　ブラウザのしくみ」（技術評論社, 2024）](https://gihyo.jp/book/2024/978-4-297-14546-0)の内容を補完する情報を掲載しています。

本ページや上記書籍についてのフィードバックは、[本サポートサイトの GitHub Issues](https://github.com/lowlayergirls/wasabi-help/issues)経由で著者までお知らせください。

ハッシュタグは [#作って学ぶブラウザのしくみ](https://x.com/search?q=%23%E4%BD%9C%E3%81%A3%E3%81%A6%E5%AD%A6%E3%81%B6%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%81%AE%E3%81%97%E3%81%8F%E3%81%BF&src=typed_query&f=live) です。

## 関連リンク

- <https://github.com/d0iasm/sababook>
- <https://github.com/hikalium/wasabi>

# 正誤情報

[『［作って学ぶ］ブラウザのしくみ』正誤表](https://lowlayergirls.github.io/wasabi-help/errata)

# 補足情報

## wgetがみつからない

原因: wgetコマンドがインストールされていない。(macOS等)

解決策: wgetコマンドをHomebrew等のパッケージマネージャ経由でインストールするか、`wget`を`curl -O`（curlのあとに半角スペース、続いてハイフンと大文字アルファベットO）に置き換えて実行してみてください。

## （コード修正済）`the x86_64-unknown-none target may not be installed`

**（2024-11-11）[Makefileの変更](https://github.com/hikalium/wasabi/commit/4796f62364ce8f24613dccba60618e1d35254b16)により修正しました。**
**`run_on_wasabi.sh`によって自動的にダウンロードしたMakefileを削除し、もう一度`run_on_wasabi.sh`スクリプトを走らせると問題は出なくなっているはずです。**

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

#### Reference

- <https://github.com/d0iasm/sababook/issues/1>

## （コード修正済）環境構築のHello, Worldで、"No route" "Timed out"という WARN が出ている

**（2024-11-11）[OS側のログ出力の変更](https://github.com/hikalium/wasabi/commit/abf27c6f587e777fce5c53234d45d997ed075996)により修正しました。**

これはOS側のコード由来のWarningなので、無視して大丈夫です。

エラーを無視して自作OS上で`saba`と実行すれば、Hello, worldが表示されます。

## run_on_wasabi.shを実行してもQEMUが起動しない

```
export DISPLAY=0
```

を実行してから再度試してみてください。OS側ビルドスクリプトでの修正を予定しています。

#### Reference

- <https://github.com/d0iasm/sababook/issues/2>

## net/wasabi/src/http.rsでcrate::alloc::string::ToStringが見つからない

`net/wasabi/src/http.rs`で`ToString`モジュールをインポートする際、unresolved importのエラーになってしまう。

```
error[E0433]: failed to resolve: unresolved import
 --> net/wasabi/src/http.rs:4:12
  |
4 | use crate::alloc::string::ToString;
  |            ^^^^^
  |            |
  |            unresolved import
  |            help: a similar path exists: `core::alloc`  
```

[リファレンスコード](https://github.com/d0iasm/sababook/blob/main/ch3/saba/net/wasabi/src/http.rs)にあるように、`crate`をつけずに`use alloc::string::ToString`としてください。

書籍のコードは次の版で修正予定です。

#### Reference

- <https://github.com/lowlayergirls/wasabi-help/issues/1>
