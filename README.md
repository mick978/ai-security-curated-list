# 🔐 AI / LLM 安全方向 GitHub 高 star 项目精选

> 调研时间：2026-06-19
> 范围：聚焦**实用工具**（扫描器、防护 WAF、red-team 框架、jailbreak 测评、Agent 安全），已排除纯论文/纯教程/套壳项目
> 共筛选 **10 个真实项目**，star 数均来自 GitHub 实时查询

排名按 ⭐ star 数从高到低排序。

---

## 1. 🛡️ [NVIDIA/garak](https://github.com/NVIDIA/garak) — ⭐ 8.1k
- **语言**: Python 50.2% · HTML 41.0% · TypeScript 8.7%
- **简介**: LLM 漏洞扫描器，号称 "nmap/Metasploit 之于 LLM"。覆盖幻觉、数据泄露、Prompt 注入、错误信息、毒性生成、越狱 (Jailbreak) 等多种失效模式。
- **推荐理由**: NVIDIA 官方维护，README 中明确列出 DAN、encoding、GCG、xss、malwaregen、leakreplay 等 20+ 内置探针。工业界事实标准的 LLM 红队扫描器，已集成 OpenAI / HuggingFace / Bedrock / Ollama 等几乎所有主流模型后端。
- **核心能力**: 静态、动态、自适应探针；支持 Hugging Face、OpenAI、Replicate、Cohere、Groq、AWS Bedrock、NIM、REST、gguf 等多模型后端；JSONL 日志可二次分析。
- **安装**: `pip install -U garak`

---

## 2. 🚀 [superagent-ai/superagent](https://github.com/superagent-ai/superagent) — ⭐ 6.6k
- **语言**: TypeScript 54.4% · Python 42.2%
- **简介**: 保护 AI 应用免受 Prompt 注入、数据泄露、有害输出，开源 AI Agent 安全 SDK（Y Combinator 投资）。
- **推荐理由**: 提供 Guard（运行时拦截 Prompt 注入/恶意工具调用）、Redact（PII 脱敏）、Scan（仓库投毒扫描）、Test（红队场景）四大能力，支持 TypeScript 和 Python 双 SDK；同时开源了 0.6B/1.7B/4B 三档 Guard 模型可本地部署，CPU GGUF 版也可离线使用。
- **集成形态**: SDK + CLI + MCP Server（Claude Code/Desktop）。
- **亮点**: 可作为 MCP Server 在 Claude/Cursor 中直接使用，对 Agent 场景最友好。

---

## 3. 🚧 [NVIDIA-NeMo/Guardrails](https://github.com/NVIDIA-NeMo/Guardrails) — ⭐ 6.5k
- **语言**: Python 99.4%
- **简介**: NVIDIA NeMo Guardrails — 为 LLM 对话系统添加可编程护栏 (programmable guardrails) 的开源工具包。
- **推荐理由**: 支持 **5 类护栏**（Input / Dialog / Retrieval / Execution / Output），引入自定义建模语言 **Colang** 来描述对话流与护栏规则；提供 OpenAI、Llama-2、Falcon、Vicuna 等多模型支持；支持 Docker 化部署与内置 LLM 漏洞扫描报告（ABC Bot 示例）。学术 EMNLP 2023 Demo 论文支撑。
- **适用场景**: RAG 问答的事实核查与输出审核、领域助手、客服 SOP 流。
- **安装**: `pip install nemoguardrails`

---

## 4. 🐢 [Giskard-AI/giskard-oss](https://github.com/Giskard-AI/giskard-oss) — ⭐ 5.4k
- **语言**: Python 96.5%
- **简介**: 面向 LLM Agent 的开源测试与评估库，覆盖 OWASP LLM Top-10 威胁类别的自动红队。
- **推荐理由**: 提供三件套 — `giskard-checks`（评估算子 + LLM-as-judge 套件，可做场景化/多轮/安全规则的断言）、`giskard-scan`（自动从 Agent 描述生成对抗性测试用例，覆盖 Prompt 注入、有害内容、刻板印象、错误信息）、`giskard-rag`（RAG 测试集自动生成 + RAGET）。可直接 `pip install giskard` 一行起步。
- **适用场景**: 上线前的回归测试、CI 阶段的安全门禁、多轮 Agent 行为合规。
- **学术支撑**: 在多篇顶会论文中被引用，文档站点 docs.giskard.ai/oss 完整。

---

## 5. 🦙 [meta-llama/PurpleLlama](https://github.com/meta-llama/PurpleLlama) — ⭐ 4.2k
- **语言**: Python（综合）
- **简介**: Meta 官方 LLM 安全工具集，紫队 (Purple Teaming) 项目，含 **Llama Guard 系列模型 + Prompt Guard + Code Shield + CyberSec Eval 1/2/3 基准**。
- **推荐理由**: 提供工业级 Input/Output 内容审核模型 Llama Guard 3（1B/8B/11B-vision），支持 7 种语言 + 128k 上下文 + 图像审核；Prompt Guard 直接分类 Prompt 注入/越狱；Code Shield 在推理时过滤 LLM 产出的不安全代码；CyberSec Eval 包含视觉 Prompt 注入、钓鱼、自主攻击三大新测试集。
- **授权**: Evals 走 MIT，模型走 Llama Community License（可商用）。
- **适用**: 任何生产 LLM 系统都可白嫖的护栏模型与基准。

---

## 6. 🔥 [Tencent/AI-Infra-Guard](https://github.com/Tencent/AI-Infra-Guard) — ⭐ 3.9k
- **语言**: Python 73.8% · Go 25.7%
- **简介**: 腾讯朱雀实验室出品的全栈 AI Red Teaming 平台 — ClawScan（OpenClaw 安全扫描）+ Agent Scan + MCP/Agent Skills 扫描 + AI Infra 漏洞扫描 + LLM Jailbreak 评估。
- **推荐理由**: **国内大厂开源，文档完整，中文友好**。v4.1.13 (2026-06) 已支持 100+ AI 组件指纹、1600+ CVE 规则、68 个 AI 框架覆盖（vLLM、ComfyUI、Ollama、Triton 等），并已发布在 Black Hat Europe 2025 Arsenal。Web UI 简单易用，Docker 一键部署，14 大类 MCP 风险扫描 + 26 种 Prompt 攻击算子（20 单轮 + 6 多轮）。
- **学术引用**: 被 19+ 论文引用，含 MCP 安全、Agent 风险、Skill 攻击等多个方向。
- **注意**: 官方建议"内部使用" — 不要公网部署（缺鉴权）。

---

## 7. 🛡️ [protectai/llm-guard](https://github.com/protectai/llm-guard) — ⭐ 3.1k
- **语言**: Python 99.0%
- **简介**: LLM 交互安全工具包，Protect AI 出品；提供 15+ 输入扫描器和 20+ 输出扫描器，可作为 LLM 调用前置/后置的**安全 WAF**。
- **推荐理由**: 覆盖 Prompt 注入、匿名化 (Anonymize/Deanonymize)、禁止代码 (BanCode)、禁止竞品 (BanCompetitors)、秘密泄露 (Secrets)、Toxicity、Bias、FactualConsistency、URLReachability、LanguageSame 等实用场景。pip 装好即用，OpenAI ChatGPT 集成示例完整。
- **适用**: 给任何 LLM 应用加一层 WAF，生产环境最容易落地的方案之一。
- **安装**: `pip install llm-guard`

---

## 8. 🔬 [greshake/llm-security](https://github.com/greshake/llm-security) — ⭐ 2.1k
- **语言**: Jupyter Notebook 80.2% · Python 19.8%
- **简介**: 间接 Prompt 注入 (Indirect Prompt Injection) 经典研究仓库，含 5 大类攻击 PoC（远程控制、数据窃取、持久化、邮件扩散、多阶段载荷），对应 CCS/AISec 2023 论文 *"More than you've asked for"* (arXiv:2302.12173)。
- **推荐理由**: **"Prompt 注入 ≈ 任意代码执行"** 这一论断的源头仓库。演示了 GPT-4 / Bing / LangChain / Copilot 等多类集成系统的攻击面，含 fuzzer 工具和 5 个可复现的 demo 场景。即使是研究型，也对构建防御有极大参考价值（很多 WAF 设计都参考了它列出的威胁模型）。
- **可玩性**: 直接 `python scenarios/main.py` 跑 GPT-4 攻击演示。

---

## 9. 🏗️ [Trusted-AI/adversarial-robustness-toolbox (ART)](https://github.com/Trusted-AI/adversarial-robustness-toolbox) — ⭐ 6.0k
- **语言**: Python 99.8%
- **简介**: IBM 出品、LFAI 毕业项目，**ML 安全的瑞士军刀** — 覆盖 Evasion / Poisoning / Extraction / Inference 四大对抗威胁，跨 TensorFlow / PyTorch / scikit-learn / XGBoost / LightGBM / CatBoost 等所有主流 ML 框架。
- **推荐理由**: 虽然偏向传统 ML 安全而非纯 LLM，但对**多模态 LLM、表格模型、CV 模型**的对抗鲁棒性测试仍无可替代 — 包含图像 adversarial、模型窃取 (extraction)、成员推断 (inference)、投毒等成熟实现。13k+ 提交、64 个 release、1.3k fork，**工业标准**。
- **适用**: LLM 之外的 ML 系统安全审计（多模态模型、CV 模型、表格模型）。
- **安装**: `pip install adversarial-robustness-toolbox`

---

## 10. 🛠️ [confident-ai/deepteam](https://github.com/confident-ai/deepteam) — ⭐ 1.9k
- **语言**: Python 100%
- **简介**: 简单易用的 LLM 红队框架 — "penetration testing, but for LLMs"。基于 [DeepEval](https://github.com/confident-ai/deepeval)，50+ 漏洞 + 20+ 对抗攻击。
- **推荐理由**: 内置 OWASP Top 10 for LLMs 2025、OWASP Top 10 for Agents 2026、NIST AI RMF、MITRE ATLAS、Aegis、BeaverTails 六大安全框架映射；20+ 单轮攻击 (Prompt Injection、Roleplay、Leetspeak、ROT13、Base64、Crescendo…) + 多轮攻击 (Linear/Tree/Sequential Jailbreak)；提供 7 个生产级 Guardrail (ToxicityGuard、PromptInjectionGuard、PrivacyGuard…)。**最容易上手的 red-team 工具**。
- **适用**: 红队评估报告生成、安全框架合规映射、CI 集成。
- **安装**: `pip install -U deepteam`

---

## 🥈 备选 (star > 1k 但偏研究/聚合)
- **[msoedov/agentic_security](https://github.com/msoedov/agentic_security)** ⭐ 1.9k — Agentic LLM 漏洞扫描器，支持多模态攻击（文本/图像/音频）和多步越狱，可作 CI 检查 (`agentic_security ci`)。
- **[CyberArk/FuzzyAI](https://github.com/cyberark/FuzzyAI)** ⭐ 1.5k — 自动 LLM 模糊测试工具，内置 12+ 攻击策略 (PAIR/ArtPrompt/Crescendo/Genetic/Many-shot…)，支持 9 大模型供应商。
- **[utkusen/promptmap](https://github.com/utkusen/promptmap)** ⭐ 1.2k — 自定义 LLM 应用的 Prompt 注入扫描器，2025 全新重写版；白盒/黑盒双模式，50+ 测试规则，6 大类别。
- **[splx-ai/agentic-radar](https://github.com/splx-ai/agentic-radar)** ⭐ 982 — LLM Agent 工作流安全扫描器，输出 HTML 可视化报告，支持 LangGraph/CrewAI/n8n/OpenAI Agents。
- **[OWASP/www-project-top-10-for-large-language-model-applications](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications)** ⭐ 1.3k — OWASP 官方 LLM Top 10 文档（GenAI Security Project），**所有 LLM 安全的"必读"**。

---

## 📌 选型建议

| 需求 | 推荐项目 |
|---|---|
| 通用 LLM 漏洞扫描 (nmap-style) | **garak** (1) |
| 实时 LLM WAF / 护栏 | **NeMo Guardrails** (3), **llm-guard** (7), **superagent** (2) |
| Agent / MCP 生态安全 | **AI-Infra-Guard** (6), **agentic-radar** (备选), **agentic_security** (备选) |
| 红队 / 越狱测评 | **deepteam** (10), **FuzzyAI** (备选), **promptmap** (备选) |
| 工业级审核模型 (直接拿来用) | **PurpleLlama / Llama Guard 3** (5) |
| 多模态 / 非纯 LLM 模型的对抗 | **ART** (9) |
| 学习/调研入口 | **greshake/llm-security** (8) + OWASP Top 10 LLM (备选) |
| 上线前 Agent 行为测试 | **Giskard** (4) |

---

*最后更新：2026-06-19，数据来源：GitHub Search API + 各项目 README + 实时 star 统计*
