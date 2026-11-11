# China Sourcing Clusters · 中文说明

[English README](README.md)

面向**海外 B2B 买家**的 Agent Skill：给任何一个中国产品，定位它真正的**县域产业带 / 生产基地**，并给出绕开一线城市贸易公司、直达源头工厂的方法。全品类适用，**零售不做**。

## 为什么要做这个

中国制造是按县域产业集群组织的：一个镇往往集中了某个品类的原料、模具、加工、表面处理、包装和物流。但海外买家几乎看不到它们。

英文搜索、B2B 平台排名、付费展位和展会摊位，基本被上海、深圳、广州、北京、杭州的出口贸易公司占据——只有他们投英文网站、SEO、平台广告、配英文销售。产业带里的工厂通常不做海外推广，很多连英文网站都没有，只通过国内批发市场、本地代理商，或给贸易公司做代工出货。

所以老外用英文搜 "Chinese manufacturer of X"，命中中间商是**结构性的信息不对称**，不是搜索技巧问题。解法是先定地理：知道产品在哪个县/镇生产，才能用中文搜、按注册地筛、按工厂的逻辑去谈。

## 能做什么 / 不做什么

**做**：全品类定位产区（省 / 市 / 县 / 镇）并解释成因；区分「产地集群 / 批发市场 / 展厅办公室」；按"能否触达集群工厂"给渠道排序；生成可直接粘贴的中文检索词；诊断工厂 vs 贸易公司并给出绕行路径；产出询盘、核验清单、可比报价打分表。

**不做**：零售、B2C、一件代发、单件购买、个人消费；真实工厂名录 / 联系方式 / 实时价格 / MOQ / 运费；验厂或证书真伪结论；法律、合同、关税、制裁、出口管制、认证与 IP 意见；代发询盘、下单、付款、验货；抓取或绕过登录 / 验证码 / 反爬。

**零依赖**：不需要 API key、不联网、无脚本、无遥测，纯 Markdown，离线可用。所有示例数据标注 `synthetic`，不硬编码汇率、运价、费率、平台标签、展会档期和标准版本号；每个参考文件带 `Last verified`。

## 安装与测试

仓库根目录**就是** skill 目录（`SKILL.md` 在顶层）。解压后整个文件夹拷进对应目录即可：

| 智能体 | 目录 | 调用 |
| --- | --- | --- |
| Codex | `~/.codex/skills/` 或项目 `.codex/skills/` | `$china-sourcing-clusters` |
| OpenClaw | `~/.openclaw/skills/` 或工作区 skills 目录 | 自动触发 / 按名称 |
| Claude Code | `~/.claude/skills/` 或 `.claude/skills/` | `/china-sourcing-clusters` |
| WorkBuddy | `~/.workbuddy/skills/` | 自动触发，也可直接导入 SKILL.md |
| Cursor 等 | 客户端 skills 目录（常见 `.agents/skills/`） | 按客户端约定 |

一行安装：`npx skills add jackwangliang/china-sourcing-clusters`（多 skill 仓库加 `--skill china-sourcing-clusters`）。仓库地址：https://github.com/jackwangliang/china-sourcing-clusters

**测试提问**（英文 README 里有 12 条完整清单，后两条应被明确拒绝）：

- `Where in China are stainless steel flanges actually made? I need the factory, not a trading company in Shanghai.`
- `Give me Chinese search terms to find a source factory for socks in Zhejiang.`
- `Is Yiwu the production base for cosmetic brushes?`
- `I want a smart speaker with custom voice dialogue. Which manufacturers can actually change the wake words and the conversation logic?` → 应拆分能力栈：先问清是离线指令词 / 云端大模型 / 语音助手生态哪条路线，再优先路由语音方案层，而不是直接给整机厂
- `I need a batch of meeting recording hardware with a backend. Where are the manufacturers?` → 应说明后台/云服务/数据层**没有产业带答案**、先问清交付模式（现成 SaaS / 对接自有后台 / 私有化整套），采购顺序反转为先定软件与部署、再找硬件产区；不能硬套一个县
- `Where can I buy one espresso machine cheapest for my kitchen?` → 应拒绝（零售）

一个合格回答应该：**说出县/镇**、区分集群与市场、中文检索词原样给出、把产区结论标为 `indicative`、最后给「置信度与未知项」，且绝不编造公司名、价格和占比数字。带固件 / 语音 / AI / APP / 后台定制的产品，还必须先拆出「方案层 / 器件层 / 整机层」，指出哪一层才拥有用户要的能力；一线城市的研发型方案商不能直接判成贸易公司，要看经营范围和产线地址；对后台、云、数据这类层，要明说产区地图不适用并改用交付方式、数据存放、IP 与服务条款筛选。

## 目录

```
SKILL.md                          决策路由、范围、硬性边界
references/cluster-map.md         全品类县域产业带地图
references/channel-matrix.md      渠道矩阵（按工厂密度排序）
references/chinese-search-terms.md  中文检索词构建块
references/bypass-trading-companies.md  中间商诊断、证据、绕行路径
references/verification-rfq.md    询盘、核验、可比报价
assets/rfq-template.md            中英双语空模板
assets/supplier-scorecard.csv     可比报价字段
assets/shortlist-template.csv     候选记录与来源
```

## 仓库与发行

- 仓库：https://github.com/jackwangliang/china-sourcing-clusters
- Release 附带 `china-sourcing-clusters.zip`（根目录为 `china-sourcing-clusters/`，可直接用于 Claude 网页上传）；不要用 GitHub 自动生成的源码 zip，它会多包一层目录。
- 许可：代码 MIT，文档 CC BY 4.0（见 `LICENSE` 与 `CONTRIBUTING.md`）。
- 提交目录索引站时，用英文 README 里的对比表说明与 `1688-sourcing-agent`、`china-factory-search` 等项目的差异。

## 维护

产业带边界会变，平台标签和政策会变。更新条目请引用工信部《中小企业特色产业集群名单》、省级名单或地方工信 / 政府产业介绍，不要引用占比与规模数字，并更新 `Last verified`。详见 [CONTRIBUTING.md](CONTRIBUTING.md)。
