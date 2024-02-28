效应量
=========================

效应量的定义
-------------

效应量（effect size）是一种量化研究结果重要性的统计方法。它描述了两个变量之间的关系强度，或者是一个变量对另一个变量的影响大小。不同于显著性测试（如 p 值）只告诉我们效应是否可能是偶然出现的，效应量则告诉我们效应的实际意义。

常用的效应量指标包括 Cohen's d、Pearson's r 以及 η²（eta squared）等。Cohen's d 通常用于衡量两个独立群体间的平均数差异的标准化大小。Pearson's r 用于衡量两个连续变量间的线性相关程度。而 η² 用于衡量方差分析中一个因素的效应占总方差的比例。

.. math::

   d = \frac{\bar{X}_1 - \bar{X}_2}{s_{pooled}}

.. math::

   r = \frac{\sum (X_i - \bar{X})(Y_i - \bar{Y})}{\sqrt{\sum (X_i - \bar{X})^2 \sum (Y_i - \bar{Y})^2}}

.. math::

   \eta^2 = \frac{SS_{between}}{SS_{total}}

其中，\(\bar{X}_1\) 和 \(\bar{X}_2\) 是两个群体的平均值，\(s_{pooled}\) 是合并标准差。

语言学习领域的案例
-------------------

考虑一个研究案例，研究者想要了解使用不同教学方法（A 方法和 B 方法）对学生英语词汇学习成效的影响。通过收集两组学生在测试中的得分，研究者可以计算 Cohen's d 来量化教学方法的效果大小。

Python 计算效应量
------------------

在 Python 中，我们可以使用 `statsmodels` 库来计算效应量。

.. code-block:: python

   import numpy as np
   from statsmodels.stats import effect_size
   
   group1 = np.array([成绩列表])
   group2 = np.array([成绩列表])
   
   cohen_d = effect_size.cohen_d(group1, group2)
   print(f"Cohen's d: {cohen_d}")

SPSS 计算效应量
----------------

在 SPSS 中，可以通过以下步骤计算效应量：

1. 运行比较测试，例如 t 测试或方差分析。
2. 在输出中查找测试统计量，如 t 值或 F 值。
3. 使用相关公式手动计算效应量，或使用 SPSS 的效应量插件。

Excel 计算效应量
-----------------

在 Excel 中，效应量的计算可以通过手动输入公式完成：

1. 使用 AVERAGE 函数计算各组的平均值。
2. 使用 STDEV.P 函数计算合并标准差。
3. 在新单元格中输入上述公式计算效应量。

总结
-----

效应量是理解研究结果实际意义的重要工具。不同的统计软件和编程语言提供了不同的方法来计算效应量，研究者应根据自己的需求和可用资源选择合适的计算方式。