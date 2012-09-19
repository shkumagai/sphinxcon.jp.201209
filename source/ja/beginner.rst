ビギナー編
==========

.. impressjs:: beginner-1
   :data-x: 0
   :data-y: 0
   :data-scale: 4

   HTMLテーマって何?

.. impressjs:: beginner-2
   :data-x: -1600
   :data-y: -1100
   :data-rotate: -90
   :data-scale: 2

   テーマ【theme】

   .. epigraph::

      * 創作や議論の根本的意図・題目・中心課題など。主題。
      * 〘言〙〔theme〕機能主義言語学の文法理論の用語。(以下略)

      *--- 三省堂 大辞林 第三版 より引用*

.. impressjs:: beginner-3
   :data-x: 1000
   :data-y: 800
   :data-rotate: 90
   :data-scale: 3

   ある意図にしたがって HTML 出力の\
   "見た目" を変更するために\
   必要な材料を一つにまとめたもの

.. impressjs:: beginner-4
   :data-x: 1000
   :data-y: 0
   :data-z: -1000
   :data-rotate: 1000
   :data-scale: 1

   つまるところ

   **HTMLテンプレートとCSSの集まり**

.. impressjs:: beginner-5
   :data-x: -1500
   :data-y: 2000
   :data-z: -500
   :data-rotate: -180
   :data-scale: 3

   どうやって使うの?

.. impressjs:: beginner-6
   :data-x: 2500
   :data-y: 500
   :data-rotate: 90
   :data-scale: 2

   *conf.py* にこんな箇所があります。

   .. code-block:: python

      # -- Options for HTML output -------------------

      # The theme to use for HTML and HTML Help pages.
      # See the documentation for a list of builtin themes.
      html_theme = 'default'

.. impressjs:: beginner-7
   :data-x: -2500
   :data-y: 500
   :data-rotate: -90
   :data-scale: 3

   ここを以下のように編集して...

   .. code-block:: python

      html_theme = "sphinxdoc"

.. impressjs:: beginner-8
   :data-x: 0
   :data-y: -2000
   :data-scale: 1

   Let's make it ;)

   .. code-block:: bash

      $ make html

.. impressjs:: beginner-9
   :data-x: 0
   :data-y: -1200
   :data-scale: 2

   .. code-block:: python

      html_theme = 'default'

   これが...

   .. image:: ../static/image/theme_default.png
      :width: 60%
      :alt: HTML Theme: default

.. impressjs:: beginner-10
   :data-x: 2000
   :data-y: -1200
   :data-scale: 2

   .. code-block:: python

      html_theme = 'sphinxdoc'

   こうなります

   .. image:: ../static/image/theme_sphinxdoc.png
      :width: 60%
      :alt: HTML Theme: sphinxdoc

.. impressjs:: beginner-11
   :data-x: 3000
   :data-y: -1200
   :data-z: -500
   :data-rotate-y: 60
   :data-scale: 2

   カンタンですね!!

.. impressjs:: beginner-12
   :data-x: 2000
   :data-y: -1200
   :data-z: -1200
   :data-rotate-x: 45
   :data-rotate-y: 145
   :data-scale: 2

   他にもこんなビルトインテーマがあります。

.. impressjs:: beginner-13
   :data-x: 1500
   :data-y: -800
   :data-z: -1000
   :data-rotate-x: 90
   :data-rotate-y: 180
   :data-scale: 1

   "agogo"

   .. image:: ../static/image/theme_agogo.png
      :width: 70%
      :alt: HTML Theme: agogo

.. impressjs:: beginner-14
   :data-x: 500
   :data-y: -800
   :data-z: -1000
   :data-rotate-x: 90
   :data-rotate-y: 180
   :data-scale: 1

   "traditional"

   .. image:: ../static/image/theme_trad.png
      :width: 70%
      :alt: HTML Theme: traditional

.. impressjs:: beginner-15
   :data-x: -500
   :data-y: -800
   :data-z: -1000
   :data-rotate-x: 90
   :data-rotate-y: 180
   :data-scale: 1

   "nature"

   .. image:: ../static/image/theme_nature.png
      :width: 70%
      :alt: HTML Theme: nature

.. impressjs:: beginner-16
   :data-x: -1500
   :data-y: -800
   :data-z: -1000
   :data-rotate-x: 90
   :data-rotate-y: 180
   :data-scale: 1

   "haiku"

   .. image:: ../static/image/theme_haiku.png
      :width: 70%
      :alt: HTML Theme: haiku

.. impressjs:: beginner-17
   :data-x: -2500
   :data-y: -800
   :data-z: -1000
   :data-rotate-x: 90
   :data-rotate-y: 180
   :data-scale: 1

   "pyramid"

   .. image:: ../static/image/theme_pyramid.png
      :width: 70%
      :alt: HTML Theme: pyramid

.. impressjs:: beginner-18
   :data-x: -3500
   :data-y: -800
   :data-z: -1000
   :data-rotate-x: 90
   :data-rotate-y: 180
   :data-scale: 1

   組み込みだけでもいろいろとあるので、\
   まずはどんなふうに表示されるのかを\
   ひと通り見てみるといいでしょう。

   `中級者編`_ へ

.. 全体俯瞰

.. impressjs:: overview
   :data-x: 0
   :data-y: 0
   :data-scale: 8

   .. 全体俯瞰表示用のダミーコンテンツです。

   \

.. links

.. _`中級者編`: intermediate.html

.. end of beginner section

