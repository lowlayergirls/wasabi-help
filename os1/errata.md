- Table of Content
{:toc}

# 正誤表（最終更新日：2025/05/03）

本書に下記のとおり誤りがございました。お詫びして訂正いたします。

# 初版第1刷の正誤表

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

## p.220 サンプルコード内 `locate_loaded_image_protocol()`関数内

ここでは`graphic_output_protocol`という名前の変数が宣言・使用されていますが、実際には`loaded_image_protocol`に相当する値を格納する変数となっています。したがって、これに即した変数名とするのがより適切でした。プログラム自体の動作には影響ありませんが、混乱を招いたことをお詫びいたします。

## p.311「ECAM ―― Enhanced Configuration Access Method」3段落目

- 誤：

各デバイスに対応するConfiguration間

- 正：

各デバイスに対応するConfiguration空間
