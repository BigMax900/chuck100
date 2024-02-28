正态分布
=========

定义
-------

正态分布，也称为高斯分布，是统计学中最重要的概率分布之一。它描述了许多自然现象和实验结果中的变量分布情况。正态分布具有以下特征：

- 呈钟形曲线。
- 均值、中位数和众数相等。
- 左右对称。
- 曲线在均值处达到最高点。

概率密度函数
----------------

正态分布的概率密度函数为：

.. math::

    f(x | \mu, \sigma^2) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{(x - \mu)^2}{2\sigma^2}}

其中，$x$ 表示随机变量的取值，$\mu$ 表示均值，$\sigma^2$ 表示方差。

常用符号表示
----------------

正态分布常用符号表示为：

- $\mu$：均值
- $\sigma^2$：方差
- $\sigma$：标准差

Python制作的图表
----------------------

你可以使用Python中的`matplotlib`库来绘制正态分布的图表，以下是一个示例代码：

.. code-block:: python

    import numpy as np
    import matplotlib.pyplot as plt

    def normal_distribution(x, mu, sigma):
        return 1 / (sigma * np.sqrt(2 * np.pi)) * np.exp(-(x - mu) ** 2 / (2 * sigma ** 2))

    x = np.linspace(-5, 5, 100)
    mu = 0
    sigma = 1
    y = normal_distribution(x, mu, sigma)

    plt.plot(x, y)
    plt.title('Normal Distribution')
    plt.xlabel('x')
    plt.ylabel('Probability Density')
    plt.grid(True)
    plt.show()

语言学习领域的案例
-------------------------

在语言学习领域，正态分布可以用于描述语言测试的分数分布情况。例如，假设一组学生参加了某种语言能力测试，他们的得分可以被视为一个随机变量，并且这些分数很可能服从正态分布。通过对测试分数进行分析，教育者可以更好地了解学生的语言能力水平分布情况，从而制定更有效的教学策略和课程安排。
