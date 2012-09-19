Advanced
========

.. impressjs:: advanced-1
   :data-x: -2000
   :data-y: 0
   :data-scale: 1

   Though I want to create theme,

   what a structure it is?

.. impressjs:: advanced-2
   :data-x: -1000
   :data-y: 0
   :data-scale: 1

   Structure of HTML theme is like this:

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

   * ``theme.conf``
   * HTML template files
   * static files

     * stylesheet(s)
     * images

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

   [theme] Section

   * inherit
   * stylesheet
   * pygments_style

.. impressjs:: advanced-6
   :data-x: -1000
   :data-y: -800
   :data-scale: 1

   [theme] Section - inherit

   * Specify a inherit theme.
   * Specify "none" when inherit no theme.
   * It is useful in case of modifying a builtin theme partly.

.. impressjs:: advanced-7
   :data-x: 0
   :data-y: -800
   :data-scale: 1

   [theme] Section - stylesheet

   * Specify a stylesheet name.
   * It can use the "Static template".
   * html_style option in *conf.py* can overwrite this in runtime.

.. impressjs:: advanced-8
   :data-x: 1000
   :data-y: -800
   :data-scale: 1

   [theme] Section - pygments_style

   * Style of code block.
   * Specify a Pygments style name.
   * pygments_style option in *conf.py* can overwrite this in runtime.

.. impressjs:: advanced-9
   :data-x: 2000
   :data-y: -800
   :data-scale: 1

   [options] Section

   * Define options of theme's own.
   * "OptionName = Value"
   * html_theme_options option in *conf.py* can overwrite this in runtime.

.. impressjs:: advanced-10
   :data-x: 2000
   :data-y: 800
   :data-rotate: 180
   :data-scale: 1

   HTML template file

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

   HTML template file

   * Template file of Jinja2 style.
   * Use template of inherited theme
     if custom template files not exists.

.. impressjs:: advanced-12
   :data-x: 0
   :data-y: 800
   :data-rotate: 180
   :data-scale: 1

   Static files

   * Stylesheet(s)
   * Image files (e.g. \*.jpg, \*.png)

.. impressjs:: advanced-13
   :data-x: -1000
   :data-y: 800
   :data-rotate: 180
   :data-scale: 1

   Stylesheet

   * It can use the "Static template".

.. impressjs:: advanced-14
   :data-x: -2000
   :data-y: 800
   :data-rotate: 180
   :data-scale: 1

   What is the "Static template"?

   * Templating of static files.
   * It can embed values into static files at runtime.

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

   Syntax:

   .. code-block:: none

      * Embed a variable which enclosed with double curly braces.
      * Specify a variable name which prefixed with "theme_".

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

      * It can use not only numeric, also string.
      * It can use filter as same as HTML template.

.. impressjs:: advanced-19
   :data-x: -2000
   :data-y: 1200
   :data-z: -1200
   :data-rotate-x: -90
   :data-scale: 1

   It enclose these files with one directory:

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

   And, put it under the document root of Sphinx:

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

   In *conf.py*, specify the html_theme_path to current directly,
   type "make html", and...

   .. code-block:: python

      # Add any paths that contain custom themes here, relative to
      # this directory.
      html_theme_path = ["."]

   * It can be specify a relatibe path from *conf.py*.

.. impressjs:: advanced-22
   :data-x: 1000
   :data-y: 1200
   :data-z: -1200
   :data-rotate-x: -90
   :data-scale: 1

   You can see a custom themed document :-)

   .. image:: ../static/image/theme_bizstyle.png
      :width: 60%
      :alt: HTML Theme: sphinxjp.themes.bizstyle

.. impressjs:: advanced-23
   :data-x: 2000
   :data-y: 1200
   :data-z: -1200
   :data-rotate-x: -90
   :data-scale: 1

   All the contents of this session are included in
   `HTML theming support`_ section of official document.

   Please refer to document and try to modify a theme.

.. Overview

.. impressjs:: overview
   :data-x: 0
   :data-y: 0
   :data-scale: 8

   \

.. links

.. _`HTML theming support`: http://sphinx.pocoo.org/theming.html

.. end of advanced
