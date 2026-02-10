# OpenClaw 调研分析报告

## 背景介绍

是一个个人AI助手项目，可在自己的设备上运行。它通过用户已经使用的渠道（如WhatsApp、Telegram、Slack、Discord等）进行交互，还支持扩展通道如BlueBubbles、Matrix等。该项目强调本地化、快速响应和持续在线体验。

### 开发团队

由奥地利开发者**Peter Steinberger**创建。他此前是成功公司 PSPDFKit（文档工具包）的创始人，在获得 Insight Partners 投资后退出，开始专注于 AI 项目开发

### 发展趋势

- **Clawdbot**→ 最初的名字（因与 Anthropic 的商标冲突而更改）
- **Moltbot**→ 临时名称（灵感来自龙虾蜕壳的生物学过程）
- **OpenClaw**→ 2026 年初确定的最终名称
- 2026 年初，OpenClaw 在几周内从默默无闻到`GitHub`获得约 147,000 星标,成为当年最受关注的 AI 项目之一。
- 奥地利（诞生）→ 硅谷（爆发）→ 中国（云厂商集成）→ 全球开发者社区  

- ### 对业界的影响
- **国外发展情况**
基础设施层面，Cloudflare 迅速跟进推出了 Moltworker 无服务器部署方案，允许用户在边缘节点上运行 OpenClaw 代理，按触发次数计费，大幅降低了部署门槛。这种云原生支持使得 OpenClaw 从个人玩具快速转变为可规模化的生产工具。

然而，企业级市场的态度呈现明显分化。大型科技公司如谷歌、微软虽然积极关注 OpenClaw 的技术演进，但在内部采用上保持极度谨慎。与此同时，安全厂商如 Palo Alto Networks、Cisco 和 Microsoft Defender 团队发布了多份严厉的风险评估报告，将 OpenClaw 描述为"安全噩梦"，指出其具备的"致命三要素"——访问私人数据、暴露于不可信内容、外部通信能力——使其成为企业环境的重大威胁。

- **国内发展情况**
与国外相比，中国对 OpenClaw 的跟进呈现出更强的系统集成特征和战略导向。阿里云、腾讯云、字节跳动等国内云巨头迅速将 OpenClaw 集成到其云平台产品中，提供一键部署和托管服务。这种集成不是简单的镜像部署，而是深度适配了国产大模型生态。OpenClaw 官方已确认支持 DeepSeek、Kimi K2.5、qwen等国产大模型作为后端，使得国内用户可以在不依赖 OpenAI、Anthropic 等西方厂商的情况下获得完整的自主代理能力。

中国开发者社区在 OpenClaw 生态中表现异常活跃，贡献了大量针对本土场景的技能包（skills）。从电商运营到社交媒体管理，从中文自然语言处理到国内 API 集成，这些社区贡献丰富了 OpenClaw 的功能边界。

全球扩散路径呈现明显的地理跳跃特征：从奥地利诞生，到硅谷爆发，再到中国云厂商大规模集成，最后辐射至全球开发者社区。这种路径反映了不同地区对自主 AI 代理技术的差异化需求——欧美更注重隐私和去中心化，中国更强调系统集成和国产替代，而其他地区则主要跟随技术潮流。

- **各行业跟进情况**
- ***科技行业***
科技行业是最早跟进 OpenClaw 的领域，跟进方式呈现多元化特征。AI 基础设施公司如 Cloudflare 推出 Moltworker 等部署方案，将 OpenClaw 能力服务化。安全厂商则采取防御姿态，Palo Alto Networks、Cisco、Microsoft Defender 等纷纷发布风险评估报告，将 OpenClaw 纳入企业安全监控范围。RPA（机器人流程自动化）厂商如 n8n 加速 AI Agent 功能开发，在其可视化工作流平台中增加 AI Nodes，直接与 OpenClaw 形成竞争。大模型公司如 Anthropic、OpenAI、DeepSeek、Kimi 则提供 API 支持，将 OpenClaw 视为下游应用场景的重要入口。
 
- ***金融服务行业***
金融行业对 OpenClaw 表现出高关注度但极度谨慎的矛盾态度。金融科技公司积极探索自主代理在交易监控、客户服务等场景的应用，潜在应用包括收据处理与财务报表生成、合规性监控与主动预警、客户账户管理与自动化沟通。然而，由于 OpenClaw 具备的"致命三要素"风险，银行核心系统尚未采用。更严峻的问题是"影子 AI"现象——22% 的企业员工未经授权使用 OpenClaw 处理敏感数据，包括金融分析师使用其分析市场数据、处理客户信息，这带来了巨大的合规风险。

- ***医疗健康行业***
医疗行业对 OpenClaw 的采用以隐私保护和伦理导向为特征。本地运行模式天然符合 HIPAA 等医疗数据保护法规要求，这使得 OpenClaw 在辅助诊断场景具有独特优势。AI 辅助放射科医生识别肿瘤的人机协作系统可提升 15-20% 诊断准确率。OpenClaw 官方伦理指南明确禁止将其用于社会评分或大规模监控，体现了对医疗伦理的尊重。但实际应用仍面临障碍：缺乏企业级审计日志难以满足医疗合规要求，持久记忆功能可能导致患者数据泄露风险，这些限制了其在核心医疗系统的渗透。

- ***零售电商行业***
零售电商行业是 OpenClaw 自动化能力的重点应用领域。在客户服务环节，商家通过 WhatsApp、Telegram 等平台部署自动回复代理，实现 7×24 小时响应，大幅降低人力成本。在订单处理环节，代理自动提取邮件订单信息并更新库存系统，减少人工录入错误。在竞品监控环节，代理定期抓取竞争对手价格生成比价报告，提供实时市场情报。最具创新性的是 SaaS 集成场景——非技术团队使用 OpenClaw Browser Relay 自动化 SaaS 工具间的数据流转，无需编写 API 集成代码即可突破数据孤岛。这种"无代码集成"能力对中小电商企业具有极高价值。

- **相关应用**
- **Moltbook**是首个基于 OpenClaw 构建的 AI 代理专属社交平台，性质类似 Reddit 但完全由 AI 代理运营。平台上 15 万多个 AI 代理自主发帖、评论、互动，形成复杂的社交网络动态，人类用户只能旁观无法参与。这种实验性质的产品暂无明确盈利模式，但其意义在于证明了多代理交互可能产生的涌现行为，为未来的 AI 社交网络提供了概念验证。
- **ClawHub**/ 是 OpenClaw 的官方技能包市场，托管数千个社区贡献的技能包。然而，安全研究发现 22-26% 的技能包包含安全漏洞，部分甚至被设计用于窃取用户凭证。这种"野生 west"状态促使官方计划推出更规范的扩展市场（Extension Marketplace），引入审核机制和安全标准。（[www.clawhub.ai](http://www.clawhub.ai)）
![图形用户界面, 文本, 应用程序 AI 生成的内容可能不正确。]https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image001.png

## 主要功能

- 多平台消息集成,  AI 代理对话,  技能包系统,  持久记忆,  自主任务执行
## 功能介绍
- ***多平台消息集成*** ： 如连接telegram，discord，whatsapp，钉钉，飞书。可以直接在聊天app上对其发布任务或接受消息：
(https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image002.jpg)

- ***AI代理对话*** ： 可以配置qwen，openai，chatgpt，gemini等ai模型，并进行对话。
![文本 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image003.png)

- ***技能包系统***：  可以持续为其增添技能包，如语音识别，图片视频生成等等。
![图形用户界面, 文本, 应用程序, 电子邮件 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image004.png)
- ***持久记忆***：  跨会话记住用户偏好和上下文，拥有无限的记忆，可以以你的方式，培养出符合你行为习惯的AI助手

![手机屏幕截图 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image005.jpg)

- ***自助任务执行***：  自动执行多步骤任务，如查资料、发邮件、管理日程。
安装邮件需要下载msmtp并下载email-send技能包并配置环境变量

![文本, 信件 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image006.jpg)

### 软件生态

OpenClaw 通过**50+ 官方集成**和**700+ 社区技能包**，支持与各类第三方软件的深度整合

- **通讯平台**：WhatsApp、Telegram、Discord、Slack、iMessage、Signal、Matrix、Mattermost、飞书。
- **生产力工具**：Gmail、Outlook、Google Calendar、Notion、Linear、Jira、Trello
- **开发工具**：`GitHub`、`GitLab`、VS`Code`、Cursor、Arcade.dev
- **其他**：Chrome 浏览器、Tavily 搜索、ProductBoard、KeyResults
- **实现方式**：
1. 原生技能包：在openclaw onboard里或clawhub网站配置，系统根据环境、配置、依赖自动过滤可用技能
2. 外部 CLI 工具桥接：适用于第三方服务提供命令行工具，无官方`Node.js`SDK（容易因为不适配导致openclaw无法启动），OpenClaw 通过shell 命令调用外部 CLI。

3. API直接集成：用户**在聊天界面直接输入自然语言openclaw自己会组装上下文与分析用户需求，LLM 推理生成结构化工具调用并网关路由到对应技能，执行 HTTP 请求后生成自然语言回复。
```bash
Openclaw config set-key "tools.ahrefs.api-key" -value "xxx"
Openclaw config set-key "tools.gsc.client-id" -value "xxx"
```

## 核心优势

clawdbot是可以长期运行的Agent执行容器

- **长期运行**：不是一次性任务，而是持续工作的进程。
- **Agent**：具有自主决策能力的智能体。
- **执行**：实际产生动作和结果。
- **容器**：提供隔离、稳定的运行环境。
不解决ai会不会写代码这样一个问题，而是：某一类事情能不能在你不盯着的情况下持续被完成。clawdbot不像ceo与决策者，像是一个永远不会下班的去执行的人员，非常擅长去做重复、标准化的工作，完全不适合判断和取舍、宏观规划和架构设计这样的事情。

## 使用方式

- **并不是任何事情都值得搞24X7的agent**  
- [ ] 第一类：一次性任务——做完就结束，不需要持续运行。  
- [ ] 第二类：需要人持续介入的任务——需要不断做决策和调整。类似vibe working：编程、辅助设计、写小说  
- [x] 第三类：可以长期自治的任务——规划明确，可以自动循环执行。给ai训练好，长期让它自己跑的任务。（唯一适合） 
- 举例：1.你需要每天去监控几个`Github`仓库，去抓他们更新，整理摘要，条件满足的话给我去发一个提醒，确保你不在场这个clawdbot也能够去帮你很好的完成。（不在场反而更有价值）
![手机屏幕截图 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image007.jpg)

2.去写一个复杂的业务模块，自动去做技术决策，没有明确边界的“先跑着看看”，“先验证行不行”，这样大概率跑一会clawdbot容易自己把自己关掉，不满足预期，或者把其自己的思绪弄混乱。（把“强思考型”工作错误的交给了执行型Agent）容易把自己搞崩溃。

## 安装过程

1.配置`Node.js`22+的环境

2.登录[www.clawdbot.com](http://www.clawdbot.com)

3.quickstart直接复制到终端

![图形用户界面, 网站 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image008.png)

4.选择模型与技能包（可以暂时跳过后续添加）

5.选择聊天app接入（也可以暂时跳过）

## 注意事项

1.`npm`包下载时需要翻墙，不然难以下载。在虚拟机内虽然共享宿主机一个网络，但需要连到socks代理，HTTP代理相同的端口，不然容易出现难以解决的错误。

2.为了快速开始。尽量选择不需要API的技能包如Summarize。

3.本地配置不要接入Telegram等外国聊天网站，目前不支持通过Clash等vpn端口代理来打通clawdbot与外国聊天软件的Channle，不然只会像机器人似的回复，而调用不了已配置的模型。

![文本 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image009.jpg)

4.系统尽量用ubuntu或Mac最新，尝试过CentOS系统，只能配置`Node`.js18环境。

## 配置方法

1. 唯一的核心配置是接入的AI模型，其他都可以暂时跳过。
2. openclaw的sillks安装：https://www.clawhub.ai/
- 第一步安装clawhub:
![图形用户界面, 文本, 应用程序, 电子邮件 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image010.png)

- 第二步搜索你想要的sillks(又称"技能")：

![图形用户界面, 文本, 应用程序 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image011.png)

- 第三步安装你想要的sillks：

![图形用户界面, 文本, 应用程序 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image012.png)找到的sillks包名例如：openbroker

- 安装命令：npx clawhub@latest install 【技能包名】

例如：npx clawhub@latest install openbroker

即可安装好技能！

随后于你的openclaw进行对话，问他：给你安装了一个新的技能或者说sillks。你查看一下！

3. 下载飞书插件（下），通过Finalfell压缩到openclaw的文件夹

![](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image013.png)

- 接着在飞书上发布应用选择机器人并配置权限

![图形用户界面, 应用程序 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image014.png)

![图形用户界面, 应用程序 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image015.png)

- 获取该机器人api与app secret以及用户id配置到环境中即可：

![](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image016.png)

 ## 注意事项
1. 关于飞书配置，千万不要让openclaw自己进行下载安装决策，容易让自己崩盘并且无法启动网关服务。
2. 目前国内暂时无法配置国外WhatsApp等聊天软件。
3. 安装技能包时要注意其是否要配置环境变量以及在国内是否可以获取。
4. 建议下载reflect安装包
![图形用户界面, 文本, 应用程序, 电子邮件 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image017.png)

![文本 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image018.png)

![图形用户界面, 文本, 应用程序 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image019.png)

## 启动第一个任务（Hello Word）

- 对其赋予名字、特性和交流风格，他会对被赋予的规则始终牢记

![文本, 信件 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image020.jpg)

## 最佳实践

给openclaw安排可以长期自治的并有准确规则的任务：

到知乎或者百度帮我整理数据库从小白到大神所要学习的每个章节步骤，并在每天的下午五点半发到1758085892@qq.com一个章节学习所需要参考到的资料文献，每天一个章节以此类推

![手机屏幕截图 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image021.jpg)

## 资源

1. 下载网站[www.clawdbot.com](http://www.clawdbot.com)

2. 技能包下载网站[www.clawhub.com](http://www.clawhub.com)

3. 飞书插件：通过网盘分享的文件：feishu.zip

链接: https://pan.baidu.com/s/1FsUos1Sy7EWpykQA4Lvugg?pwd=4nmd 提取码: 4nmd

--来自百度网盘超级会员v3的分享

4. 官方`github`仓库：[github.com/clawdbot/clawdbot">https://`github`.com/clawdbot/clawdbot](https://<code class=)

5. 虚拟机安装教程：[【2026最新】免费版VMware安装教程，傻瓜式安装【附安装包资料免费领取】_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV12X2UBPEmB/?spm_id_from=333.337.top_right_bar_window_default_collection.content.click&vd_source=35f01971be2b21bee755b47851dd6916)

6. linux安装教程：[https://www.bilibili.com/video/BV1a5mzYXET8/?spm_id_from=333.788.top_right_bar_window_default_collection.content.click](https://www.bilibili.com/video/BV1a5mzYXET8/?spm_id_from=333.788.top_right_bar_window_default_collection.content.click)

## 总结

- **clawdbot 讨论非常多**： 有人说这是第一个真正可用的ai员工，还有人说这不过是自动化脚本的大合集，也有人买了mac mini跑了一两次之后吃灰了

- **核心**：这波爆火，本质上不是一个工具问题，而是“你会不会设计agent 工作方式”的问题。

- 复用的是agent的配置，而不是agent本身。

![图形用户界面 AI 生成的内容可能不正确。](https://cdn.jsdelivr.net/gh/crispfpx/openclaw-image2/img/image022.png)

- **有人问是不是可以复用上次那个AI员工？** 不行！因为clawdbot不是一种资产，而用clawdbot去适配的那个场景才是资产，clawdbot本身只是一个运行态的容器，就像一个正在跑的进程。不能复用上一次的clawdbot，真正想复用的其实是你之前为clawdbot设计好的任务结构、固定下来的规则以及稳定的输入输出的一个边界和长期利用起来的有效的记忆。所以说clawdbot负责承载而不是积累价值。

- **关键认知转变**：并不是Clawdbot效果好不好，而是没有把一类事情设计成“值得长期自动化”的问题。有人用的顺就可以大大提升工作效能，有的只是简单跑了一些单后就觉得这个东西没啥用。
- **真正的价值**：不在于它有多少个技能，能不能去远程控制你的电脑，而在于让我们认真思考一件事情 ，就是哪些事情是我们值得把时间的控制权完全交给ai。
- **真实项目关注点**：1.稳定性——能不能长期可靠运行。2.可复用性——能不能在不同场景使用。3.可预测性——长期行为是否可控。4.并不是某一次效果有多惊艳。