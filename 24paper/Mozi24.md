# 问题

现有的对数据库进行变质测试的方法关注查询之间的等价转换，但这种方法一般需要对不同DBMS进行高度定制，来解决不同DBMS中的方言问题。

# 想法

不关注查询等效，而是**生成具有不同配置的等效DBMS**。这种方法具有更好的可拓展性以及需要更少的人工。

**挑战**：如何选择相关配置 -> 通过查询计划引导。

# 方案

1. 执行查询并将**执行计划**记录在目标DBMS上
2. 根据执行计划动态修改DBMS中的特定配置，以创建不同数据库实例
3. 向等效实例发出相同的查询并比较查询结果，来检查逻辑或性能错误

# 实验

* Bug情况（数据 + 严重性 + Case Study）
* 与现有工具Bug数对比 + 覆盖率对比
* Bug数和覆盖率消融实验
* 用MoZi增强现有工作

# 总结

本文使用配置来构造等价关系。

问题：

* 如何识别查询计划中的配置？是人工确定的吗？
* 不同数据库的配置是否一样？适配这些配置所需要的人工成本？