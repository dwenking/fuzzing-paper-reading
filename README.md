# fuzzing-paper-reading

Fuzzing相关论文笔记整理，持续更新中。

## Database Theory

* *Analyzing the Impact of Cardinality Estimation on Execution Plans in Microsoft SQL Server(VLDB'23)*: [笔记](23paper/CE23.md), [原文](https://www.vldb.org/pvldb/vol16/p2871-dutt.pdf)

## Data Generation

* *Search-Based Test Data Generation for SQL Queries(ICSE'18)*: [笔记](previous/EvoSql18.md), [原文](https://dl.acm.org/doi/10.1145/3180155.3180202)
* *Touchstone: Generating Enormous Query-Aware Test Databases(ATC'18)*: [笔记](previous/TouchStone18.md), [原文](https://dl.acm.org/doi/10.5555/3277355.3277411)

## Database Testing

### Logic Bug

* *Finding Logic Bugs in Spatial Database Engines via Affine Equivalent Inputs(SIGMOD'24)*: [笔记](24paper/SQuality24.md), [原文](https://dlnext.acm.org/doi/pdf/10.1145/3698810)
* *Understanding and Reusing Test Suites Across Database Systems(SIGMOD'24)*: [笔记](24paper/SQuality24.md), [原文](https://arxiv.org/abs/2410.21731)
* *Detecting Logic Bugs in Database Engines via Equivalent Expression Transformation(OSDI'24)*: [笔记](24paper/EET24.md), [原文](https://jzuming.github.io/paper/osdi24-jiang.pdf)
* *Keep It Simple: Testing Databases via Differential Query Plans(SIGMOD'24)*:  [笔记](24paper/DQP24.md), [原文](https://bajinsheng.github.io/assets/pdf/dqp_sigmod24.pdf)
* *Detecting Metadata-Related Logic Bugs in Database Systems via Raw Database Construction(VLDB'24)*: [笔记](24paper/Radar24.md), [原文](https://dl.acm.org/doi/abs/10.14778/3659437.3659445)
* *Detecting Logic Bugs in Graph Database Management Systems via Injective and Surjective Graph Query Transformation(ICSE'24)*: [笔记](24paper/DetectLogic24.md), [原文](https://yuanchengjiang.github.io/docs/GraphGenie-ICSE24.pdf)
* *PINOLO: Detecting Logical Bugs in Database Management Systems with Approximate Query Synthesis(ATC'23)*: [笔记](23paper/Pinolo23.md), [原文](https://wcphkust.github.io/publications/ATC2023.pdf)
* *Detecting Logic Bugs of Join Optimizations in DBMS(SIGMOD'23)*: [笔记](23paper/TQS23.md), [原文](https://dl.acm.org/doi/10.1145/3588909)

### Crash Bug

* *WINGFUZZ: Implementing Continuous Fuzzing for DBMSs(ATC'24)*: [笔记](24paper/Wing24.md), [原文](http://www.wingtecher.com/themes/WingTecherResearch/assets/papers/paper_from_24/WingFuzz_ATC24.pdf)
* *Towards Generic Database Management System Fuzzing(Security'24)*: [笔记](24paper/Buzz24.md), [原文](https://www.usenix.org/system/files/sec24summer-prepub-7-yang-yupeng.pdf)
* *Sedar: Obtaining High-Quality Seeds for DBMS Fuzzing via Cross-DBMS SQL Transfer(ICSE'24)*: [笔记](24paper/Sedar24.md), [原文](http://www.wingtecher.com/themes/WingTecherResearch/assets/papers/paper_from_24/Sedar_ICSE24.pdf)
* *Mozi: Discovering DBMS Bugs via Configuration-Based Equivalent Transformation(ICSE'24)*: [笔记](24paper/Mozi24.md), [原文](http://www.wingtecher.com/themes/WingTecherResearch/assets/papers/paper_from_24/MOZI_ICSE24.pdf)

### Performance Bug

* *PUPPY: Finding Performance Degradation Bugs in DBMSs via Limited-Optimization Plan Construction(ICSE'25)*: [笔记](25paper/Putty25.md), [原文](http://wingtecher.com/themes/WingTecherResearch/assets/papers/paper_from_25/Puppy_ICSE25.pdf)
* *Finding Performance Issues in Database Engines via Cardinality Estimation Testing(ICSE'24)*: [笔记](24paper/FindPer24.md), [原文](https://arxiv.org/abs/2306.00355)
* *Automatic Detection of Performance Bugs in Database Systems using Equivalent Queries(ICSE'22)*: [笔记](previous/AMOEBA22.md), [原文](https://ieeexplore.ieee.org/document/9793961/)

### Transaction Bug

* *Understanding Transaction Bugs in Database Systems(ICSE'24)*: [笔记](24paper/TXBug.md), [原文](https://dl.acm.org/doi/10.1145/3597503.3639207)
* *Detecting Transactional Bugs in Database Engines via Graph-Based Oracle Construction(OSDI'23)*: [笔记](23paper/DetectTrans23.md), [原文](https://www.usenix.org/system/files/osdi23-jiang.pdf)

## DB Application Testing

* *Data-Oriented Differential Testing of Object-Relational Mapping Systems(ICSE'21)*: [笔记](previous/CYN21.md), [原文](https://ieeexplore.ieee.org/document/9401963)

## Mutation-Based Fuzzing

* *The Mutators Reloaded: Fuzzing Compilers with Large Language Model Generated Mutation Operators(ASPLOS'24)*: [笔记](24paper/Meta24.md), [原文](https://connglli.github.io/pdfs/metamut_asplos24.pdf)
