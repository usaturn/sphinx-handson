.. _editor:


reST を記述する上での注意点
===========================

ファイル名、ディレクトリ名
--------------------------
- Sphinx 自体はマルチバイト文字に対応していますがコマンドラインを扱う上で日本語やスペースを入れる事は避けて半角英数文字を使う事を推奨します。


文字コード
----------

- 標準は UTF-8 です。設定により他の文字コードも使えますが UTF-8 を使うことを推奨します。

フォント
---------

- プロポーショナルフォントは使わず、必ず等幅フォントを使用して下さい

ハードタブは使わない
--------------------

- 半角スペースを使うようにして下さい

インデント
----------

- reSTではインデントが重要な意味を持っています。

    目安は半角スペース 3 個ですが、直前の行によって挙動が変わります。
    連続する同じ高さのインデントは、ひとつのブロックとして扱われ、空行を1行以上入れると段落が分かれます。
    インデントの高さを変える場合は、次のインデントとの間に1行以上の空行を開ける必要がります。


改行コード
----------

- LF、CRLF のどちらでも構いません。

シンタックスハイライト
----------------------

- reSt で記述する際は reST のシンタックスハイライトが利くエディタを利用する事を推奨します。

