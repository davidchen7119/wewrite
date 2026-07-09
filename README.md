# WeWrite（定制版 · 中老年人生哲理文案）

基于 [oaker-io/wewrite](https://github.com/oaker-io/wewrite) 改造，专为「中老年人生哲理 / 情感文案」公众号场景深度定制。

严格遵循《AI复刻文案指导手册（最高级 / 严格模式）》，复刻中老年哲理金句同质文案风格：
替 45–65 岁（核心 45–60 岁）、正在变老又不想认输的人，把心里的委屈和倔强说出来。

> 笔名固定为 **温言入画**——一个坐在读者对面的知心大姐，通篇用"你"对话，卖的不是哲理是安慰。

## 定制特性对照

| 改动项 | 原版 WeWrite | 本定制版 |
|--------|-------------|----------|
| 写作角色 | 7 套 persona 可切换 | 固定「温言入画」（知心大姐），不切换 |
| 文章结构 | H1+H2，1500–2500 字 | `# 01`/`# 02`/`# 03` 三段 + 金句双发，200–400 字 |
| 选题来源 | 热点抓取 + SEO | 8 大选题库（悦己 / 通透 / 心态 / 关系 / 独立 / 健康 / 独处 / 命运） |
| 标题格式 | 带书名号《》 | **一律不加书名号**，直接写标题文字 |
| 署名 | 可配置 author | `作者: 温言入画 ｜ 发布时间`（已删除"发布地点"） |
| 尾部 CTA | 固定点赞文案 | 「喜欢今天这篇文字，不妨点个【赞👍🏻】和【在看❤️】／你每一份认可，都是温柔的鼓励」 |
| 工作模式 | 默认全自动 | 默认**逐步确认**，每步暂停等用户确认（说"全自动"可一口气跑完） |
| 视觉 AI | 封面 + 内文配图（需生图 API） | **输出中文生图提示词**（默认不接 API）；风格锁绘本风 + 角色一致性 + 金句文字入图 |
| 角色一致 | 无 | 支持固定同一中年女性形象（上传角色参考图，脸部不变、按场景换装） |

## 它能做什么

```
"写一篇中老年哲理文案"
  → 选题（8 大方向）→ 素材采集（俗语 / 老话）→ 写作（#01/#02/#03 + 金句双发）
  → 质量自检（9 项硬性检查）→ 视觉 AI（中文生图提示词）→ 微信排版 → 推送草稿箱（可选）
```

每一步完成后都会暂停等你确认，未经同意不自动进入下一步。

## 文章结构（铁律）

一篇只讲一个论点，结构固定如下（`references/writing-guide.md` 为最高级硬性约束）：

```
[标题]        强观点短句（= 全文唯一论点，不加书名号）
[署名行]      作者: 温言入画 ｜ 发布时间: YYYY年M月D日
[氛围图占位]  （一句话描述一张绘本风插画，定调情绪，不载信息）
# 01          抛观点 / 甩金句（1–3 句，直给，口语）
【金句卡片】  <本段核心金句，逐字>
# 02          展开一层（引俗语 / 老话 / 讲对比 / 给画面），继续围绕同一论点
【金句卡片】  <本段核心金句，逐字>
# 03          升华收尾（点题 + 温和落点）
绘画：温言入画
[尾部 CTA]    固定点赞引导（照抄，不可发挥）
```

**金句双发**（本库核心特征）：每段正文末的金句，必须在紧跟其后的【金句卡片】里**逐字复现**一次，两处完全一致。

**写作风格硬规则**：
1. 第二人称"你"贯穿全文，不用"笔者以为""大家应该"
2. 金句密集且双发（正文一遍 + 卡片复一遍）
3. 对仗 / 排比 / 对比节奏，朗朗上口适合截图转发
4. 可借俗语 / 老话 / 道家，禁止硬塞名人名言
5. 强观点短标题，且**一律不加书名号**

**红线**：不写存钱理财硬凑、不写政治、不写医疗诊断、不写迷信预言。

## 8 大选题方向

| 方向 | 说明 |
|------|------|
| ① 悦己·爱自己 | 取悦自己、浪漫、开心健康 |
| ② 通透·觉醒 | 中年通透、活得清醒、活得明白 |
| ③ 心态·不内耗 | 情绪管理、不较劲、戒掉情绪 |
| ④ 关系·边界 | 不上赶着、不消耗自己、学会拒绝 |
| ⑤ 自我·独立 | 成为自己的山、不慕强、做好自己 |
| ⑥ 健康·平安 | 健康快乐、心态风水 |
| ⑦ 独处·自在 | 敢于孤独、不责怪、不操心 |
| ⑧ 命运·顺其自然 | 天助磨你、疾风不言弃、人生本无意义 |

## Step 6 视觉 AI 规范（本版最重要的定制）

本版**不内置生图 API**，Step 6 始终输出**中文生图提示词**，由你拿去即梦 / seedream 生成后回传图片。提示词遵循 `references/visual-prompts.md` 的硬性约束：

### 风格锁（STYLE LOCK · 全程统一，绝不偏移）

每一张提示词（封面 + 每张卡片）都必须**完整嵌入同一段风格锁原文**，系列零漂移：

> 日式极简自然主义治愈系绘本插画，几米风格，小森林美学，东方留白美学，生活纪实绘本风格。极简构图、大面积留白、主体突出、电影感镜头；人物自然略带 Q 版、五官简洁克制、动作真实生动、不夸张不卖萌；彩铅 + 水彩 + 粉彩混合手绘、和纸纹理、低锐度、稚拙手绘感；真实环境光（晨光 / 午后 / 黄昏 / 夜灯 / 窗边侧光 / 逆光），无高对比硬阴影；低饱和高明度莫兰迪色系（暖白 / 米白 / 浅木打底，自然延展浅蓝浅绿浅棕浅灰暖橙），禁止高纯高对比；安静、细腻、克制、治愈，具诗意与情感共鸣；金句文字以娟秀手写体自然融入画面，与插画一体。

禁止：写实摄影、厚涂厚描边、卡通可爱化、高饱和网红风、逐张改画风。

### 情绪正面对位 + 找回自我

- **情绪正面对位**：文中点名的是读者痛点（如"疲惫 / 委屈"），但图片必须画**正面、阳光、积极**的状态（觉醒 / 松弛 / 自在）——走出痛苦后的轻松与光亮。读者看图应是"我也想这样"。
- **找回自我（增强层，非替代）**：可叠加"中老年女性重拾兴趣 / 做自己喜欢的事"的瞬间（遛狗、插花、临帖、织围巾、晨间太极、阳台瑜伽、闺蜜下午茶、读书会、跟姐妹旅行……**仅为举例，须发挥想象力，绝不可只局限这几个**）。
- **不硬塞**：所选状态必须与对应金句内核贴合；不合适就退回纯情绪画面，绝不为凑热闹硬加。

### 角色一致性（可选但推荐）

若你提供一张角色参考图（如中年女性正面形象），全系列图片锁定同一张脸、同发型、同神态，仅按场景换服装 / 配饰：

- 建议把参考图放到 `output/character_ref.png`，或直接在即梦 / seedream 上传作"角色参考 / 人物一致性 / 垫图"
- **背影不描写面部**：某图若为背影，提示词不得出现任何面部特征，只写背影 / 后脑勺 / 发尾 / 身影
- **配角不写五官、以主角为主**：场景中有其他人时，不写其五官表情，姿态按画面实际决定，始终以主角为主、不抢镜

### 金句文字入图（本库核心特征）

每张金句卡片图的提示词中，必须写明"用娟秀手写体清晰写下文字：'金句逐字'"，金句文字与【金句卡片】逐字一致，自然融入画面。

## 安装

把 skill 放到 WorkBuddy 的用户级 skills 目录，并建立隔离 Python 环境：

```bash
# WorkBuddy 用户级 skills 目录（Windows 示例）
git clone https://github.com/davidchen7119/wewrite.git \
  "C:/ProgramData/WorkBuddy/users/<你的用户ID>/.workbuddy/skills/wewrite"

cd "C:/ProgramData/WorkBuddy/users/<你的用户ID>/.workbuddy/skills/wewrite"
bash install.sh
```

> `install.sh` 会在 `.venv` 里创建隔离环境并安装依赖（markdown / bs4 / cssutils / requests / yaml / pygments / pillow 等，主要用于 Step 7 排版转 HTML）。核心写作流程（Step 1–6）不依赖 Python。
>
> ⚠️ `install.sh` 原本面向 macOS / Linux（调用 `.venv/bin/python`），在 Windows 上 venv 可执行文件位于 `.venv/Scripts/python.exe`，用该路径安装依赖即可。

安装后，在 WorkBuddy 对话中说出触发词即可唤起（见下）。

## 配置（可选）

```bash
cp config.example.yaml config.yaml
```

填入微信公众号 `appid` / `secret`（推送草稿箱需要）。

- **不配也能用**：自动降级为本地 HTML 预览 + 输出中文生图提示词，不推送。
- **微信推送前置条件**：除 `appid` / `secret` 外，还需把调用方服务器 IP 加入公众号后台「基本配置 → IP 白名单」，否则取 token 会报 `40164`。

> 注意：`config.yaml`、`output/` 下的生成图片与角色参考图已写入 `.gitignore`，**不会**被提交进仓库。

## 快速开始

在 WorkBuddy 对话里说：

```
写一篇公众号文章
选 ⑥ 健康·平安
继续
```

触发关键词：公众号、推文、微信文章、写公众号、中老年文案、哲理文案、情感文案、金句、文案搭子、选题、草稿箱、微信排版。

整个流程会逐步停下来等你的确认（选题、大纲、初稿、自检、提示词、排版）。

## 工作流程

```
Step 1  环境 + 配置（加载写作指导手册 / 风格）
  ↓
Step 2  选题（8 大方向 → 5 候选 → 历史去重）
  ↓
Step 3  素材采集（WebSearch 俗语老话 / 生活场景 → 写作大纲）
  ↓
Step 4  写作（#01/#02/#03 + 金句双发）
  ↓
Step 5  质量自检（9 项硬性检查 + 金句双发验证）
  ↓
Step 6  视觉 AI（输出中文生图提示词：氛围图 + 金句卡片图）
  ↓
Step 7  排版 + 发布（嵌入回传图片 → 微信 HTML；可选推草稿箱）
  ↓
Step 8  收尾（写 history.yaml → 移动到 {cwd}/WeWrite输出/）
```

默认逐步确认。说"全自动"可一口气跑完 Step 1–8。

## Toolkit 独立使用

若只想用排版 / 发布工具链（需先建好 `.venv`）：

```bash
# Markdown → 微信 HTML 预览
python3 toolkit/cli.py preview article.md --theme warm-editorial

# 发布到微信草稿箱
python3 toolkit/cli.py publish article.md --cover cover.png --title "标题" --digest "摘要"

# 主题列表 / 主题画廊
python3 toolkit/cli.py themes
python3 toolkit/cli.py gallery

# 小绿书 / 图片帖（横滑轮播，最多 20 张）
python3 toolkit/cli.py image-post p1.jpg p2.jpg p3.jpg -t "周末探店" -c "望京的宝藏咖啡馆"

# 文章质量检查
python3 scripts/humanness_score.py article.md --verbose

# 抓热点 / SEO / 范文风格库 / 学排版主题（底层能力，仍可用）
python3 scripts/fetch_hotspots.py --limit 20
python3 scripts/seo_keywords.py --json "AI大模型" "科技股"
python3 scripts/extract_exemplar.py article.md
python3 scripts/learn_theme.py https://mp.weixin.qq.com/s/xxxx --name my-style
```

## 目录结构

```
wewrite/
├── SKILL.md                  # 主管道（Step 1–8，最高级约束）
├── config.example.yaml       # 微信 / 生图 API 配置模板
├── style.example.yaml        # 风格配置模板
├── writing-config.example.yaml # 写作参数模板
├── requirements.txt
├── install.sh                # 创建 .venv 并装依赖
├── LICENSE / VERSION
│
├── references/               # Agent 按需加载的规范
│   ├── writing-guide.md        # 写作规范 + 质量自检（最高级硬性约束）
│   ├── visual-prompts.md        # 视觉 AI 提示词规范（风格锁 / 角色一致 / 情绪正面对位）
│   ├── content-enhance.md       # 内容增强策略
│   ├── topic-selection.md       # 选题评估
│   ├── frameworks.md            # 写作框架
│   ├── seo-rules.md / compliance-seo.md
│   ├── wechat-constraints.md    # 微信平台限制 + 自动修复
│   ├── style-template.md        # 风格字段 + 主题列表
│   ├── onboard.md / commands.md / learn-edits.md / effect-review.md
│   └── exemplars/               # 用户范文风格库（自动生成，不入 git）
│
├── toolkit/                  # Markdown → 微信工具链
│   ├── cli.py                  # preview / publish / gallery / themes / image-post
│   ├── converter.py            # Markdown → 内联样式 HTML + 微信兼容修复
│   ├── theme.py / themes/       # 主题引擎（含 warm-editorial / elegant-rose / sspai 等）
│   ├── publisher.py            # 微信草稿箱 API
│   ├── wechat_api.py           # access_token / 图片上传
│   ├── image_gen.py            # AI 生图（如配置 provider 可用）
│   └── config.py / platforms/
│
├── scripts/                  # 数据采集 + 诊断 + 构建
│   ├── fetch_hotspots.py / seo_keywords.py / fetch_stats.py
│   ├── extract_exemplar.py / learn_theme.py / fetch_article.py
│   ├── humanness_score.py / learn_edits.py / diagnose.py
│   └── build_codex.py / build_openclaw.py / build_playbook.py / context_budget.py / similarity_check.py
│
├── personas/                 # 底层写作人格预设（本版固定温言入画，不切换）
├── output/                   # 生成文章 / 图片 / 角色参考图（不入 git）
└── .gitignore                # 排除 .venv / config.yaml / output 图片
```

## License

MIT
