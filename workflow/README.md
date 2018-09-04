# 团队工作流程规范

## Git Flow

![](http://images2015.cnblogs.com/blog/94928/201607/94928-20160706080812280-1827483538.png)

| 分支类型 | 描述 | protected | 时效 |
|----|----|----|----|----|
| master | 管理对外发布版本，每个commit对一个tag | 是 | 长期 |
| develop | 日常开发汇总 | 是 | 长期 |
| feature | 新功能开发 | 否 | 短期,生于develop,死于develop |
| hotfix | bug修补 | 否 | 短期,生于master,死于develop和master |
| release | 预发布版本测试 | 否 | 短期,生于develop,死于develop和master |

**优点：** 清晰可控；

**缺点：** 相对复杂，需要同时维护两个长期分支，且这个模式是基于"版本发布"的，目标是一段时间以后产出一个新版本；



## Github Flow

![](http://7xt4xp.com1.z0.glb.clouddn.com/blog_work-flow-05.png)

 1. master 开出新分支，不区分功能分支或补丁分支。
 2. 新分支开发完成后，或者需要讨论的时候，就向 master 发起一个 Pull Request。
 3. 项目内人一起评审和讨论你的代码。对话过程中，你还可以不断提交代码。
 4. Pull Request通过，合并进master，原分支就被删除。

**优点：** 简单，适合持续发布的产品；

**缺点：** 合并到master分支并不表示能立刻发布，对于指定时间才能发布的产品，这会导致线上版本落后于master分支；


## 团队 Workflow

| 分支类型 | 描述 | protected | 时效 |
|----|----|----|----|----|
| master | 管理对外发布版本，每个commit对一个tag | 是 | 长期 |
| dev | 日常开发汇总 | 否 | 长期 |
| feature | 新功能开发 | 否 | 短期,生于master,死于dev和master |
| hotfix | bug修补 | 否 | 短期,生于master,死于dev和master |

 1. master 开出新分支，功能分支命名为feature_xxx或补丁分支命名为hotfix_xxx。
 2. 新分支开发完成，向dev分支合并进行日常测试。
 3. 测试完成，新分支就向 master 发起一个 Merge Request。
 4. 团队成员基于Merge Request进行Code Review。
 5. Merge Request通过，合并进master并删除原分支；Merge Request不通过，修改问题点并回到第2步。


## Merge Request说明

 * 一个任务完成才能提交MR；
 * MR必须在一个工作日内被合并或者被拒绝；
 * MR提交之后只允许针对Review发现问题再次提交代码，除非有充足的理由，严禁在同一个MR中再次提交其它任务的代码；


## 目标

 * 提高代码质量；
 * 减少bug数量；
 * 提升团队成员对各个项目的熟悉程度；
 * 学习各自的代码优点，提高团队编程水平；