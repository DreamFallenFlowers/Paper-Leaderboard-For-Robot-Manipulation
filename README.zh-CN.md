# Robot Manipulation Knowledge Base

一个可搜索、可更新、可组合筛选的 robot manipulation 论文排行榜，用来更快地找到真正重要的工作。

[主页地址](https://dreamfallenflowers.github.io/Paper-Leaderboard-For-Robot-Manipulation/) · [English README](./README.md)

## 快速信息

- 收录 **2023-01-01** 到最近一次项目更新时间之间的 robot manipulation arXiv 论文
- 当前覆盖 **11038** 篇论文
- 包含 **76** 个关键词
- 提供 **三种排行方式**：`Overall`、`Hot`、`Newest`
- **每月更新一次**
- **一周内** 开源整套工作流

## 为什么要做这个项目

robot manipulation 的论文增长得太快了。

真正重要的想法，散落在成千上万篇论文里；值得跟踪的路线，常常被论文数量本身淹没；一个方向到底是“已经成为主流”，还是“刚刚开始爆发”，靠肉眼追论文很难判断。

这个项目的目标，就是把这种混乱压缩成一个真正可用的工具：一个领域地图、一个趋势探测器、一个能帮你迅速筛出重点工作的排行榜。

## 主页地址

在线页面：

- https://dreamfallenflowers.github.io/Paper-Leaderboard-For-Robot-Manipulation/

## 本仓库收录了什么

本仓库追踪 **2023-01-01** 以来，arXiv 上与 **robot manipulation** 相关的论文。

- 论文发现来源：**arXiv**
- 引用量来源：**Google Scholar** 缓存结果
- 关键词来源：**自动抽取工作流**

## 三种排行方式

本榜单提供三种视角：

- **Overall**：总引用影响力
- **Hot**：影响力与新鲜度结合后的综合热度
- **Newest**：按发布时间排序

直观理解：

- **Overall** 看的是哪些工作已经真正塑造了这个领域
- **Hot** 看的是哪些工作正在快速升温
- **Newest** 看的是最前沿的新论文

## 关键词筛选

当前榜单包含 **76 个关键词**。

你可以在搜索框里自由组合：

- `a + b`
- `a + b - c`

例如：

- `VLA + world model`
- `reinforcement learning + robotic manipulation - survey`
- `tactile + dexterous manipulation`

这意味着你可以非常快地筛出自己真正想看的细分方向排行。

## 关于关键词的重要说明

本项目的关键词抽取策略是**刻意保守**的。

关键词只提取每篇论文**最核心的贡献**，而不是把论文里所有出现过的技术元素都打上标签。所以，一篇工作可能确实使用了某个标签相关的方法、模块、benchmark 或数据元素，但如果它不是这篇论文的核心贡献，那么这个标签就可能不会被提取出来。

这不是缺陷，而是一个有意的设计选择：我们更希望得到一个**更干净、更适合真实筛选和排行**的标签系统，而不是一个覆盖面看似更大、但语义很松散的标签堆。

## 分数公式

排行榜分数由引用量和论文年龄共同决定。

记：

- `cited_by_count`：缓存得到的 Google Scholar 引用量
- `age_days`：论文发表至今的天数
- `lambda = 0.00075`

则：

- `citation_factor = 1 + ln(1 + cited_by_count)`
- `freshness = exp(-lambda * age_days)`
- `Overall Score = citation_factor`
- `Hot Score = citation_factor * freshness`

含义可以理解为：

- **Overall Score**：对引用量做对数压缩后的总影响力
- **Hot Score**：在总影响力基础上乘上时间衰减，用来突出近期快速上升的论文

## 数据文件

本仓库包含最终发布产物：

- `data/papers.min.json`：网页使用的精简论文数据
- `data/tags.json`：关键词统计
- `data/aliases.json`：搜索别名映射
- `data/stats.json`：站点元信息
- `data/total_ranked.csv`：Overall 排行表
- `data/hot_ranked.csv`：Hot 排行表
- `data/ranked.csv`：完整导出排行表

## 更新计划

本榜单会 **每月更新一次**。

与此同时，我也会在 **一周内** 开源整套工作流，方便你直接复用这套方法，制作你自己领域的 paper leaderboard。
