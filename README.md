## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/Winowang/Winowang.github.io/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).



**Bold** and _Italic_ and 
Tensorflow tips 

How to install the tensorflow

http://www.tensorflownews.com/2018/03/28/tensorflow-windows-install/
在安装Tensorflow前，我们要先安装Anaconda，因为它集成了很多Python的第三方库及其依赖项，方便我们在编程中直接调用。

Anaconda 安装
下载安装anaconda的小插曲
https://blog.csdn.net/vict_99/article/details/79432950
1、在官网上找到windows的32位的下载（毕竟是八年前的老本了，另一个本装的64位），结果网站上出现问题，没有成功下载
2、万能的网络，终于找到可以下载的清华镜像地址：https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/

安装好Anaconda后，我们便可以打开命令提示符，输入pip install Tensorflow完成Tensorflow的安装。
之后我们进入python可执行界面，输入import tensorflow as tf来检验Tensorflow是否安装成功。如果没有报任何错，可以正常执行，则说明Tensorflow已经安装成功。

Jupyter Notebook是一款非常好用的交互式开发工具，不仅支持40多种编程语言，还可以实时运行代码、共享文档、数据可视化、支持markdown等，适用于机器学习、统计建模数据处理、特征提取等多个领域。尤其在Kaggle、天池等数据科学竞赛中，快捷、实时、方便的优点深受用户欢迎。本书后边的章节中，均将以Jupyter Notebook作为开发环境，运行Tensorflow程序。

pycharm应用
在pycharm下调用anaconda 和tensorflow
intepreter 设置 anaconda 的安装路径， 例如在 D/app/ananconda/python/.exe
解决 updating indeice 问题， 在  setting 中 的 project： 找到相应prokect 把不想的content 添加到excluded 。


More about the tensorflow:
tensorflow usefull info:

1. use tf.Variable for trainable variables such as weights (W) and biases (B) for your model,  tf.variables will be trained (modified) as the result of this training.
2. tf.placeholder is used to feed actual training examples 

Difference: 
The difference is that with tf.Variable you have to provide an initial value when you declare it. With tf.placeholder you don't have to provide an initial value and you can specify it at run time with the feed_dict argument inside Session.run.


函数constant有五个参数，分别为value，name，dtype，shape和verify_shape。其中value为必选参数，其它均为可选参数。Value为常量的具体值，可以是一个数字，一维向量或是多维矩阵。Name是常量的名字，用于区别其它常量。Dtype是常量的类型，具体类型可参见图2-2。Shape是指常量的维度，我们可以自行定义常量的维度。

还提供了一些常见常量的初始化，如：tf.zeros、tf.ones、tf.fill、tf.linspace、tf.range等，均可以快速初始化一些常量。例如：我们想要快速初始化N维全0的矩阵，我们可以利用tf.zeros进行初始化




### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Winowang/Winowang.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
