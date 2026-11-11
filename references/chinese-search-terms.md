# Chinese search terms

Last verified: 2026-11-10. Vocabulary and administrative place names are stable. Platform filter labels, badges and policies change; recheck them in the platform's current interface.

## Why this file exists

A cluster factory is usually indexed in Chinese, under a local place name and a process word, not under an English marketing term. A buyer who pastes an English phrase into a global search engine is searching the intermediary's index. Chinese queries are the single highest-leverage step in this skill.

Keep Chinese strings verbatim. They are search inputs, not text to translate away. Give the buyer a short English gloss next to each.

## Query construction

Build four to six queries for each sourcing case:

```
<product word> + <cluster place name> + <factory signal>
<cluster place name> + <product word> + <process word> + 加工/定制
<product word> + 产业带 / 生产基地 / 源头工厂
<product word> + <material or standard word> + 生产厂家
```

Examples of the pattern (illustrative, not supplier data):

| Chinese query | English gloss |
| --- | --- |
| 中山古镇 灯具 生产厂家 | Zhongshan Guzhen, lighting, manufacturer |
| 诸暨大唐 袜子 源头工厂 | Zhuji Datang, socks, source factory |
| 永康 五金 来图加工 定制 | Yongkang, hardware, build-to-print processing, custom |
| 乐清柳市 低压电器 制造商 | Yueqing Liushi, low-voltage electrical, manufacturer |
| 澄海 玩具 产业带 厂家 | Chenghai, toys, industrial cluster, factory |
| 南通 家纺 一手货源 | Nantong, home textiles, first-hand supply |

## Factory-signalling terms

| Chinese | Meaning | Use |
| --- | --- | --- |
| 厂家 / 生产厂家 | manufacturer | Baseline factory signal |
| 源头工厂 / 源头厂货 | source factory / direct-from-factory goods | Strongest common signal on domestic platforms |
| 制造商 | manufacturer | More formal, common on industrial sites |
| 加工 / 来图加工 / 来样加工 | processing / build to drawing / build to sample | Indicates a production workshop |
| 定制 / 定做 | custom-made | Useful for OEM and industrial parts |
| 开模 / 模具 / 注塑 / 冲压 / 锻造 / 机加工 | tooling, moulding, stamping, forging, machining | Process-specific; use when matching by capability |
| 电镀 / 喷涂 / 表面处理 / 组装 | plating, coating, surface treatment, assembly | Upstream step; use with the cluster name |
| 一手货源 | first-hand supply | Domestic wholesale phrasing |
| 产业带 / 生产基地 / 工业园 / 经济开发区 | industrial cluster / production base / industrial park | Pairs with a county name |
| 出厂价 / 工厂价 | ex-works price | Signals a producer quotation, still needs verification |

## Solution-layer terms (smart and connected goods)

For products whose customisation lives in firmware, voice, AI, an app or connectivity, the whole-unit factory is often the wrong target. Use these to find the party that owns the capability. Each term describes a **role**, not a verified company.

| Chinese | English gloss | Use |
| --- | --- | --- |
| 方案商 / 语音方案 / 解决方案 | solution house / voice solution | Finds the firm owning the reference design |
| 模组 / 语音模组 / 语音识别模块 | module / voice module / ASR module | Hardware plus firmware building block |
| 机芯 / 机芯板 / 主板方案 | core board / board solution | Common in audio and AI-toy supply chains |
| 二次开发 / SDK / API 对接 | secondary development / SDK / API integration | Tests whether customisation is actually open to the buyer |
| 自定义唤醒词 / 命令词 / 词条 | custom wake word / command word / voice entry | Offline voice customisation |
| 固件 / 烧录 / OTA 升级 | firmware / flashing / OTA upgrade | Who controls the shipped software |
| 离线语音 / 云端语音 / 大模型语音 | offline voice / cloud voice / LLM voice | Separates the three common technical routes |
| ASR / TTS / 降噪 / 回声消除 / 远场拾音 | ASR / TTS / noise reduction / AEC / far-field pickup | Capability vocabulary for a technical RFQ |
| 公模 / 私模 / ODM / OEM / 贴牌 | public tooling / private tooling / ODM / OEM / private label | Tooling and order type |
| 生态认证 / 语音助手认证 | ecosystem / voice-assistant certification | Ask which scheme and who holds it; never assert validity |
| 软件著作权 / 专利 | software copyright / patent | Reverse-lookup signal for a genuine solution house |
| 后台管理 / 管理后台 / 管理平台 | admin console / management platform | The "backend": device, file, account and audit management |
| 私有化部署 / 本地化部署 / 内网部署 | private / on-premise / intranet deployment | Ask where the service runs and who operates it |
| 软硬一体 / 整机方案 | hardware-plus-software package | Often the real lead supplier when a backend is required |
| 语音转文字 / 会议转写 / 会议纪要 | speech-to-text / meeting transcription / minutes | Backend function vocabulary |
| 说话人分离 / 声纹识别 / 角色分离 | speaker diarisation / voiceprint / role separation | Distinguish from the microphone hardware that enables it |
| 源码交付 / 部署包 / API 对接 / 开放接口 | source handover / deployment package / API integration | What is actually delivered and may be modified |
| 云端 SaaS / 订阅 / 服务费 / SLA | cloud SaaS / subscription / service fee / SLA | Continuing commercial terms, not a one-off unit price |
| 数据存放 / 数据不出域 | data location / data stays on-premise | Ask, never assert a compliance conclusion |

Append 生产厂家 / 厂家 only when the same entity also runs a line. A solution house with no production scope is a legitimate supplier, not a fake factory — label the role instead of forcing it into a factory/trader binary.

Paste-ready examples (illustrative, not supplier data):

| Chinese query | English gloss |
| --- | --- |
| 智能音箱 语音方案 二次开发 深圳 | Smart speaker, voice solution, secondary development, Shenzhen |
| 自定义唤醒词 指令词 离线语音模组 厂家 | Custom wake word, command set, offline voice module, maker |
| AI大模型 语音对话 机芯 方案商 ODM | LLM voice dialogue, core board, solution house, ODM |
| 语音模组 SDK 固件 OTA 定制 | Voice module, SDK, firmware, OTA, custom |
| 智能音箱 公模 私模 ODM 生产厂家 宝安 | Smart speaker, public/private tooling, ODM, manufacturer, Bao'an |
| 会议录音 后台管理 平台 软硬一体 方案商 | Meeting recording, admin console, hardware-plus-software, solution house |
| 私有化部署 会议转写 说话人分离 系统 供应商 | Private deployment, meeting transcription, diarisation, system supplier |
| 阵列麦克风 模组 ODM 生产厂家 深圳 | Mic-array module, ODM, manufacturer, Shenzhen |

Reverse-lookup additions for layered products: `<公司全称> 软件著作权 / 专利`, `<公司全称> 招聘 语音算法 / 嵌入式 / SMT`. Ask both sides `语音方案由谁提供` (who supplies the voice solution) and `量产合作整机厂是哪家` (which factory runs volume production).

## Intermediary-signalling terms

| Chinese | Meaning |
| --- | --- |
| 贸易有限公司 | trading company limited |
| 进出口有限公司 | import & export company limited |
| 商贸有限公司 | commerce / trading company |
| 国际 / 实业 / 供应链 | international / industrial / supply chain (ambiguous, not proof either way) |
| 办事处 / 展厅 / 营销中心 | office / showroom / marketing centre |
| 销售 / 贸易 / 货物进出口 | sales / trade / import-export of goods (typical registered scope of an intermediary) |

Contrast with a producing entity's registered scope, which normally contains 生产、制造、加工 or similar. A legal name or a business scope is evidence to check in a public registry, not a verdict.

## Administrative place-name words

Append the correct level to the cluster name from `cluster-map.md`:

`省` province · `市` city · `区` district · `县` county · `镇` town · `街道` sub-district · `村` village

Many well-known clusters sit at town level (for example 大唐镇 in 诸暨市, 古镇镇 in 中山市, 柳市镇 in 乐清市). Adding the town name often separates local producers from city-level trading offices.

## Reverse-lookup queries

Use these to check a named company, not to find new ones:

| Chinese query | Purpose |
| --- | --- |
| `<公司全称>` 工商 注册地址 经营范围 | Registration, address, business scope |
| `<公司全称>` 生产许可证 / 环评 / 排污许可 | Process licences where applicable |
| `<公司全称>` 专利 / 商标 | Technical activity and assignee name |
| `<公司全称>` 招聘 车间 / 操作工 | Signals of real production staffing |
| `<地名>` + `<产品词>` + 行业协会 / 产业园 | Local industry infrastructure |

Replace `<公司全称>` with the exact registered Chinese legal name. A search on an English trade name usually returns nothing useful.

## Platform-side filters

On domestic B2B platforms, look for filters or labels meaning: seller location (所在地), business model (经营模式: 生产加工 vs 经销批发), source factory (源头工厂 / 源头厂货), verified supplier (实力商家 / 深度验厂). On export platforms, filter by supplier province/city and read the declared business type.

All such labels are **self-declared or platform-assigned claims**. They narrow a search; they do not certify a factory.

## Specification vocabulary (keep bilingual)

Machine translation routinely garbles dimensions, tolerances and material grades. Write critical values twice: Chinese term + number + standard designation.

| Chinese | English |
| --- | --- |
| 起订量 / 最小起订量 | MOQ |
| 打样 / 样品费 | sampling / sample charge |
| 模具费 / 开模费 | tooling / mould cost |
| 含税 / 不含税 | tax included / excluded |
| 出厂价 / FOB / 含运费 | ex-works / FOB / freight included |
| 材质 / 牌号 / 公差 | material / grade / tolerance |
| 表面处理 / 电镀 / 喷涂 | surface finish / plating / coating |
| 营业执照 / 经营范围 | business licence / registered business scope |
| 验厂 / 出货前验货 | factory audit / pre-shipment inspection |
| 质检报告 / 检测报告 | QC report / test report |
| 交期 / 产能 | lead time / capacity |
| 质保 / 售后 | warranty / after-sales |
| 技术标准 / 国标 / 行标 | technical standard / GB standard / industry standard |

## Rules

- Produce paste-ready strings, not paraphrases. Prefix each with its English gloss.
- Do not invent product words that a native speaker would not use; when uncertain, give two or three alternative Chinese synonyms and say which is a guess.
- Do not include real company names, contact details or deep platform URLs.
- Do not rely on automated translation for specifications; instruct the buyer to confirm dimensions, materials, grades, tolerances and MOQ directly with the supplier.
- For firmware, voice, AI or app requirements, produce terms for the solution layer as well as the whole-unit layer; a single product-name query will miss the party that owns the customisation.
- When the request includes a backend, cloud service, deployment model or data requirement, give two separate query sets — hardware (with county/town names) and platform / service (without them) — and say explicitly that the platform layer is not selected by production geography.
