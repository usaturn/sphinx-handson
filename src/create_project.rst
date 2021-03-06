プロジェクトを作成する
======================


Sphinxでドキュメントを作成するためには、まず「プロジェクト」を作る必要があります。
プロジェクトの作成はコマンドラインからの作業になりますので、Windowsの場合はコマンドプロンプト、MacやLinuxの場合は仮想端末(ターミナルなど)を起動させます。

プロジェクトは、いくつかの設定ファイルなどが配置された、ドキュメントを保存するための専用ディレクトリです。
配置するファイルなどは、Sphinxに含まれる「sphinx-quickstart」というコマンドで作成します。

sphinx-quickstart
-----------------

何もオプションを付けないと対話モードになり、 ``-q`` オプションを付けると非対話モードでプロジェクトが作成できます。
ここでは非対話モードを紹介します。

:プロジェクト名の指定: -p
:ドキュメントの製作者(Author name(s))の指定: -a
:プロジェクトのバージョンを指定: -v
:プロジェクトのロケール(言語)を指定: -l

sphinx-quickstart(非対話モード)の実行例:

.. code-block:: console

    $ sphinx-quickstart -q -p project_name -a pyconjp -v 1.0 -l ja project_dir
    Creating file project_dir/conf.py.
    Creating file project_dir/index.rst.
    Creating file project_dir/Makefile.
    Creating file project_dir/make.bat.

    Finished: An initial directory structure has been created.
    (... 以下省略 ...)

- プロジェクトは引数で指定されたディレクトリに作成されます。
- 指定されたディレクトリが存在しない場合は、ディレクトリが作成されます。
- 省略されている場合はカレントディレクトリとなります。
- プロジェクトを作成するディレクトリは空の必要があります。


生成されるファイルとディレクトリ ::

    project_dir/
    ├── _build/
    ├── _static/
    ├── _templates/
    ├── conf.py
    ├── index.rst
    ├── make.bat
    └── Makefile

最初の「make html」
-------------------
sphinx-quickstartの実行が完了すると設定ファイルと雛形のindex.rstが生成されます。

フォーマット変換にはmakeコマンドを利用します。 利用している環境にmakeコマンドがなければ、yumやapt-getなどでインストールしてください。 Windows環境の場合は、sphinx-quickstart実行時に生成されるバッチファイル(make.bat)を利用します。

フォーマット変換もコマンドラインからの作業になります。 まず最初にカレントディレクトリをプロジェクトのルートディレクトリ(Makefileやmake.batが存在するディレクトリ)に移動させます。 プロジェクトのルートディレクトリで「make html」を実行すると、reSTがHTMLに変換されます。 この時の画面には、進捗状況や警告などが表示されます。 警告はreSTの書式に合っていない場合などに発生します。

Sphinxはフォーマット変換を行なう際、最初にすべてのreSTファイルを読み込みます。 読み込まれたreSTファイルは可能な限り変換が行われますが、警告となった部分はreSTに記述したテキストがそのまま出力されたり、該当箇所が抜け落ちる形になります。 エラーとなった場合は変換処理が中断されます。

設定を変更する
--------------
sphinx-quickstartで設定したものはすべて「conf.py」というファイルに記述されています。
内容を確認すると「設定項目 = 設定値」の様に並んでいることがわかります。
conf.pyは、拡張子からもわかるようにPythonで記述されたものです。
マルチバイトを含む設定値は「u'日本語'」のようにクォートの前に「u」を付けるが必要があります。
「u」を指定していない場合、文字化けの原因となります。

設定できる内容は公式ドキュメントにまとまっていますので、そちらを参照してください。

- http://sphinx-doc.org/config.html
- http://docs.sphinx-users.jp/config.html

メニューなどを日本語に変更するにはconf.pyの「language」を設定します。
デフォルトでは設定値が省略されており、「en」と同じになっています。
languageを「ja」と変更することで、日本語に変更できます。


HTMLテーマを変更する
--------------------
見た目を簡単に変更する事ができます。conf.py を編集してみましょう ::

    html_theme = 'bizstyle'


標準のテーマについてはリファレンスを見て下さい。

http://www.sphinx-doc.org/ja/stable/theming.html

