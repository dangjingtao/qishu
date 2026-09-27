# 《气数》产品草案 v0.1

状态：**探索期 / 可随研究迭代**

## 一、定位

《气数》同时是：

1. 一个长期历史与现实研究专题；
2. 一套开放、版本化的研究工作流；
3. tomz.io 书架中的“研究型书籍”；
4. 可持续发布到公众号的内容源；
5. 一部可能从多年研究中生长出来的书。

它不是：

- 王朝周期论；
- 国家寿命预测器；
- 政治立场宣言；
- AI 自动生成的历史百科；
- 为证明某个当代结论而倒推历史材料的论证工程。

## 二、内容结构

面向读者采用五条路径，而不是暴露仓库目录：

### 王朝｜失去余地之前

中国多个朝代。反复追问：力量如何形成？选择从什么时候开始减少？事件与长期结构各自承担什么作用？

### 世界｜大国怎样改变命运

罗马、奥斯曼、西班牙、英国、法国、苏联、日本、美国等案例按问题选择，不预设统一“帝国生命周期”。

### 机制｜气数怎样形成

可逐步生长的专题：

- 财政能力；
- 军政关系；
- 人口与家庭结构；
- 官僚与国家能力；
- 中央与地方；
- 债务与资产负债表；
- 技术与生产率；
- 改革成本；
- 路径依赖；
- 系统冗余与韧性；
- 社会预期与长期投资。

### 当代｜我们身处哪一页

把经过历史案例检验的方法用于当代国家。

尤其研究中国时，要求：

- 当前资料重新检索；
- 国内外来源交叉验证；
- 不从作者个人观点预设结论；
- 记录证据截止日期；
- 明确事实、解释与判断；
- 不做政治人物/政党排名、背书或选举预测。

### 人生｜一个人的余地

回到个人：

当时代、身体、关系、职业与财富都包含不可控因素，人怎样尽量保留未来选择？

## 三、渠道架构

```text
qishu / dev → test → prod
                  │       │
                  │       ├─ tomz.io：正式阅读 / 研究入口
                  │       ├─ 微信公众号：大众传播版
                  │       └─ Book edition：未来书稿
                  │
                  └─ tomz.io Cloudflare Pages：noindex Preview
```

### GitHub

研究与内容单一真相源：

- 问题；
- 研究卡；
- 资料；
- 竞争解释；
- 母稿；
- 版本历史；
- 发布流水线。

### tomz.io

不是简单镜像 Markdown，而是《气数》的正式数字阅读界面。

第一版只需要四种能力：

1. 书架中的《气数》卡片；
2. 专题首页：核心问题、五条路径、正在追问、最近文章；
3. 文章页：正文优先；
4. 文后研究层：研究札记、主要争议、来源、开放问题、修订记录。

未来再考虑气数图谱、时间轴等，不在 v0.1 预建复杂系统。

### 微信公众号

一等发布渠道，但不是第二份手工维护正文。

公众号版允许：

- 更适合传播的标题；
- 更短的摘要；
- 移动端段落；
- 更文学的开场；
- 精简正文内引用。

必须保持：

- 事实一致；
- 关键判断一致；
- 引用可回溯；
- 完整研究可从 tomz.io / GitHub 找到。

推荐发布链：

```text
research / essay PR
        ↓
      dev
        ↓
      test @ exact SHA
        ↓
tomz.io trusted renderer
(build-time import only)
        ↓
Cloudflare Pages Preview
(noindex / human review)
        ↓
      prod @ exact SHA
        ↓
tomz.io production renderer
        ↓
Cloudflare Pages
```

核心边界：

- `publication.json` 与正文只在 qishu 维护；
- tomz.io 只保留通用 importer / renderer，不保存《气数》正文副本；
- Preview / Production 构建都固定到 qishu 的精确 commit SHA；
- Cloudflare Pages Preview、Cloudflare Pages Production、未来公众号草稿都属于派生输出，不是内容真相源；
- 《气数》真人 Preview 使用 tomz.io 的 External Book Cloudflare Preview，稳定 branch namespace 为 `preview/external-book/qishu`，稳定地址为 `https://preview-external-book-qishu.tomz-io.pages.dev/`；
- GitHub Pages 仅保留 tomz.io 的 `/tomz-io/` base 与静态输出兼容性验证，不再承担《气数》真人 Preview；
- 当前已实现 test → External Book Cloudflare Preview 的 importer / workflow 基础能力；prod → Cloudflare 的外部 Book 正式发布链仍待后续实现。

公众号正式群发保留人工确认。

## 四、首页表达（候选）

### 书名

**气数**

### 副题

**一个人与一个国家，还剩多少种选择**

### 项目宣言（候选）

> 我们知道上一页叫什么，却不知道自己身处的这一页，未来会被怎样命名。
>
> 《气数》研究王朝、大国、制度与个人：当下一场风暴尚未到来，我们手里还剩多少余地。

### 状态文案

**连载中 · 我们还不知道结论。**

## 五、v0.1 仓库结构

先保持克制：

```text
qishu/
├── README.md
├── AGENTS.md
├── METHODOLOGY.md
├── EDITORIAL.md
├── docs/
│   └── PRODUCT_DRAFT.md
├── research/
│   └── seeds/
│       └── preface.md
├── essays/          # 第一篇真正开始时再建
├── cases/           # 有第二个案例再抽象
├── mechanisms/      # 有复用需求再抽象
└── library/         # 引用体系确定后再建设
```

不要因为“未来可能需要”就提前制造复杂 schema。

## 六、第一辑（候选，不视为承诺）

第一辑的目的不是覆盖五卷，而是验证这种写作是否成立。

可能包括：

1. **序｜气数：历史为什么总在下一页突然转弯**
2. **高适｜一个人的气数**
3. **盛唐｜安史之乱真的毁掉了大唐吗**
4. **治理｜为什么能干的治理者也可能无能为力**
5. **世界｜帝国不一定会死，有些国家只是换了一种活法**
6. **研究说明｜我们如何谈气数，而不替历史算命**

具体选题须经过漫谈和资料研究后再锁定。

## 七、需要以后回答的问题

- tomz.io 的 Research Book 数据协议是什么？
- 母稿和微信版采用自动转换还是显式渠道 override？
- 引用最终使用 CSL-JSON、BibTeX 还是其他方案？
- GitHub Issue 是否成为每篇文章的研究契约？
- 外部贡献是否开放？开放到资料纠错、研究讨论还是正文 PR？
- 文章达到什么成熟度后，才进入未来书稿？
