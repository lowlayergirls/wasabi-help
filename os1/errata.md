- Table of Content
{:toc}

# 正誤表（最終更新日：2025/05/03）

本書に下記のとおり誤りがございました。お詫びして訂正いたします。

# 初版第1刷の正誤表

## p.xv「第4章　マルチタスクを実装しよう」目次要素

- 誤：

aync/awaitを使えるようにする

- 正：

async/awaitを使えるようにする

## p.48「"Hello, world"はどこへ行く？」2段落目

- 誤：

　鍵となるのは、この`prinln!`です。

- 正：

　鍵となるのは、この`println!`です。


## p.161「OSのテストをRustで書く」3段落目

- 誤：

うまくいったら正常に終了し、そうでなければ`panic()`するような関数を書けばよいです。

- 正：

うまくいったら正常に終了し、そうでなければ`panic!()`するような関数を書けばよいです。

## p.162「シリアルポート出力の実装」4段落目

- 誤：

今回はエミューレーターを使用して

- 正：

今回はエミュレーターを使用して

## p.167 サンプルコード`src/allocator.rs`内

- 誤：

```
    assert_eq!(round_up_to_nearest_pow2(9), Ok(16));
    assert_eq!(round_up_to_nearest_pow2(9), Ok(16));
```

- 正：

```
    assert_eq!(round_up_to_nearest_pow2(9), Ok(16));

```

(注:
テストケースの最後の2つが冗長でしたので片方を削除しました。残っていても間違いではありませんが、削除したほうがより適切です。)

## p.188 コードブロック内

最上部のコードブロックと、ページ中央のコードブロックの2箇所について：

- 誤：

```
0x0XAC_TUWP
```

- 正：

```
0b0XAC_TUWP
```

## p.194 「async/awaitを使えるようにする」4段落目

- 誤：

_Identity mapping_

- 正：

_Identity Mapping_

## p.204 サンプルコード`src/x86.rs`内

- 誤：

```
struct FPUContenxt {
```

- 正：

```
struct FPUContext {
```

## p.205 サンプルコード`src/x86.rs`内

- 誤：

```
    fpu_context: FPUContenxt, // used by FXSAVE / FXRSTOR
```

- 正：

```
    fpu_context: FPUContext, // used by FXSAVE / FXRSTOR
```

## p.220 サンプルコード内 `locate_loaded_image_protocol()`関数内

ここでは`graphic_output_protocol`という名前の変数が宣言・使用されていますが、実際には`loaded_image_protocol`に相当する値を格納する変数となっています。したがって、これに即した変数名とするのがより適切でした。プログラム自体の動作には影響ありませんが、混乱を招いたことをお詫びいたします。

## p.245 「async/awaitを使えるようにする」見出し

- 誤：

aync/awaitを使えるようにする

- 正：

async/awaitを使えるようにする

## p.311「ECAM ―― Enhanced Configuration Access Method」3段落目

- 誤：

各デバイスに対応するConfiguration間

- 正：

各デバイスに対応するConfiguration空間

## p.312 ページ一番下のコマンド出力結果について

- 誤：

```
$ qemu-system-x86_64 -machine ? | grep q35 | head -n 1
```

- 正：

```
$ qemu-system-x86_64 -machine '?' | grep q35 | head -n 1
```
