用語集を作る
============

Sphinxには用語集を作成するための「glossary」というディレクティブがあります。
記述したキーワード(用語)は「term」というロール(後述)で参照することができます。
また、キーワードとして定義した単語は、索引のページからも参照できます。

Sphinx1.3のデフォルトテーマのAlabasterでは、横幅が860px以上あると索引へのリンクは消えてしまいます。
ブラウザの横幅をサイドバーが消えるまで縮める(横幅860px未満)か、ページ内に「 ``:ref:`genindex``` 」としてリンクを作成してください。
テーマによっては、ページの右上、または右下に索引のリンクが常に存在するものもあります。
テーマの変更については次回紹介します。

glossaryはディレクティブの要素にキーワードを指定し、さらにインデントを付け、キーワードの説明を記述しています。
これは「定義リスト」と呼ばれるreSTの記法のひとつです。
定義リストの詳しい内容についてはDocutilsのドキュメント [#definition-lists]_ を参照してください。

glossaryは1箇所にまとめて記述する必要はなく、複数のページで使用しても問題はありません。

glossaryは以下の様に使用します。
sortedオプションは変換時にキーワードをアルファベット順に並べ替えます。


glossaryを参照する例::

   :term:`Sphinx` と :term:`Word` について、それぞれのメリット・デメリットをまとめます。

.. [#definition-lists]
   - http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#definition-lists
   - http://docutils.sphinx-users.jp/docutils/docs/ref/rst/restructuredtext.html#definition-lists
