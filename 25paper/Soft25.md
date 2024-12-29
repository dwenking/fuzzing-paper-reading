# 问题

DBMS 中的内建 SQL 函数是实现数据查询、转换和聚合的重要工具。然而，SQL 函数缺陷可能导致系统崩溃、数据泄露甚至任意代码执行等严重问题。

传统测试方法主要侧重于生成复杂的 SQL 语法结构，未能充分关注 SQL 函数的边界值问题。

# 调研

对3 个流行数据库上的 318 个内置函数的 bug 进行调研分析，主要发现如下：

* 在所研究的具有可识别回溯的 bug 中，约 **70.0% (161/230) 发生在执行阶段**，约 19.6% (45/230) 发生在优化阶段，约 10.4% (24/230) 发生在解析阶段。
* SQL 函数表达式在这些 bug 的 PoC 中总共出现了 508 个。 **最常见的引发错误的 SQL 函数类型是字符串函数（117/508，约 23.0%）和聚合函数（91/508，约 17.9%）。** 超过 40% 的错误是由这两类 SQL 函数引起的。
* 大多数（278/318，约 87.5%）所研究的错误在其错误诱导语句中**包含不超过两个函数表达式**。
* 大约 47.5% (151/318) 的研究 bug 依赖于表创建和数据插入，大约 41.5% (132/318) 可以在不依赖任何表的情况下导致 DBMS 崩溃，大约 11.0% (35/318) 依赖于未插入数据的特定表。

Bug 的 Root Cause 总结如下：

* 87.4% (278/318) 的错误是由于参数边界值处理不当引起的，这可以被视为内置 SQL 函数错误的主要原因。
  * **边界字面值（Boundary Literal Values）**：如极端数值、空字符串、NULL 等。
  * **边界类型转换（Boundary Type Casting）**：由于不正确的类型转换引发问题。
  * **嵌套函数返回值（Boundary Return Values from Nested Functions）**：嵌套函数返回的特殊值触发问题。
* 其他不常见的原因，如配置、复杂语法结构、特定表定义

# 方案

调研表明，SQL 函数错误的主要原因是对参数边界值的错误处理，然而，现有的测试框架无法有效地构建SQL函数参数的边界值并检测SQL函数的错误：

* 首先，它们中的大多数随机生成文字值，而不考虑 SQL 函数表达式的边界值。
* 其次，他们专注于构建语法和语义上正确的语句，但经常忽略无效的类型转换。
* 第三，它们中的大多数生成具有各种关键字和子句的复杂 SQL 结构，而忽略嵌套函数表达式。

针对这种问题，论文总结了 10 种详细boundary-value-generation模式来指导生成 SQL，概括的有三种大类：

* 使用极端字面值作为参数，例如：±0.999…99、±999…99、空字符串、NULL
* 使用类型转换作为参数，包括 CAST 显式转换和UNION 过程中的显式转换，以及将一个函数的计算结果传入另一个函数
* 构造嵌套函数模式

# 实验

* Bug 调研，包括总数，开发者反馈等
* 每一种 Pattern 的 Bug 的案例分析
* 与现有工作的对比，证明能覆盖更多的 function 和相关的 branch