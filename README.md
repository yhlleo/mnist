# mnist
Some samples of the MNIST classifier which are corresponding to the tutorials of the jikexueyuan(https://wiki.jikexueyuan.com/project/tensorflow-zh/).

**构建模块：**

 - `input_data.py`: MNIST数据集下载与解压
 - `mnist.py`: Implements the inference/loss/training pattern for model building
 
**代码测试：**

 - `mnist_softmax.py`: MNIST机器学习入门
 - `mnist_deep.py`: 深入MNIST
 - `fully_connected_feed.py`: TensorFlow运作方式入门
 - `mnist_with_summaries.py`: Tensorboard训练过程可视化

将MNIST数据集，下载后拷贝到文件夹`Mnist_data`中，如果已经配置好`tensorflow`环境，主要的四个测试代码文件，都可以直接编译运行：

 - `mnist_softmax.py`: MNIST机器学习入门
 - `mnist_deep.py`: 深入MNIST
 - `fully_connected_feed.py`: TensorFlow运作方式入门
 - `mnist_with_summaries.py`: Tensorboard训练过程可视化

**`mnist_softmax.py`**运行结果比较简单，就不列举。

**`mnist_deep.py`**迭代运行较为耗时，结果已显示在博客： [深入MNIST code测试](https://blog.csdn.net/yhl_leo/article/details/50624471) 。

**`fully_connected_feed.py`**的运行结果如下（本人电脑为2 CPU，没有使用GPU）：
```
Extracting Mnist_data/train-images-idx3-ubyte.gz
Extracting Mnist_data/train-labels-idx1-ubyte.gz
Extracting Mnist_data/t10k-images-idx3-ubyte.gz
Extracting Mnist_data/t10k-labels-idx1-ubyte.gz
I tensorflow/core/common_runtime/local_device.cc:25] Local device intra op parallelism threads: 2
I tensorflow/core/common_runtime/local_session.cc:45] Local session inter op parallelism threads: 2
Step 0: loss = 2.33 (0.023 sec)
Step 100: loss = 2.09 (0.007 sec)
Step 200: loss = 1.76 (0.009 sec)
Step 300: loss = 1.36 (0.007 sec)
Step 400: loss = 1.12 (0.007 sec)
Step 500: loss = 0.74 (0.008 sec)
Step 600: loss = 0.78 (0.006 sec)
Step 700: loss = 0.69 (0.007 sec)
Step 800: loss = 0.67 (0.007 sec)
Step 900: loss = 0.52 (0.010 sec)
Training Data Eval:
  Num examples: 55000  Num correct: 47532  Precision @ 1: 0.8642
Validation Data Eval:
  Num examples: 5000  Num correct: 4360  Precision @ 1: 0.8720
Test Data Eval:
  Num examples: 10000  Num correct: 8705  Precision @ 1: 0.8705
Step 1000: loss = 0.56 (0.013 sec)
Step 1100: loss = 0.50 (0.145 sec)
Step 1200: loss = 0.33 (0.007 sec)
Step 1300: loss = 0.44 (0.006 sec)
Step 1400: loss = 0.39 (0.006 sec)
Step 1500: loss = 0.33 (0.009 sec)
Step 1600: loss = 0.56 (0.008 sec)
Step 1700: loss = 0.50 (0.007 sec)
Step 1800: loss = 0.42 (0.006 sec)
Step 1900: loss = 0.41 (0.006 sec)
Training Data Eval:
  Num examples: 55000  Num correct: 49220  Precision @ 1: 0.8949
Validation Data Eval:
  Num examples: 5000  Num correct: 4520  Precision @ 1: 0.9040
Test Data Eval:
  Num examples: 10000  Num correct: 9014  Precision @ 1: 0.9014
[Finished in 22.8s]
```

**`mnist_with_summaries.py`**主要提供了一种在Tensorboard可视化方法，首先，编译运行代码：

![tensorboard](https://img.blog.csdn.net/20160219140910928)

运行完毕后，打开终端`Terminal`，输入`tensorboard --logdir=/tmp/mnist_logs`，就会运行出：`Starting TensorBoard on port 6006 (You can navigate to https://localhost:6006)`

然后，打开浏览器，输入链接`https://localhost:6006`：

![tensorboard2](https://img.blog.csdn.net/20160219141246792)

其中，有一些选项，例如菜单栏里包括`EVENTS, IMAGES, GRAPH, HISTOGRAMS`，都可以一一点开查看~

另外，此时如果不关闭该终端，是无法在其他终端中重新生成可视化结果的，会出现端口占用的错误，更多详细信息可以查看英文原文：[TensorBoard: Visualizing Learning](httpss://www.tensorflow.org/versions/master/how_tos/summaries_and_tensorboard/index.html)。

源自博客： [Tensorflow MNIST 数据集测试代码入门](https://https://blog.csdn.net/YhL_Leo/article/details/50614444)

如有纰漏，欢迎指正！
