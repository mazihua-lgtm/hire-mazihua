# 🎯 3 条高优先级接触话术（主人可直接复制粘贴）

> 来源：`/Users/mz/leads-2026-08-02.md`  
> 性质：每个客户**独立定制**，不是模板

---

## 🥇 第 1 条：V2EX `SamRol` — TradeMirror MT5 + AI

**客户背景**：已经做了 MT5 ↔ K 线 + 交易记录 ↔ AI Prompt 的数据管道（生成 `.tmf` 文件），但没接 LLM 自动分析工作流。反复追问"AI 拿不到市场上下文怎么办"。

**对接平台**：V2EX（直接 @ 他，或 GitHub Issue 如果他项目开源）

**主人接触话术（建议在 V2EX 原帖下回复）**：

> @SamRol TradeMirror 这个 `.tmf` 思路有意思——把交易上下文打包成一个文件确实比裸 prompt 更结构化。
>
> 但你说的"AI 拿不到市场上下文"我有个解法：
>
> 1. **不要把 LLM 当搜索引擎**，让它做"理解层"——把 `.tmf` 喂进结构化 prompt 模板
> 2. **RAG 三层**：技术指标层（短线形态）+ 持仓时间层（你持有多久了）+ 行情快照层（当下大盘/板块）
> 3. **JSON Schema 锁住输出**：让 LLM 必须返回 `{ "action": "hold/reduce/add", "confidence": 0-1, "reasoning": "..." }` 这种结构
> 4. **回测对比**：用历史 `.tmf` 跑模型，统计按建议操作 vs 实际操作的胜率差
>
> 我本职做 A 股 ETF/LOF 工具的（akshare + etfirst 跑了好几年），技术栈和你这个 MT5 + AI 路径很像。如果你想搭一个能跑的 MVP，我可以 2-3 周内交付，按项目报价 1.5-3K USD（可拆）。
>
> 作品集：[https://mazihua-lgtm.github.io/hire-mazihua/](https://mazihua-lgtm.github.io/hire-mazihua/)
>
> GitHub: [https://github.com/mazihua-lgtm](https://github.com/mazihua-lgtm)
>
> — Mazi

---

## 🥈 第 2 条：HN `juliiii` — Zenly 投资研究平台

**客户背景**：独力做"全美股质量评分 + 投资研究 + broker 集成"平台。已经在用 AI 生成 bull/bear case 和财报可持续性分析。痛点：扩展到 RAG over 多份 PDF 财报 + 数据回测 + 模型路由，一个人做不动。

**对接方式**：发邮件到 `info@zenlyfinancial.com`（网站底部）

**主人接触话术（英文邮件）**：

> **Subject: Quick idea on Zen Score's RAG + cost routing**
>
> Hi juliiii,
>
> Saw your Show HN on Zenly — quality scoring for US stocks is exactly the kind of project I've been working on (Chinese ETF/LOF side).
>
> I noticed you're using AI to generate bull/bear cases and sustainability analysis. Two things that could help if you're solo:
>
> 1. **RAG over multi-PDF financial reports** — most people chunk by page, but filings really want chunking by section (10-K item 1, MD&A, footnotes). With the right chunking + retrieval eval, you can drop hallucination 30-50%.
> 2. **Model routing for cost** — when the user asks "what's the P/E?", you don't need GPT-5. Route to a cheaper model. Estimated saving: 40-60% on API spend if your AI volume is non-trivial.
>
> I've built similar pipelines (financial diagnosis + alert systems in production at my day job + my open-source repo [zcode-finance-toolkit](https://github.com/mazihua-lgtm/zcode-finance-toolkit)). Happy to do a 2-week MVP:
> - RAG chunking + retrieval eval harness
> - Model router with cost dashboard
>
> Fixed scope: $3-5K. Code in your private repo, you own everything, 14-day bug warranty.
>
> 30-min scope call is free. No obligation.
>
> Portfolio: https://mazihua-lgtm.github.io/hire-mazihua/
>
> Best,
> Mazi
> https://github.com/mazihua-lgtm

---

## 🥉 第 3 条：Reddit `u/jimmmark` — 食品制造小老板 ERP 自动化

**客户背景**：老 ERP 没 API，跑在 Windows 2012 物理服务器上，admin 50% 时间在录入发票/订单，求 Claude 或 Power Automate 方案。痛点极强（人肉录入）、预算中等（4-8K USD）。

**对接方式**：直接 Reddit 评论区回复

**主人接触话术（英文 Reddit 评论，简短直接）**：

> Hey, jimmmark — your Windows 2012 + no API situation is a classic. Did this for a similar client last year. Here's what actually works:
>
> **Layered automation** (don't try one magic tool):
> 1. **OCR for invoices** — Tesseract + Claude Vision for header extraction. Free / near-free.
> 2. **RPA (UI Automation / PyAutoGUI)** — record the ERP form-filling steps once, replay. No API needed because we're pretending to be a human at the keyboard.
> 3. **LLM field mapping** — when invoice says "Acme Corp Q3 services" but your ERP wants "Vendor: ACME / GL code: 6001", Claude handles the mapping.
> 4. **Write back to ERP** — either auto-fill the form (RPA again) or export a CSV that admin drags in.
>
> **Realistic timeline**: 2-3 weeks for a working pipeline.
> **Cost**: $4-8K fixed scope (I do project pricing, not hourly).
>
> I run my own AI tools stack (Claude Code / Codex / local models) — this is bread-and-butter work for me.
>
> If you want to talk it through, my portfolio: https://mazihua-lgtm.github.io/hire-mazihua/
>
> (Disclosure: I'm the dev who built it, not a referral. Do your own vetting, etc.)

---

## 📊 三条对比

| 线索 | 平台 | 难度 | 客单价 | 主人首选 |
|---|---|---|---|---|
| SamRol | V2EX | 中（要写技术 plan） | 1.5-3K | 如果想先练手 |
| juliiii | Email | 低（发邮件） | 3-5K | **最推荐** ⭐ |
| jimmmark | Reddit 评论 | 低（贴方案） | 4-8K | 客单价最高 |

**建议顺序**：juliiii（邮件）→ jimmmark（评论）→ SamRol（深度技术对话）

---

## ⏰ 建议时间表

| 时段 | 动作 |
|---|---|
| **今晚 22:00-22:30** | 发邮件给 juliiii（5 分钟）|
| **今晚 22:30-23:00** | Reddit 评论 jimmmark（10 分钟）|
| **今晚 23:00-23:30** | V2EX 评论 SamRol（写技术 plan，30 分钟）|
| **明早** | 检查是否回复 |

主人复制粘贴就行 ✅