# Robot Manipulation Knowledge Base

[English Version](./README.md)

这是一个面向 **robot manipulation** 领域的论文排行榜项目。它想解决一个非常现实的问题：

**在机器人操作这个快速爆发的方向里，哪些论文最重要、最有影响力、最值得持续跟踪？**

## 主页地址

- GitHub Pages: https://dreamfallenflowers.github.io/Paper-Leaderboard-For-Robot-Manipulation/

## 本仓库收录了什么

本仓库爬取了 **2023-01-01** 到项目最近更新时间之间，arXiv 上与 **robot manipulation** 相关的论文。

- 论文发现来源：arXiv
- 引用量来源：Google Scholar 缓存结果
- 关键词来源：一套自动抽取工作流

因此，它不是一个静态表格，而是一个可以搜索、组合、筛选、持续更新的领域地图。

## 三种排行方式

本榜单提供三套不同的排行方式：

- **Overall**：按总引用影响力排序
- **Hot**：按综合热度排序
- **Newest**：按发布时间排序

其中分数公式为：

- `citation_factor = 1 + ln(1 + cited_by_count)`
- `freshness = exp(-0.00075 * age_days)`
- `Overall Score = citation_factor`
- `Hot Score = citation_factor * freshness`

直观理解就是：

- **Overall** 会突出那些已经真正塑造了这个领域的工作
- **Hot** 会把近期上升很快、正在变得重要的工作顶上来
- **Newest** 则适合你直接追踪最新前沿

## 关键词筛选

当前榜单包含 **76 个关键词**。

你可以自由组合关键词来构造自己想看的细分方向排行，例如：

- `a + b`
- `a + b - c`

也就是说，你可以非常方便地筛出自己关心的方法路线、控制范式、数据设定、world model 工作、VLA 方向、tactile 方向、sim-to-real 方向等等。

## 关于关键词的重要说明

本项目的关键词抽取策略是**刻意保守**的。

关键词只提取每篇论文**最核心的贡献**，而不是把论文里所有出现过的元素都打上标签。因此，有些工作虽然使用了某个标签相关的技术、模块、benchmark 或数据元素，但如果它不是这篇论文的核心贡献，就可能不会被抽取出来。

这不是漏洞，而是一个有意的设计选择：  
我们更希望得到一个**更干净、更可用于真实筛选和排行**的标签系统，而不是一个表面覆盖率更高、但语义很松散的标签堆。

## 更新计划

本榜单计划 **每月更新一次**。

与此同时，我也会在 **一周内** 开源整套工作流，方便你直接复用这套方法，制作你自己领域的 paper leaderboard。

## 数据文件

本仓库当前包含最终发布产物：

- `data/papers.min.json`：网页使用的精简论文数据
- `data/tags.json`：关键词统计
- `data/aliases.json`：搜索别名映射
- `data/stats.json`：站点元信息
- `data/total_ranked.csv`：Overall 排行表
- `data/hot_ranked.csv`：Hot 排行表
- `data/ranked.csv`：完整导出排行表

## 为什么要做这个项目

robot manipulation 方向的论文增长得太快了。  
真正重要的想法，往往淹没在海量新论文里。

我希望这个项目成为一个更锋利的工具：  
它不仅告诉你“这个方向有什么”，更告诉你“什么值得看，什么正在变热，什么真正塑造了这个领域”。
