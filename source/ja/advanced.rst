上級者編
========

.. impressjs:: advanced-1
   :data-x: -2000
   :data-y: 0
   :data-scale: 1

   テーマを自分で作ってみたいけど、

   どういう作りなの？

.. impressjs:: advanced-2
   :data-x: -1000
   :data-y: 0
   :data-scale: 1

   HTML テーマの構造

   .. code-block:: none

      pyconjp
          + theme.conf
          + layout.html
              :
          + static
              + pyconjp.css_t
              + pyconjp_2012_logo.png

.. impressjs:: advanced-3
   :data-x: 0
   :data-y: 0
   :data-scale: 1

   * ``theme.conf`` ファイル
   * テンプレートファイル
   * 静的ファイル

     * スタイルシート
     * 画像

.. impressjs:: advanced-4
   :data-x: 1000
   :data-y: 0
   :data-scale: 1

   theme.conf

   .. code-block:: ini

      [theme]
      inherit = basic
      stylesheet = pyconjp.css_t
      pygments_style = friendly

      [options]
      rightsidebar = false

.. impressjs:: advanced-5
   :data-x: -2000
   :data-y: -800
   :data-scale: 1

   [theme] セクション

   * inherit
   * stylesheet
   * pygments_style

.. impressjs:: advanced-6
   :data-x: -1000
   :data-y: -800
   :data-scale: 1

   [theme] セクション - inherit

   * 継承元テーマを指定します
   * 継承しない場合は ``none`` を指定
   * 組み込みテーマを部分的に変更したい場合に便利

.. impressjs:: advanced-7
   :data-x: 0
   :data-y: -800
   :data-scale: 1

   [theme] セクション - stylesheet

   * 適用するスタイルシート名を指定
   * "静的テンプレート" ファイル名でもOK
   * conf.py の html_style オプション (文字列) で上書き可能

.. impressjs:: advanced-8
   :data-x: 1000
   :data-y: -800
   :data-scale: 1

   [theme] セクション - pygments_style

   * Code Block のスタイル
   * Pygments のスタイル名を指定
   * conf.py の pygments_style オプション (文字列) で上書き可能

.. impressjs:: advanced-9
   :data-x: 2000
   :data-y: -800
   :data-scale: 1

   [options] セクション

   * テーマ固有のオプションを記述
   * 「オプション名 = 値」
   * conf.py の html_theme_options オプション (辞書) で上書き可能

.. impressjs:: advanced-10
   :data-x: 2000
   :data-y: 800
   :data-rotate: 180
   :data-scale: 1

   テンプレートファイル

   .. code-block:: jinja

      {#
          default/layout.html
          ~~~~~~~~~~~~~~~~~~~

          Sphinx layout template for the default theme.

          :copyright: Copyright 2007-2011 by the Sphinx team, see AUTHORS.
          :license: BSD, see LICENSE for details.
      #}
      {% extends "basic/layout.html" %}

      {% if theme_collapsiblesidebar|tobool %}
      {% set script_files = script_files + ['static/sidebar.js'] %}
      {% endif %}

.. impressjs:: advanced-11
   :data-x: 1000
   :data-y: 800
   :data-rotate: 180
   :data-scale: 1

   テンプレートファイル

   * Jinja2 のテンプレート
   * テンプレートを指定しない場合は、
     継承元のテンプレートをそのまま利用します

.. impressjs:: advanced-12
   :data-x: 0
   :data-y: 800
   :data-rotate: 180
   :data-scale: 1

   静的ファイル

   * スタイルシート
   * 画像ファイル (.jpg, .png 等)

.. impressjs:: advanced-13
   :data-x: -1000
   :data-y: 800
   :data-rotate: 180
   :data-scale: 1

   スタイルシート

   * static template を使えます

.. impressjs:: advanced-14
   :data-x: -2000
   :data-y: 800
   :data-rotate: 180
   :data-scale: 1

   static template って何？

   * 静的ファイルのテンプレート化
   * make html する時に、値を埋め込めます

.. impressjs:: advanced-15
   :data-x: -2000
   :data-y: 1200
   :data-z: -400
   :data-rotate-x: -90
   :data-scale: 1

   Example

.. impressjs:: advanced-16
   :data-x: -1000
   :data-y: 1200
   :data-z: -400
   :data-rotate-x: -90
   :data-scale: 1

   pyconjp.css_t

   .. code-block:: guess

             :
      div.sphinxsidebar {
          margin: 0;
          padding: 0.5em  15px 15px 0;
          width: {{ theme_sidebarwidth|toint - 20 }}px
          float: right;
          font-size: 1em;
          text-align: left;
      }
             :

   書き方:

   .. code-block:: none

      * オプション名に theme_ プレフィクスを付ける
      * 置換したい箇所に {{ , }} を使って埋め込む

.. impressjs:: advanced-17
   :data-x: 0
   :data-y: 1200
   :data-z: -400
   :data-rotate-x: -90
   :data-scale: 1

   theme.conf

   .. code-block:: guess

      [theme]
      inherit = basic
      stylesheet = pyconjp.css_t
      pygments_style = sphinx

      [options]
      sidebarwidth = 170

.. impressjs:: advanced-18
   :data-x: 1000
   :data-y: 1200
   :data-z: -400
   :data-rotate-x: -90
   :data-scale: 1

   pyconjp.css

   .. code-block:: guess

             :
      div.sphinxsidebar {
          margin: 0;
          padding: 0.5em  15px 15px 0;
          width: 150px
          float: right;
          font-size: 1em;
          text-align: left;
      }
             :

   \

   .. code-block:: none

      * 数値だけではなく、文字列も OK
      * HTML テンプレートと同様にフィルタも使えます

.. impressjs:: advanced-19
   :data-x: -2000
   :data-y: 1200
   :data-z: -1200
   :data-rotate-x: -90
   :data-scale: 1

   これらを一つのディレクトリに入れます

   .. code-block:: none

      pyconjp
          + theme.conf
          + layout.html
               :
          + static
              + pyconjp.css_t
              + pyconjp_2012_logo.png

.. impressjs:: advanced-20
   :data-x: -1000
   :data-y: 1200
   :data-z: -1200
   :data-rotate-x: -90
   :data-scale: 1

   このディレクトリを Sphinx の

   ドキュメントルートに置きます。

   .. code-block:: none

      some_document
          + static
          + _templates
          + conf.py
          + index.rst
          + pyconjp     <-- New!

.. impressjs:: advanced-21
   :data-x: 0
   :data-y: 1200
   :data-z: -1200
   :data-rotate-x: -90
   :data-scale: 1

   *conf.py* でテーマのパスを指定します。これで make html すると。。。

   .. code-block:: python

      # Add any paths that contain custom themes here, relative to
      # this directory.
      html_theme_path = ["."]

   * *conf.py* からの相対パスで指定できます。

.. impressjs:: advanced-22
   :data-x: 1000
   :data-y: 1200
   :data-z: -1200
   :data-rotate-x: -90
   :data-scale: 1

   自作テーマのドキュメントが！！

   （下の画像はイメージです）

   .. image:: ../static/image/theme_bizstyle.png
      :width: 60%
      :alt: HTML Theme: sphinxjp.themes.bizstyle

.. impressjs:: advanced-23
   :data-x: 2000
   :data-y: 1200
   :data-z: -1200
   :data-rotate-x: -90
   :data-scale: 1

   今日の内容は `HTML テーマサポート`_ のページに

   書かれているものです。

   公式ドキュメントを参考に、色々と触ってみてください。

.. 全体俯瞰

.. impressjs:: overview
   :data-x: 0
   :data-y: 0
   :data-scale: 8

   .. 全体俯瞰表示用のダミーコンテンツです。

   \

.. links

.. _`HTML テーマサポート`: http://sphinx.pocoo.org/theming.html

.. end of advanced
