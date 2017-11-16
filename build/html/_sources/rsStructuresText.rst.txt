rsStructureText 语法
======================

简介
----

	``reStructuredText`` 是扩展名为 ``.rst`` 的纯文本文件，含义为 **"重新构建的文本"** ，rst 文件是轻量级标记语言的一种，被设计为容易阅读和编写的纯文本，并且可以借助 ``Docutils`` 这样的程序进行文档处理，也可以转换为 ``HTML`` 或 ``PDF`` 等多种格式，或由 ``Sphinx-Doc`` 这样的程序转换为 ``LaTex`` 、 ``Man`` 等更多格式。

标题
----

	在文本下一行（或上一行）添加至少与文本同宽的符号，即可以使文本成为标题。

示例:
::

	一级标题
	========

	二级标题
	--------


段落
-----
	 
	段落是构成reST文档的基本单位。通过一个或一个以上的 ``空行`` 隔开的文本区块就是一个段落。正如在python里一样，reST中的 ``缩进`` 非常重要。同一段落的多个文本行必须有一样的缩进。

标记
----

	行内标记常用的有:

		字体加粗：左右各两个星号,且 **块前后有空格**

		字体倾斜：左右各一个星号,且 **块前后有空格**

		代码或内容引用：左右各两个反引号,且 **块前后有空格**

	示例:
	::

		AAAA **加粗** AAAA

		AAAA *倾斜* AAAA

		AAAA ``引用`` AAAA

	效果:

		AAAA **加粗** AAAA

		AAAA *倾斜* AAAA

		AAAA ``引用`` AAAA


列表
----

	符号列表 ``*`` 号后空格

	编号列表 数字加点加空格，或者 ``#`` 号加点加空格

	定义列表 术语（只能一行）的下一行 **缩进** ，下一行为定义内容

	示例:
	::

		* item                                                          
		* item                                                          
		* item                                                          
                                                                
		1. item1                                                        
		2. item2                                                        
		3. item3                                                        
                                                                
		#. item4                                                        
		#. item5                                                        
		#. item6               

代码
----

	reST文档中列出代码有三种方式：

	* 行内代码 用 ````code````

	* 简单代码块在代码块的上一个段落后面加2个 ``冒号`` ， ``空一行`` 后开始写代码块，代码块要 ``缩进``

	示例:
        ::

          ::

            class Student(object):
                def __init__(self, name, score):
                    self.name = name
                    self.score = score

                def print_score(self):
                    print('%s: %s' % (self.name, self.score))



	效果:
	::

		class Student(object):
		    def __init__(self, name, score):
		        self.name = name
		        self.score = score

		    def print_score(self):
		        print('%s: %s' % (self.name, self.score))
                         

	* 复杂代码块 使用code-block指导语句，还可以选择列出行号和高亮重点行等

	示例:
        ::

            .. code-block:: python
                :linenos:

                class Student(object):
                    def __init__(self, name, score):
                        self.name = name
                        self.score = score

                    def print_score(self):
                        print('%s: %s' % (self.name, self.score))


	效果：

	.. code-block:: python
		:linenos:

		class Student(object):
		    def __init__(self, name, score):
		        self.name = name
		        self.score = score

		    def print_score(self):
		        print('%s: %s' % (self.name, self.score))

超链接
------
	主要有两种方式：

		* 行内超链接 语法 ```链接文字 <URL>`_``
		* 分开的超链接 用到链接的地方 ```链接文字`_`` , 定义链接的地方 ``.. _链接文字: URL``

		``注：链接URL要加http://前缀``

	
	示例:
	::

		visit `baidu <http://www.baidu.com>`_                           
                                                                
		visit `baidu URL`_  

		.. _baidu URL: http://www.baidu.com  

	效果:

		visit `baidu <http://www.baidu.com>`_                           
                                                                
		visit `baidu URL`_  

		.. _baidu URL: http://www.baidu.com                                                                               
                                  

图片
----
	
    使用 ``image`` 指导语句

    示例:

        ::

            python logo:

            .. image:: ../images/timg.jpg
                :width: 200px


    效果：

        python logo:

        .. image:: ../images/timg.jpg
            :width: 200px



表格
----

	``-`` 用来分隔行，``=`` 用来分隔表头和表体行，``|`` 用来分隔列，``+`` 用来表示行和列相交的节点。

	示例:
	::

		+------------+------------+-----------+
		| Header 1   | Header 2   | Header 3  |
		+============+============+===========+
		| body row 1 | column 2   | column 3  |
		+------------+------------+-----------+
		| body row 2 | Cells may span columns.|
		+------------+------------+-----------+
		| body row 3 | Cells may  | - Cells   |
		+------------+ span rows. | - contain |
		| body row 4 |            | - blocks. |
		+------------+------------+-----------+

	效果:

		+------------+------------+-----------+
		| Header 1   | Header 2   | Header 3  |
		+============+============+===========+
		| body row 1 | column 2   | column 3  |
		+------------+------------+-----------+
		| body row 2 | Cells may span columns.|
		+------------+------------+-----------+
		| body row 3 | Cells may  | - Cells   |
		+------------+ span rows. | - contain |
		| body row 4 |            | - blocks. |
		+------------+------------+-----------+

引用
----
	示例：
	::

		It is methioned by [Ref]_ that python is good.

		.. [Ref] 《Python Programming》

	效果：

		It is methioned by [Ref]_ that python is good.

		.. [Ref] 《Python Programming》

注脚
----

    示例：
    ::

        orem ipsum [#f1]_ dolor sit amet ... [#f2]_

        Footnotes

        .. [#f1] Text of the first footnote.
        .. [#f2] Text of the second footnote.

    效果：

        orem ipsum [#f1]_ dolor sit amet ... [#f2]_

        Footnotes

        .. [#f1] Text of the first footnote.
        .. [#f2] Text of the second footnote.

**更多reST语法请参考：**

* `reStructuredText标记语言规范 <http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html>`_


