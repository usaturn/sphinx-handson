Markdown を使うには？
=====================

reST の代わりに Markdown を使うことも可能です。ただし Sphinx ディレクティブが使えない為、 toctree にぶらさげるだけの利用方法となります。

    Python 拡張「recommonmark」のインストール ::

        pip install recommonmark

    conf.py の編集 ::

      from recommonmark.parser import CommonMarkParser

      source_parsers = {
          '.md': CommonMarkParser,
      }

      source_suffix = ['.rst', '.md']

