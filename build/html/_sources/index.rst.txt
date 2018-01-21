.. Sphinx-Help documentation master file, created by
   sphinx-quickstart on Fri Nov 10 16:40:55 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

WebSite-Contents
=======================

本网站致力于Python生态知识的交流和学习，主要包含以下内容:
-----------------------------------------------------------



.. important::

    **Python** : Python是一种解释型、面向对象、动态数据类型的高级程序设计语言。Python由Guido van Rossum于1989年底发明，
    第一个公开发行版发行于1991年。像Perl语言一样, Python 源代码同样遵循 GPL(GNU General Public License)协议。
    Python就为我们提供了非常完善的基础代码库，覆盖了网络、文件、GUI、数据库、文本等大量内容，被形象地称作“内置电池（batteries included）”。
    用Python开发，许多功能不必从零编写，直接使用现成的即可。除了内置的库外，Python还有大量的第三方库，也就是别人开发的，供你直接使用的东西。
    当然，如果你开发的代码通过很好的封装，也可以作为第三方库给别人使用。许多大型网站就是用Python开发的，例如YouTube、Instagram，还有国内的豆瓣。
    很多大公司，包括Google、Yahoo等，甚至NASA（美国航空航天局）都大量地使用Python。
    Python的应用领域：

   * 网站、后台服务
   * 机器学习和深度学习
   * 数据挖掘与分析
   * 大数据ETL工具
   * 网络爬虫
   * 小工具，脚本任务


.. important::

    **机器学习（Machine Learning, ML）** : 是一门多领域交叉学科，涉及概率论、统计学、逼近论、凸分析、算法复杂度理论等多门学科。
    专门研究计算机怎样模拟或实现人类的学习行为，以获取新的知识或技能，重新组织已有的知识结构使之不断改善自身的性能。它是人工智能的核心，
    是使计算机具有智能的根本途径，其应用遍及人工智能的各个领域，它主要使用归纳、综合而不是演绎。


.. important::

    **深度学习（Deep Learning, DL）** : 深度学习的概念源于人工神经网络的研究。含多隐层的多层感知器就是一种深度学习结构。
    深度学习通过组合低层特征形成更加抽象的高层表示属性类别或特征，以发现数据的分布式特征表示。深度学习的概念由Hinton等人于2006年提出。
    基于深度置信网络(DBN)提出非监督贪心逐层训练算法，为解决深层结构相关的优化难题带来希望，随后提出多层自动编码器深层结构。
    此外Lecun等人提出的卷积神经网络是第一个真正多层结构学习算法，它利用空间相对关系减少参数数目以提高训练性能。深度学习是机器学习
    中一种基于对数据进行表征学习的方法。观测值（例如一幅图像）可以使用多种方式来表示，如每个像素强度值的向量，或者更抽象地表示成一系列边、
    特定形状的区域等。而使用某些特定的表示方法更容易从实例中学习任务（例如，人脸识别或面部表情识别）。深度学习的好处是用非监督式或半监督式
    的特征学习和分层特征提取高效算法来替代手工获取特征。深度学习是机器学习研究中的一个新的领域，其动机在于建立、模拟人脑进行分析学习的神经网络，
    它模仿人脑的机制来解释数据，例如图像，声音和文本。同机器学习方法一样，深度机器学习方法也有监督学习与无监督学习之分．不同的学习框架下建立的学
    习模型很是不同．例如，卷积神经网络（Convolutional neural networks，简称CNNs）就是一种深度的监督学习下的机器学习模型，
    而深度置信网（Deep Belief Nets，简称DBNs）就是一种无监督学习下的机器学习模型。




.. important::

    **Sphinx** : Sphinx 是一种文档工具，它可以令人轻松的撰写出清晰且优美的文档, 由 Georg Brandl 在BSD 许可证下开发。
    新版的Python文档 就是由Sphinx生成的， 并且它已成为Python项目首选的文档工具，同时它对 C/C++ 项目也有很好的支持；
    并计划对其它开发语言添加特殊支持。 它采用reStructuredText语法下面列出了其良好特性,这些特性在Python官方文档中均有体现:

   * 丰富的输出格式: 支持 HTML (包括 Windows 帮助文档), LaTeX (可以打印PDF版本), manual pages（man 文档）, 纯文本
   * 完备的交叉引用: 语义化的标签,并可以自动化链接函数,类,引文,术语及相似的片段信息
   * 明晰的分层结构: 可以轻松的定义文档树,并自动化链接同级/父级/下级文章
   * 美观的自动索引: 可自动生成美观的模块索引
   * 精确的语法高亮: 基于 Pygments 自动生成语法高亮
   * 开放的扩展: 支持代码块的自动测试,并包含Python模块的自述文档(API docs)等

.. important::

    **rsStructureText** : reStructuredText是扩展名为.rst的纯文本文件，含义为重新构建的文本 ，
    rst 文件是轻量级标记语言的一种，被设计为容易阅读和编写的纯文本，并且可以借助 Docutils这样的程序进行文档处理，
    也可以转换为HTML或 PDF等多种格式，或由Sphinx-Doc这样的程序转换为LaTex 、Man等更多格式。

    ``* 本网站内容即由rst语法编写，由Sphinx编译而成``




Contents
--------
.. toctree::
   :maxdepth: 1

   python
   MechineLearning
   DeepLearning
   sphinxEnv
   rsStructuresText














