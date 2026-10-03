# 气数资料雷达

本目录用于保存自动化资料雷达发现的**候选研究来源与初步证据说明**。

## 分支

长期工作分支：`research/source-radar`

该分支专门承载资料雷达结果，不直接进入 `dev → test → prod` 发布链，也不作为正文或 Question Contract 的真相源。

## 规则

- 每次运行都先读取 `dev` 当前的 `AGENTS.md`、`README.md`、`METHODOLOGY.md`、`EDITORIAL.md`、开放 Research Issues 与相关 `research/` 文件。
- 只沉淀经过实际核验、值得后续研究的新增来源；普通相关链接、重复来源和搜索摘要不写入。
- 优先服务当前 Question Contract，同时主动寻找反证、竞争解释和能修改既有判断的材料。
- 每条记录至少包含书目信息、来源等级、稳定链接/DOI/ISBN、对应研究问题、关键证据或论点、对当前判断的作用、局限与待核查项。
- 不自动改正文、不改 Question Contract、不发布、不把候选资料冒充正式证据。
- 真正进入专项研究时，由人工或研究任务把选中的材料吸收到对应 `research/<topic>/` 中；不要整分支合并回 `dev`。

## 文件命名

按运行日期记录：

`research/radar/YYYY-MM-DD.md`

同一天再次发现更强资料时，更新当天文件并保留去重后的有效条目。
