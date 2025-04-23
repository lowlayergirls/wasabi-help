- Table of Content
{:toc}

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
- 正：**スクリプト**を走らせると、QEMUのアプリケーション**上でOS**が開始します（図0-1）。

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

# 初版第1～2刷をお持ちの方（第3刷で修正済み）

## p90 「メイン関数の実装」リスト下から1行目
- 誤：match client.get("example.com".to_string(), 80, "/".to_string()) {
- 正：match client.get("example.com".to_string(), 80, **""**.to_string()) {

## p94 「メイン関数の変更」リスト5行目
- 誤：match client.get("host.test".to_string(), 8000, "/test.html".to_string()) {
- 正：match client.get("host.test".to_string(), 8000, "**test.html**".to_string()) {

## p127 「AfterAttributeValueQuoted 状態の実装」2段落7行目
- 誤：BeforeAttributeValue 状態に移動します。
- 正：BeforeAttribute**Name**状態に移動します。

## p128 リスト下から7行目
- 誤：self.state = State::BeforeAttributeValue;
- 正：self.state = State::BeforeAttribute**Name**;

## p166 「要素ノードの追加」2段落2行目
- 誤：ノード（current）呼ぶ
- 正：るノード（current）**と**呼ぶ

## p167 リスト

- 誤：

```
        if current.borrow().first_child().is_some() { ── ❹
            let mut last_sibiling = current.borrow().first_child();
            loop { ── ❺
                last_sibiling = match last_sibiling {
                    Some(ref node) => {
                        if node.borrow().next_sibling().is_some() {
                            node.borrow().next_sibling()
                        } else {
                            break;
                        }
                    }
                    None => unimplemented!("last_sibiling should be Some"),
                };
            }

            last_sibiling
                .unwrap()
                .borrow_mut()
                .set_next_sibling(Some(node.clone())); ── ❻
            node.borrow_mut().set_previous_sibling(Rc::downgrade(
                &current
                    .borrow()
                    .first_child()
                    .expect("failed to get a first child"),
            ))
        } else { ── ❼
            current.borrow_mut().set_first_child(Some(node.clone())); ── ❽
        }

        current.borrow_mut().set_last_child(Rc::downgrade(&node)); ── ❾
        node.borrow_mut().set_parent(Rc::downgrade(&current)); ── ❿

        self.stack_of_open_elements.push(node); ── ⓫
    }
}
```

- 正：

```
        if current.borrow().first_child().is_some() { ── ❹
            let mut last_sibling = current.borrow().first_child();	✏「sibling」のスペルを修正
            loop { ── ❺
                last_sibling = match last_sibling {	✏「sibling」のスペルを修正
                    Some(ref node) => {
                        if node.borrow().next_sibling().is_some() {
                            node.borrow().next_sibling()
                        } else {
                            break;
                        }
                    }
                    None => unimplemented!("last_sibling should be Some"),	✏「sibling」のスペルを修正
                };
            }

            last_sibling	✏「sibling」のスペルを修正
                .as_ref()	✏追加
                .unwrap()
                .borrow_mut()
                .set_next_sibling(Some(node.clone())); ── ❻
            node.borrow_mut().set_previous_sibling(Rc::downgrade(
                &last_sibling.expect("last_sibling should be Some")	✏変更
            ))
        } else { ── ❼
            current.borrow_mut().set_first_child(Some(node.clone())); ── ❽
        }

        current.borrow_mut().set_last_child(Rc::downgrade(&node)); ── ❾
        node.borrow_mut().set_parent(Rc::downgrade(&current)); ── ❿

        self.stack_of_open_elements.push(node); ── ⓫
    }
}
```

## p171 リストの19行目

- 誤：

```
if current.borrow().first_child().is_some() {  ── ❺
    current
        .borrow()
        .first_child()
        .unwrap()
        .borrow_mut()
        .set_next_sibling(Some(node.clone())); ── ❻
    node.borrow_mut().set_previous_sibling(Rc::downgrade(
        &current
            .borrow()
            .first_child()
            .expect("failed to get a first child"),
    ));
```

- 正：

```
if current.borrow().first_child().is_some() {  ── ❺
    current
        .borrow()
        .first_child()
        .unwrap()
        .borrow_mut()
        .set_next_sibling(Some(node.clone())); ── ❻
    🖍削除
```

## p273 「位置の計算」2段落3、4、5行目
- 誤：sibiling
- 正：**sibling**

## p273-274 リスト5、6、7、12、13、14行目
- 誤：sibiling
- 正：**sibling**

## p275 リスト5、6、7、11、14、15、24、25行目
- 誤：sibiling
- 正：**sibling**

## p334 リスト下から7行目
- 誤：return Err(Error::InvalidUI("failed to draw a string".to_string()));
- 正：return Err(Error::InvalidUI("failed to draw a **rect**".to_string()));

## p379 リスト1行目

- 誤：

```
if self.input[self.pos].is_ascii_alphanumeric() || self.input[self.pos] == '$' {
```


- 正：

```
if self.input[self.pos].is_ascii_alphanumeric()
|| self.input[s elf.pos] == '_' || self.input[self.pos] == '$' {	◀「|| self.input[s elf.pos] == '_'」を追加
```

## p384 1つ目のリスト10行目

- 誤：<identifier name> ::= (& | _ | a-z | A-Z) (& | a-z | A-Z)*
- 正：<identifier name> ::= (**$** | _ | a-z | A-Z)**+**

## p394 「変数の取得」1段落1行目

- 誤：Environment 構造体に保存されている変数をまずvariablesに保存されている変数をチェックし
- 正：Environment 構造体**の**variablesに保存されている変数をチェックし

## p394 「変数の追加と更新」1段落1行目、2段落1行目

- 誤：varialbe
- 正：vari**able**

## p395 「evalメソッドの変更」3段落3行目、6段落1行目

- 誤：varialbe
- 正：vari**able**

## p405 上から3行目

- 誤：変名
- 正：変**数**名

## p426 「ブラウザAPIを呼び出すメソッドの追加」4段落4行目

- 誤：取得ための
- 正：取得**する**ための