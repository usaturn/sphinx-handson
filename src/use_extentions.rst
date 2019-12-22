拡張を使ってみよう
==================

Sphinx拡張
----------

Sphinx拡張は、あらかじめSphinxに機能として実装されている「組み込み拡張機能」とインストールして機能を追加するサードパーティ製の拡張機能があります。
さまざまな拡張機能がありますが、主な拡張はディレクティブを追加し、Sphinxで表現できる記法を増やします。
他の外部コマンドの実行結果を取り込むような拡張もあります。

サードパーティ製の拡張機能の情報は以下にまとまっています。

- http://sphinx-doc.org/extensions.html
- http://docs.sphinx-users.jp/extensions.html

今回は組み込み拡張のひとつ、「todo拡張」について紹介します。
どの拡張機能も有効にする方法は同じですので、公式ドキュメントを参考に他の拡張機能も使用してみて下さい。

todo以外の拡張機能については公式ドキュメント [#extensions]_ を参照してください。

.. rubric:: 脚注
.. [#extensions]
   - http://sphinx-doc.org/extensions.html#builtin-sphinx-extensions
   - http://docs.sphinx-users.jp/extensions.html#builtin-sphinx-extensions

拡張機能を有効にする
--------------------

拡張機能を使用するにはプロジェクトディレクトリのルートにあるconf.pyに設定を追加します。
todo拡張を有効にするには以下の様に設定します。

変更前::

   extensions = []

変更後::

   extensions = ['sphinx.ext.todo']

複数の拡張機能を使用する場合はカンマ( :kbd:`,` )で区切って並べます。
1行で記述しでも問題ありませんが、下記の例では可読性を高めるために改行を入れています。

複数の拡張機能を使用する例::

   extensions = [
     'sphinx.ext.todo',
     '他の拡張機能',
   ]


追加されるディレクティブとオプション
------------------------------------

todo拡張を有効にすると「todo」と「todolist」というディレクティブが追加されます。

todoディレクティブは、ToDoとしてメモしておきたい内容をreSTに埋め込みます。
ディレクティブの要素にToDoの内容を記述します。
なお、ToDoが1行の場合はディレクティブの引数に内容を記述できます。

todolistディレクティブは、プロジェクト全体のtodoの内容を列挙します。
どのreSTファイルの何行目にあるtodoなのかも合わせて表示します。

しかし、これらのToDoはこのままではHTMLには表示されません。
todo拡張を有効にすると、「todo_include_todos」というオプションが追加されます。
conf.pyに「todo_include_todos = True」と追加で設定すると、todo、todolistが表示されるようになります。

