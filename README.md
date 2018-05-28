# Tensorflow tips 

**How to install the tensorflow

http://www.tensorflownews.com/2018/03/28/tensorflow-windows-install/
在安装Tensorflow前，我们要先安装Anaconda，因为它集成了很多Python的第三方库及其依赖项，方便我们在编程中直接调用。

## Anaconda 安装
下载安装anaconda的小插曲
https://blog.csdn.net/vict_99/article/details/79432950
1、在官网上找到windows的32位的下载（毕竟是八年前的老本了，另一个本装的64位），结果网站上出现问题，没有成功下载
2、万能的网络，终于找到可以下载的清华镜像地址：https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/

安装好Anaconda后，我们便可以打开命令提示符，输入pip install Tensorflow完成Tensorflow的安装。
之后我们进入python可执行界面，输入import tensorflow as tf来检验Tensorflow是否安装成功。如果没有报任何错，可以正常执行，则说明Tensorflow已经安装成功。

Jupyter Notebook是一款非常好用的交互式开发工具，不仅支持40多种编程语言，还可以实时运行代码、共享文档、数据可视化、支持markdown等，适用于机器学习、统计建模数据处理、特征提取等多个领域。尤其在Kaggle、天池等数据科学竞赛中，快捷、实时、方便的优点深受用户欢迎。本书后边的章节中，均将以Jupyter Notebook作为开发环境，运行Tensorflow程序。

## pycharm应用
在pycharm下调用anaconda 和tensorflow
intepreter 设置 anaconda 的安装路径， 例如在 D/app/ananconda/python/.exe
解决 updating indeice 问题， 在  setting 中 的 project： 找到相应prokect 把不想的content 添加到excluded 。


**More about the tensorflow:**
tensorflow usefull info:

1. use tf.Variable for trainable variables such as weights (W) and biases (B) for your model,  tf.variables will be trained (modified) as the result of this training.
2. tf.placeholder is used to feed actual training examples 

Difference: 
The difference is that with tf.Variable you have to provide an initial value when you declare it. With tf.placeholder you don't have to provide an initial value and you can specify it at run time with the feed_dict argument inside Session.run.

## 一些常用的数据类型：
函数constant有五个参数，分别为value，name，dtype，shape和verify_shape。其中value为必选参数，其它均为可选参数。Value为常量的具体值，可以是一个数字，一维向量或是多维矩阵。Name是常量的名字，用于区别其它常量。Dtype是常量的类型，Shape是指常量的维度，我们可以自行定义常量的维度。

还提供了一些常见常量的初始化，如：tf.zeros、tf.ones、tf.fill、tf.linspace、tf.range等，均可以快速初始化一些常量。例如：我们想要快速初始化N维全0的矩阵，我们可以利用tf.zeros进行初始化


## 分布式
我们需要了解分布式TensorFlow中ps、worker、in-graph、between-graph、synchronous training和asynchronous training的概念。首先ps是整个训练集群的参数服务器，保存模型的Variable，worker是计算模型梯度的节点，得到的梯度向量会交付给ps更新模型。in-graph与between-graph对应，但两者都可以实现同步训练和异步训练，in-graph指整个集群由一个client来构建graph，并且由这个client来提交graph到集群中，其他worker只负责处理梯度计算的任务，而between-graph指的是一个集群中多个worker可以创建多个graph，但由于worker运行的代码相同因此构建的graph也相同，并且参数都保存到相同的ps中保证训练同一个模型，这样多个worker都可以构建graph和读取训练数据，适合大数据场景。同步训练和异步训练差异在于，同步训练每次更新梯度需要阻塞等待所有worker的结果，而异步训练不会有阻塞，训练的效率更高，在大数据和分布式的场景下一般使用异步训练。


纵观大数据处理和资源调度行业，Hadoop生态俨然成为了业界的标准，通过MapReduce或Spark接口来处理数据，用户通过API提交任务后由Yarn进行统一的资源分配和调度，不仅让分布式计算成为可能，也通过资源共享和统一调度平的台极大地提高了服务器的利用率。很遗憾TensorFlow定义是深度学习框架，并不包含集群资源管理等功能，但开源TensorFlow以后，Google很快公布了Google Cloud ML服务，我们从Alpha版本开始已经是Cloud ML的早期用户，深深体会到云端训练深度学习的便利性。通过Google Cloud ML服务，我们可以把TensorFlow应用代码直接提交到云端运行，甚至可以把训练好的模型直接部署在云上，通过API就可以直接访问，也得益于TensorFlow良好的设计，我们基于Kubernetes和TensorFlow serving实现了Cloud Machine Learning服务，架构设计和使用接口都与Google Cloud ML类似。


## Epochs, batch, batch_size, iteration 
只有在数据很庞大的时候（在机器学习中，几乎任何时候都是），我们才需要使用 epochs，batch size，迭代这些术语，在这种情况下，一次性将数据输入计算机是不可能的。因此，为了解决这个问题，我们需要把数据分成小块，一块一块的传递给计算机，在每一步的末端更新神经网络的权重，拟合给定的数据

**EPOCHS

当一个完整的数据集通过了神经网络一次并且返回了一次，这个过程称为一个 epoch。
然而，当一个 epoch 对于计算机而言太庞大的时候，就需要把它分成多个小块。


**BATCH 是什么？

在不能将数据一次性通过神经网络的时候，就需要将数据集分成几个 batch。
正如将这篇文章分成几个部分，如介绍、梯度下降、Epoch、Batch size 和迭代，从而使文章更容易阅读和理解。

理解迭代，只需要知道乘法表或者一个计算器就可以了。迭代是 batch 需要完成一个 epoch 的次数。记住：在一个 epoch 中，batch 数和迭代数是相等的。
比如对于一个有 2000 个训练样本的数据集。将 2000 个样本分成大小为 500 的 batch，那么完成一个 epoch 需要 4 个 iteration。

一次epoch=所有训练数据forward+backward后更新参数的过程。
一次iteration=[batch size]个训练数据forward+backward后更新参数过程。



**Instruction of the writing rules

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


**Bold** and _Italic_


### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Winowang/Winowang.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

http://blog.jobbole.com/105602/

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
