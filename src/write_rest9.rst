ファイルのダウンロードリンクや画像へのリンク
=============================================

.. highlight:: rest

ファイルをダウンロードさせるリンク
-----------------------------------
* :term:`プロジェクト` 内に存在するファイルへのダウンロード用リンクを張る事ができます。

  記述例::

    :download:`ダウンロードできます <./ref/build_and_browsing.zip>`

  このように表示されます。

  :download:`ダウンロードできます <./ref/build_and_browsing.zip>`


画像を表示する ～figure ディレクティブ～
----------------------------------------
* 画像を表示させたい場合は ``.. figure::`` というディレクティブを使います。

  まずはPythonの `pillowパッケージ <http://pypi.python.org/pypi/Pillow/>`_ をインストールしましょう。

  ::

    pip install pillow

  `pillowパッケージ <http://pypi.python.org/pypi/Pillow/>`_ がインストール出来たら figureディレクティブのオプションが使えるようになります。

  記述例::

        .. figure:: ./img/background.png
           :scale: 50
           :align: left
           :target: http://sphinx-users.jp/

           一行あけてここに書いたものがキャプションになります

  htmlこのように表示されます。

  .. figure:: ./img/background.png
     :scale: 50
     :align: left
     :target: http://sphinx-users.jp/

     一行あけてここに書いたものがキャプションになります

  * **scale** は縮小、拡大をする時のオプションです。100が1/1スケールです。
  * **target** リンク先を指定する事ができます。

