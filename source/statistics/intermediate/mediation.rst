中介分析
======================

中介分析(mediation analysis)是一种统计方法，用于检验一个变量（中介变量）是否在另外两个变量（自变量和因变量）之间起中介作用的过程。

定义和公式
----------------

中介分析主要关注的是“通过什么途径”一个变量影响另一个变量。公式化地，可以表示为：

- 总效应：\(c = c' + ab\)
- 直接效应：\(c'\)
- 间接效应（中介效应）：\(ab\)

其中，\(a\) 是自变量对中介变量的效应，\(b\) 是中介变量对因变量的效应，\(c\) 是自变量对因变量的总效应，\(c'\) 是控制中介变量后自变量对因变量的直接效应。

类型
----

1. **单中介模型**：包含一个中介变量。
2. **多中介模型**：包含多个中介变量。

语言学习领域的案例
----------------------

假设我们想研究学习方法（自变量）对语言测试成绩（因变量）的影响，同时考虑学习动机（中介变量）的作用。

使用SPSS计算
-----------------

1. 打开SPSS并加载数据。
2. 使用PROCESS宏（由Andrew F. Hayes开发）进行中介分析，选择相应的模型号进行分析。
3. 在PROCESS对话框中，指定自变量、因变量和中介变量。
4. 运行PROCESS宏，查看输出的中介效应分析结果。

使用Excel计算
-----------------

Excel本身不支持直接进行中介分析，需要借助于外部统计软件的结果或者手动进行计算：

1. 计算总效应、直接效应和中介效应的相关系数。
2. 使用公式`= INDIRECT EFFECT / TOTAL EFFECT` 来计算中介效应的比例。

使用Python计算
-------------------

.. code-block:: python

    from statsmodels.stats.mediation import Mediation
    import statsmodels.api as sm
    import pandas as pd

    # 加载数据
    data = pd.read_csv('data.csv')
    X = data['study_method']
    M = data['motivation']
    Y = data['test_score']

    # 定义模型
    mediator_model = sm.OLS(M, sm.add_constant(X)).fit()
    outcome_model = sm.OLS(Y, sm.add_constant(pd.concat([X, M], axis=1))).fit()

    # 进行中介分析
    med = Mediation(outcome_model, mediator_model, 'const', 'study_method').fit()
    print(med.summary())

优点
----

1. **深入理解变量间的关系**：中介分析可以揭示变量之间的内在机制。
2. **提高模型的解释力**：通过考虑中介变量，可以更全面地解释变量间的关系。

缺点
----

1. **数据要求高**：需要大量数据来稳定估计中介效应。
2. **假设限制**：中介分析基于线性关系和因果假设，这在某些情况下可能不成立。
