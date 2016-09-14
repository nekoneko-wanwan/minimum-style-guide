# これは何
- ゆるいスタイルガイド
- 最低限守りたいファイル構成のみを用意し、命名などは柔軟に
- 特に少ないページを作成するのに使う

# ファイル構成

```styleSheets/
- style.scss
- preset/
    - _config.scss: グローバル変数・関数・mixinなどの定義
    - _reset.scss: リセットcss
    - _styleTag_default.scss: 要素の初期値（classはつけない）
    - _styleTag_custom.scss: defaultをclassで拡張したもの
    - _フレームワーク.scssとか
- _layout.scss
    - ユニークなもの
    - 接頭辞に **l-** を付ける
- _module.scss
    - 汎用的なもの
    - 接頭辞に **m-** を付ける
- _page.scss
    - 汎用的でないパーツ・特定のページなどで使うもの
    - 接頭辞に **p-** を付ける
    - _moduleを拡張することを許可
        - 特定のスタイル `.p-xxx` 配下でのmoduleはこうしたい、など
- _utility.scss
    - アドホックなスタイル
    - 接頭辞に **u-** を付ける
```

※必要に応じて、layout・module・page・utilityもpresetのように分割する

# レイヤー構成
style.scssの読み込み順も同じ

↑弱い

- preset/
  - _reset
  - _styleTag_default
  - _styleTag_custom
  - _フレームワーク
- _layout
- _module
- _page
- _utility

↓強い

