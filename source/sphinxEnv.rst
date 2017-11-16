Sphinx 环境搭建
===============


安装Python
-----------



* 下载 `Python安装包 <https://www.python.org/ftp/python/3.6.3/python-3.6.3-amd64.exe>`_


* 安装Pyhton：

   运行该 ``exe`` 文件，按照提示进行安装，可根据需要选择相应的安装路径，本例安装路径为：``D:\Tools\LANG\Python\python-3.6.3`` 。


修改缓存目录
------------

    用户若直接按默认方式安装，可跳过此步骤，则Pip缓存会默认放在 ``C:\Users\$username\AppData\Local\pip\cache`` 目录下，而第三方工具会被安装在 ``$PYTHON_HOME\Lib\site-packages`` 目录下。
    本例为了将Pip缓存目录以及第三方软件包site-packages分离出来，选择以下安装方式：

  ``注:`` ``username`` 为当前用户名

* 新建以下目录：

  ``E:\Data\PBT\Python``

  ``E:\Data\PBT\Python\Pip``

  ``E:\Data\PBT\Python\Python36``

* 新建以下目录及文件：

  ``C:\Users\$username\pip``

  ``C:\Users\$username\pip\pip.ini``


* ``pip.ini`` 文件内容如下：

  ::

    [global]
    timeout = 60
    cache-dir = E:\Data\PBT\Python\Pip

    [list]
    format = columns

    [install]
    user = true

    [download]
    dest = E:\Downloads



创建环境变量
--------------

* 新增以下环境变量:

  ``PYTHONUSERBASE:    E:\Data\PBT\Python``

  ``PYTHON_HOME:       D:\Tools\LANG\Python\python-3.6.3``

  ``PYTHON_USER_HOME:  E:\Data\PBT\Python\Python36``

  ``注：若按默认方式则只需添加相应的PYHTON_HOME环境变量``

* Path变量新增以下内容:


  ``%PYTHON_HOME%;%PYTHON_HOME%\Scripts;``


安装Sphinx
-----------


* 运行Pip，安装Sphinx:

  ::
   
    pip install sphinx


* pip将下载sphinx及其依赖包，并进行安装:

   pip的缓存目录为：``E:\Data\PBT\Python\Pip``

   sphinx等第三方包目录：``E:\Data\PBT\Python\Python36\site-packages``

   sphinx等脚本及程序目录：``E:\Data\PBT\Python\Python36\Scripts``


安装PyCharm
---------------

* 下载 `PyCharm <https://www.jetbrains.com/pycharm/download/download-thanks.html?platform=windows&code=PCC>`_ 安装包，并按照提示安装:

   本例安装路径为：``D:\Tools\PyCharm`` ，可根据需要选择相应的安装路径。

``注: 若按默认安装方式,可略过以下步骤，则PyCharm的配置文件会在C:\Users\john\.PyCharmCE目录下``

* 新建以下目录：

  ``E:\Data\Tools\PyCharm``

* 编辑配置文件

  ``D:\Tools\PyCharm\bin\idea.properties``

* 新增以下两行：
  ::

      idea.config.path=E:/Data/Tools/PyCharm/config
      idea.system.path=E:/Data/Tools/PyCharm/system



Sphinx初探
------------

* 创建Sphinx项目

  Sphinx提供了一个脚本 ``sphinx-quickstart`` ，该脚本能够通过简单的向导来生成工程文件及目录。
  打开PyCharm，新建工程，填写工程名称，如 ``SphinxHelp``，在PyCharm的Terminal下执行 ``sphinx-quickstart`` 命令，或者通过
  ``Tools->Sphinx Quickstart`` 工具来创建一个工程，按照Terminal的提示，填入相应的信息：

  .. code-block:: bash

    > Root path for the documentation [.]
    > Separate source and build directories (y/n) [n]: y
    > Name prefix for templates and static dir [_]:
    > Project name: Sphinx-Help
    > Author name(s): Fengj
    > Project version: 1.0
    > Project release [1.0]:
    > Project language [en]:
    > Source file suffix [.rst]:
    > Name of your master document (without suffix) [index]:
    > Do you want to use the epub builder (y/n) [n]:
    > Create Makefile? (y/n) [y]:
    > Create Windows command file? (y/n) [y]:


  工程创建完成后会在当前工程目录 ``SphinxHelp`` 下生成一些目录及文件：

  ::

    SphinxHelp
       |
       |
       |-----make.bat                Windows下编译脚本
       |
       |-----Makefile                Linux下编译脚本
       |
       |-----build                   执行编译之后产生的文件所在目录
       |
       |-----source                  项目源文件目录
                |
                |
                |----conf.py         项目配置文件
                |----index.rst       项目主框架文件
                |----_static         静态文件存放目录
                |----_templates      模板存放目录



* 编译运行

  执行 ``make html`` 命令后，会在 ``build`` 目录下生成 ``doctrees`` 和 ``html`` 目录，生成的html文件就在该目录下。
  Sphinx可以连接多个文件到单个层次结构的文件，在主文件 ``index.rst`` 中有如下内容：
::

    .. toctree::
        :maxdepth: 2

        sphinxEnv               新增的rst文件名称
        rsStructuresText        新增的rst文件名称

在该标识符下，添加新增的 ``rst`` 文件名称（不用加后缀）,就可以将多个文件组织起来，每次执行 ``make html`` 命令之后就生成相应的html文件

* 更换主题

Sphinx有很多 `内置主题 <http://www.sphinx-doc.org/en/stable/theming.html#builtin-themes>`_ ，不同的主题会有不同的显示效果，本例采用 ``sphinx_rtd_theme`` 主题，可使用 ``pip install sphinx_rtd_theme``
安装，并在 ``conf.py`` 文件中添加如下配置项:
::

    import sphinx_rtd_theme
    html_theme = "sphinx_rtd_theme"
    html_theme_path = [sphinx_rtd_theme.get_html_theme_path()]

该主题的更多使用方式请参考 `sphinx_rtd_theme使用方法 <https://github.com/rtfd/sphinx_rtd_theme>`_




**更多Sphinx使用规范请参考：** `sphinx-doc官网 <http://www.sphinx-doc.org/en/stable/>`_

**reST的语法请参考** `rsStructureText 语法 <http://localhost:63342/SphinxHelp/build/html/rsStructuresText.html>`_