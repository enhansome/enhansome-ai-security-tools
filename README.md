# Awesome AI Security Tools with stars

> A curated list of **public-source, research, and commercial** tools for AI security and AI-assisted cybersecurity — autotriage, agent security, AI/ML supply chain, pentest agents, AI SAST, LLM-driven fuzzing, threat intelligence, SOC/SIEM triage, reverse engineering, LLM red-teaming, and more.

[![License: CC0-1.0](https://img.shields.io/badge/license-CC0--1.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#contributing)

**Type legend:** 🟢 public source / open-source · 🔬 research (paper / benchmark / dataset / framework) · 🟠 commercial with open components · ⚠️ restrictive, non-commercial, or unclear/no license — check before use.

GitHub-hosted entries show static **★ stars** and **last-commit** snapshots; refresh them with `python3 scripts/update_github_metrics.py` before release. Latest snapshot: 2026-08-16. Hugging Face model entries show license, access, and artifact metadata. Ordering within a section favors flagship and actively maintained projects.

***

## Contents

* [Autotriage of Security Findings](#autotriage-of-security-findings)
* [AI Agent & Coding-Agent Security](#ai-agent--coding-agent-security)
  * [Scanners & Auditors](#scanners--auditors)
  * [Frameworks, Rule Standards & Benchmarks](#frameworks-rule-standards--benchmarks)
  * [Runtime Protection & Enforcement](#runtime-protection--enforcement)
* [AI/ML Supply Chain & Model Security](#aiml-supply-chain--model-security)
* [Pentest & Red-Team Agents](#pentest--red-team-agents)
* [AI-Powered Recon & Narrow ML Tools](#ai-powered-recon--narrow-ml-tools)
  * [Subdomain & DNS Prediction](#subdomain--dns-prediction)
  * [Recon Screenshot Triage](#recon-screenshot-triage)
  * [Software / Tech Fingerprinting](#software--tech-fingerprinting)
  * [AI-Assisted Fuzzing](#ai-assisted-fuzzing)
  * [Password / Credential ML](#password--credential-ml)
  * [Phishing Detection (Visual / URL)](#phishing-detection-visual--url)
  * [AI/ML-Assisted Detection Rules & Engines](#aiml-assisted-detection-rules--engines)
  * [Defensive Trained-Model Detectors](#defensive-trained-model-detectors)
* [AI-Powered SAST & Secure Code Review](#ai-powered-sast--secure-code-review)
* [AI-Powered Threat Modeling](#ai-powered-threat-modeling)
* [LLM-Driven Fuzzing](#llm-driven-fuzzing)
  * [Harness / target generation](#harness--target-generation)
  * [Fuzzing the LLM](#fuzzing-the-llm)
* [Threat Intelligence](#threat-intelligence)
* [Log Analysis / SIEM / SOC Triage](#log-analysis--siem--soc-triage)
* [Reverse Engineering](#reverse-engineering)
* [LLM Red-Teaming & Guardrails](#llm-red-teaming--guardrails)
  * [Scanners, Evals & Guardrails](#scanners-evals--guardrails)
  * [Prompt-Injection Classifier Models](#prompt-injection-classifier-models)
  * [Specialty Security LLMs](#specialty-security-llms)
* [LLM Honeypots & Deception](#llm-honeypots--deception)
* [CTF / Exploit / Bug-Bounty Agents & Benchmarks](#ctf--exploit--bug-bounty-agents--benchmarks)
* [Cloud / IaC / DFIR / OSINT / Phishing](#cloud--iac--dfir--osint--phishing)
* [Related Awesome Lists](#related-awesome-lists)
* [Contributing](#contributing)
* [Contact](#contact)
* [License](#license)

***

## Autotriage of Security Findings

AI/LLM tools that triage, deduplicate, prioritize, or validate the output of scanners and finding sources.

* **[nano-analyzer](https://github.com/weareaisle/nano-analyzer) ⭐ 307 | 🐛 0 | 🌐 Python | 📅 2026-04-14** 🟢🔬 — Minimal three-stage LLM pipeline (context → scan → skeptical triage) for zero-day discovery in C/C++. *(AISLE)* *(★ 307 · updated 2026-04-14)*
* **[seclab-taskflow-agent](https://github.com/GitHubSecurityLab/seclab-taskflow-agent) ⭐ 221 | 🐛 26 | 🌐 Python | 📅 2026-08-13** 🟢 — YAML-driven taskflow agent framework for triaging CodeQL/SAST alerts and filtering false positives. *(GitHub Security Lab)* *(★ 221 · updated 2026-08-03)*
  * **Related:** [SigmaOptimizer](https://github.com/YusukeJustinNakajima/SigmaOptimizer) ⭐ 11 | 🐛 0 | 🌐 PowerShell | 📅 2025-08-01
* **[honeyslop](https://github.com/gadievron/honeyslop) ⭐ 97 | 🐛 0 | 🌐 Python | 📅 2026-05-20** 🟢 — Code-canary decoys to triage AI-hallucinated ("slop") vulnerability reports flooding bug-bounty programs. *(★ 97 · updated 2026-05-20)*
* **[SigmaOptimizer](https://github.com/YusukeJustinNakajima/SigmaOptimizer) ⭐ 11 | 🐛 0 | 🌐 PowerShell | 📅 2025-08-01** 🟢 — Generates, tests, and refines Sigma rules from real logs with false-positive checking. *(★ 11 · updated 2025-08-01)*
  * **Related:** [soctalk](https://github.com/soctalk/soctalk) ⭐ 78 | 🐛 34 | 🌐 Python | 📅 2026-08-12 · [seclab-taskflow-agent](https://github.com/GitHubSecurityLab/seclab-taskflow-agent) ⭐ 221 | 🐛 26 | 🌐 Python | 📅 2026-08-13
* **[nuclei-autotriage](https://github.com/cyberok-org/nuclei-autotriage) ⭐ 1 | 🐛 0 | 🌐 Python | 📅 2026-05-27** 🟢⚠️ — Two-stage LLM triage (falsifier + red-team pass) of Nuclei JSONL findings via OpenAI-compatible endpoints (vLLM/Ollama). *(CyberOK)* — **note:** restrictive personal/non-commercial EULA, not a permissive OSS license. *(★ 1 · updated 2026-05-25)*
  * **Related:** [agent-audit](https://github.com/scadastrangelove/agent-audit) ⭐ 15 | 🐛 2 | 🌐 Python | 📅 2026-07-15 · [asamm](https://github.com/scadastrangelove/asamm) ⭐ 17 | 🐛 2 | 🌐 HTML | 📅 2026-07-26
* **[ai-soc-triage-assistant](https://github.com/pranavibunny/ai-soc-triage-assistant) ⭐ 0 | 🐛 0 | 🌐 Python | 📅 2026-02-23** 🟢⚠️ — SOC alert triage assistant with prompt-injection guardrails, output validation, and MITRE ATT\&CK mapping. *(★ 0 · updated 2026-02-23)*

> See also: OpenAI's *Aardvark* research preview — public references exist, but there is no standalone installable repository to badge here.

***

## AI Agent & Coding-Agent Security

Securing the AI agents themselves — auditing coding agents (Claude Code, Codex, OpenClaw), scanning skills / plugins / MCP manifests, and governance for agentic development. A fast-moving 2026 category, split below by role.

### Scanners & Auditors

* **[SkillSpector](https://github.com/NVIDIA/SkillSpector) ⭐ 14,677 | 🐛 79 | 🌐 Python | 📅 2026-08-16** 🟢 — Security scanner for AI-agent skills used by Claude Code, Codex CLI, Gemini CLI, and similar ecosystems; combines static analysis, AST/YARA/taint checks, optional LLM semantic review, MCP least-privilege/tool-poisoning checks, risk scoring, and SARIF/JSON/Markdown output. *(NVIDIA)* *(★ 14,673 · updated 2026-08-15)*
  * **Related:** [Cisco AI Defense – skill-scanner](https://github.com/cisco-ai-defense/skill-scanner) ⭐ 2,435 | 🐛 7 | 🌐 Python | 📅 2026-08-04 · [skilltotal](https://github.com/pezhik/skilltotal) ⭐ 1 | 🐛 5 | 🌐 Python | 📅 2026-08-16 · [Snyk Agent Scan](https://github.com/snyk/agent-scan) ⭐ 2,913 | 🐛 9 | 🌐 Python | 📅 2026-08-16 · [Cisco AI Defense – mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14
* **[AI-Infra-Guard](https://github.com/Tencent/AI-Infra-Guard) ⭐ 4,513 | 🐛 18 | 🌐 Python | 📅 2026-08-12** 🟢 — Full-stack AI red-teaming platform covering OpenClaw security scan, agent scan, skills scan, MCP scan, AI-infra vulnerability scan, and LLM jailbreak evaluation. *(Tencent Zhuque Lab)* *(★ 4,512 · updated 2026-08-12)*
  * **Related:** [agent-audit](https://github.com/scadastrangelove/agent-audit) ⭐ 15 | 🐛 2 | 🌐 Python | 📅 2026-07-15 · [aguara](https://github.com/garagon/aguara) ⭐ 86 | 🐛 1 | 🌐 Go | 📅 2026-08-12 · [Cisco AI Defense – skill-scanner](https://github.com/cisco-ai-defense/skill-scanner) ⭐ 2,435 | 🐛 7 | 🌐 Python | 📅 2026-08-04 · [Cisco AI Defense – mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14
* **[agent-scan](https://github.com/snyk/agent-scan) ⭐ 2,913 | 🐛 9 | 🌐 Python | 📅 2026-08-16** 🟢 — Security scanner for AI agents, MCP servers, and agent skills; the successor path for the original Invariant Labs mcp-scan work. *(Snyk)* *(★ 2,912 · updated 2026-08-13)*
  * **Related:** [aguara](https://github.com/garagon/aguara) ⭐ 86 | 🐛 1 | 🌐 Go | 📅 2026-08-12 · [Cisco AI Defense – mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14 · [Cisco AI Defense – skill-scanner](https://github.com/cisco-ai-defense/skill-scanner) ⭐ 2,435 | 🐛 7 | 🌐 Python | 📅 2026-08-04
* **[skill-scanner](https://github.com/cisco-ai-defense/skill-scanner) ⭐ 2,435 | 🐛 7 | 🌐 Python | 📅 2026-08-04** 🟠 — Scanner for agent skills combining YAML + YARA patterns, LLM-as-a-judge, and behavioral dataflow analysis (Codex / Cursor skill formats). *(Cisco AI Defense)* *(★ 2,435 · updated 2026-08-04)*
  * **Related:** [defenseclaw](https://github.com/cisco-ai-defense/defenseclaw) ⭐ 819 | 🐛 42 | 🌐 Go | 📅 2026-08-16 · [aguara](https://github.com/garagon/aguara) ⭐ 86 | 🐛 1 | 🌐 Go | 📅 2026-08-12 · [Cisco AI Defense – mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14
* **[AgentShield](https://github.com/affaan-m/agentshield) ⭐ 1,068 | 🐛 23 | 🌐 TypeScript | 📅 2026-07-22** 🟢 — Security scanner for AI-agent configurations, MCP servers, hooks, and tool permissions with CLI, GitHub Action, and app workflows. *(★ 1,068 · updated 2026-07-22)*
  * **Related:** [agent-audit](https://github.com/scadastrangelove/agent-audit) ⭐ 15 | 🐛 2 | 🌐 Python | 📅 2026-07-15 · [Snyk Agent Scan](https://github.com/snyk/agent-scan) ⭐ 2,913 | 🐛 9 | 🌐 Python | 📅 2026-08-16
* **[agentic-radar](https://github.com/splx-ai/agentic-radar) ⭐ 1,036 | 🐛 15 | 🌐 Python | 📅 2025-11-27** 🟠 — CLI security scanner for agentic workflows (LangGraph, CrewAI, n8n, etc.) — maps tools/data flows and flags risks. *(SplxAI)* *(★ 1,036 · updated 2025-11-27)*
* **[mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14** 🟢⚠️ — Scanner for MCP servers and agentic tool surfaces, covering tools, prompts, resources, package risk, malware indicators, and deployment readiness. *(Cisco AI Defense)* *(★ 1,033 · updated 2026-08-07)*
  * **Related:** [Cisco AI Defense – skill-scanner](https://github.com/cisco-ai-defense/skill-scanner) ⭐ 2,435 | 🐛 7 | 🌐 Python | 📅 2026-08-04 · [Snyk Agent Scan](https://github.com/snyk/agent-scan) ⭐ 2,913 | 🐛 9 | 🌐 Python | 📅 2026-08-16 · [aguara](https://github.com/garagon/aguara) ⭐ 86 | 🐛 1 | 🌐 Go | 📅 2026-08-12
* **[MCP Observatory](https://github.com/KryptosAI/mcp-observatory) ⭐ 176 | 🐛 60 | 🌐 HTML | 📅 2026-08-15** 🟢🟠 — CI-native MCP-server testing tool for schema drift, safe attack simulation, record/replay verification, health scoring, and SARIF evidence before agents depend on a server. *(KryptosAI)* — **note:** the local evidence engine is open source; hosted telemetry intelligence, fleet workflows, and commercial ranking remain outside the package. *(★ 176 · updated 2026-08-15)*
  * **Related:** [Cisco AI Defense – mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14 · [skilltotal](https://github.com/pezhik/skilltotal) ⭐ 1 | 🐛 5 | 🌐 Python | 📅 2026-08-16
* **[A2A Security Scanner](https://github.com/cisco-ai-defense/a2a-scanner) ⭐ 162 | 🐛 4 | 🌐 Python | 📅 2026-04-16** 🟢 — CLI and PyPI scanner for Agent-to-Agent (A2A) agent cards, source code, registries, and live endpoints using specification validation, YARA rules, heuristics, endpoint testing, and an optional LLM analyzer. *(Cisco AI Defense)* *(★ 162 · updated 2026-04-16)*
  * **Related:** [Cisco AI Defense – mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14 · [Agent Threat Rules](https://github.com/Agent-Threat-Rule/agent-threat-rules) ⭐ 371 | 🐛 37 | 🌐 TypeScript | 📅 2026-08-16
* **[repo-forensics](https://github.com/alexgreensh/repo-forensics) ⭐ 155 | 🐛 2 | 🌐 Python | 📅 2026-08-08** 🟢⚠️ — Offline scanner for AI-agent repos, skills, plugins, and MCP servers; license is PolyForm Noncommercial. *(★ 155 · updated 2026-08-08)*
  * **Related:** [agent-audit](https://github.com/scadastrangelove/agent-audit) ⭐ 15 | 🐛 2 | 🌐 Python | 📅 2026-07-15 · [aguara](https://github.com/garagon/aguara) ⭐ 86 | 🐛 1 | 🌐 Go | 📅 2026-08-12
* **[mcp-armor](https://github.com/aira-security/mcp-armor) ⭐ 119 | 🐛 0 | 🌐 Python | 📅 2026-03-27** 🟢 — Local MCP security scanner with auto-discovery for agentic IDE configs, tool/resource/prompt inventory, prompt-injection checks, rug-pull and tool-poisoning detection, baseline drift monitoring, and JSON/Markdown reports. *(Aira Security)* *(★ 119 · updated 2026-03-27)*
  * **Related:** [SkillSpector](https://github.com/NVIDIA/SkillSpector) ⭐ 14,677 | 🐛 79 | 🌐 Python | 📅 2026-08-16 · [Ramparts](https://github.com/highflame-ai/ramparts) ⭐ 96 | 🐛 16 | 🌐 Rust | 📅 2026-08-07 · [Cisco AI Defense – mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14
* **[Ramparts](https://github.com/highflame-ai/ramparts) ⭐ 96 | 🐛 16 | 🌐 Rust | 📅 2026-08-07** 🟢 — Rust scanner for MCP servers and agent-skill bundles with YARA rules, optional LLM analysis, OSV/CVE lookups, OWASP MCP Top 10 mapping, and SARIF/JSON/Markdown reports. *(★ 96 · updated 2026-08-07)*
  * **Related:** [SkillSpector](https://github.com/NVIDIA/SkillSpector) ⭐ 14,677 | 🐛 79 | 🌐 Python | 📅 2026-08-16 · [Cisco AI Defense – skill-scanner](https://github.com/cisco-ai-defense/skill-scanner) ⭐ 2,435 | 🐛 7 | 🌐 Python | 📅 2026-08-04 · [Cisco AI Defense – mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14
* **[aguara](https://github.com/garagon/aguara) ⭐ 86 | 🐛 1 | 🌐 Go | 📅 2026-08-12** 🟢 — Single-binary static scanner (Go, no LLM) for AI-agent skills and MCP servers; multi-layer engine (pattern + NLP + taint tracking + rug-pull detection). Companion **[aguara-mcp](https://github.com/garagon/mcp-aguara) ⭐ 4 | 🐛 0 | 🌐 Go | 📅 2026-07-01** exposes scanning as an MCP tool. *(★ 86 · updated 2026-08-12)*
  * **Related:** [aguara-mcp](https://github.com/garagon/mcp-aguara) ⭐ 4 | 🐛 0 | 🌐 Go | 📅 2026-07-01 · [agent-audit](https://github.com/scadastrangelove/agent-audit) ⭐ 15 | 🐛 2 | 🌐 Python | 📅 2026-07-15 · [Snyk Agent Scan](https://github.com/snyk/agent-scan) ⭐ 2,913 | 🐛 9 | 🌐 Python | 📅 2026-08-16 · [Cisco AI Defense – skill-scanner](https://github.com/cisco-ai-defense/skill-scanner) ⭐ 2,435 | 🐛 7 | 🌐 Python | 📅 2026-08-04
* **[inkog](https://github.com/inkog-io/inkog) ⭐ 28 | 🐛 27 | 🌐 Go | 📅 2026-08-09** 🟠 — Commercial-backed static security scanner for AI agents across LangChain, LangGraph, CrewAI, AutoGen, and no-code workflows; Apache-2.0 CLI with proprietary deep-scan engine. *(Inkog)* *(★ 28 · updated 2026-06-07)*
  * **Related:** [Snyk Agent Scan](https://github.com/snyk/agent-scan) ⭐ 2,913 | 🐛 9 | 🌐 Python | 📅 2026-08-16 · [agentic-radar](https://github.com/splx-ai/agentic-radar) ⭐ 1,036 | 🐛 15 | 🌐 Python | 📅 2025-11-27
* **[trentclaw](https://github.com/trnt-ai/trent-openclaw-security-assessment) ⭐ 23 | 🐛 3 | 🌐 Python | 📅 2026-07-27** 🟠 — Client-side security auditor for OpenClaw deployments: applies pattern-based secret redaction locally, then uploads config/skill metadata and confirm-gated skill archives to Trent AI's API, which identifies misconfigurations, risky skills (prompt injection, permission escalation, data exfiltration), and chained attack paths. *(Trent AI)* — **note:** core detection runs server-side via the Trent AI API (requires an API key); the Apache-2.0 client collects OpenClaw config/skill metadata, applies pattern-based secret redaction locally, and uploads skill archives only after an explicit in-terminal confirmation. *(★ 23 · updated 2026-07-27)*
* **[agent-audit](https://github.com/scadastrangelove/agent-audit) ⭐ 15 | 🐛 2 | 🌐 Python | 📅 2026-07-15** 🟢 — Forensic auditor for local AI coding agents (Claude Code, Codex CLI, OpenClaw) **and** project-surface scanner for repos shipping skills, plugins, and MCP manifests; 296 bundled rules across native + imported detector families, with optional LLM cross-verification. *(CyberOK / S. Gordeychik)* *(★ 15 · updated 2026-07-15)*
  * **Sources:** [asamm](https://github.com/scadastrangelove/asamm) ⭐ 17 | 🐛 2 | 🌐 HTML | 📅 2026-07-26 · [ATR – Agent Threat Rules](https://github.com/Agent-Threat-Rule/agent-threat-rules) ⭐ 371 | 🐛 37 | 🌐 TypeScript | 📅 2026-08-16 · [aguara](https://github.com/garagon/aguara) ⭐ 86 | 🐛 1 | 🌐 Go | 📅 2026-08-12 · [Cisco AI Defense – skill-scanner](https://github.com/cisco-ai-defense/skill-scanner) ⭐ 2,435 | 🐛 7 | 🌐 Python | 📅 2026-08-04
  * **Related:** [asamm](https://github.com/scadastrangelove/asamm) ⭐ 17 | 🐛 2 | 🌐 HTML | 📅 2026-07-26 · [aguara](https://github.com/garagon/aguara) ⭐ 86 | 🐛 1 | 🌐 Go | 📅 2026-08-12 · [agentguard](https://github.com/GoPlusSecurity/agentguard) ⭐ 456 | 🐛 15 | 🌐 TypeScript | 📅 2026-06-25 · [agentic-radar](https://github.com/splx-ai/agentic-radar) ⭐ 1,036 | 🐛 15 | 🌐 Python | 📅 2025-11-27 · [nuclei-autotriage](https://github.com/cyberok-org/nuclei-autotriage) ⭐ 1 | 🐛 0 | 🌐 Python | 📅 2026-05-27
* **[mcp-guardian](https://github.com/alexandriashai/mcp-guardian) ⭐ 6 | 🐛 2 | 🌐 TypeScript | 📅 2026-07-29** 🟢 — JS/TS library and CLI for detecting prompt injection in MCP tool descriptions and pinning tool definitions. *(★ 6 · updated 2026-07-29)*
  * **Related:** [Cisco AI Defense – mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14 · [Snyk Agent Scan](https://github.com/snyk/agent-scan) ⭐ 2,913 | 🐛 9 | 🌐 Python | 📅 2026-08-16
* **[Sunglasses](https://github.com/sunglasses-dev/sunglasses) ⭐ 4 | 🐛 5 | 🌐 Python | 📅 2026-08-14** 🟢 — Local input/content scanner for AI agents that checks prompts, files, media metadata, skills, and tool descriptions against pattern and mechanism-based prompt-injection, exfiltration, command-injection, and agent-threat rules. — **note:** early-stage project; published precision/recall benchmark is self-reported by the project. *(★ 4 · updated 2026-08-14)*
  * **Related:** [skilltotal](https://github.com/pezhik/skilltotal) ⭐ 1 | 🐛 5 | 🌐 Python | 📅 2026-08-16 · [Armorer Guard](https://github.com/ArmorerLabs/Armorer-Guard) ⭐ 42 | 🐛 7 | 🌐 Rust | 📅 2026-08-09
* **[skilltotal](https://github.com/pezhik/skilltotal) ⭐ 1 | 🐛 5 | 🌐 Python | 📅 2026-08-16** 🟢 — Offline deterministic static scanner (regex + AST, no LLM, no account) for AI components — agent skills/plugins, MCP servers, npm & PyPI packages, and git repos; flags supply-chain risk, dangerous capabilities, prompt-injection surfaces, MCP tool poisoning/shadowing, and data-exfiltration paths, maps to the OWASP Agentic Skills Top 10, and emits JSON + SARIF 2.1.0. *(skilltotal.ai)* *(★ 1 · updated 2026-08-15)*
  * **Related:** [aguara](https://github.com/garagon/aguara) ⭐ 86 | 🐛 1 | 🌐 Go | 📅 2026-08-12 · [Snyk Agent Scan](https://github.com/snyk/agent-scan) ⭐ 2,913 | 🐛 9 | 🌐 Python | 📅 2026-08-16 · [Cisco AI Defense – skill-scanner](https://github.com/cisco-ai-defense/skill-scanner) ⭐ 2,435 | 🐛 7 | 🌐 Python | 📅 2026-08-04 · [Cisco AI Defense – mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14

### Frameworks, Rule Standards & Benchmarks

* **[Anthropic-Cybersecurity-Skills](https://github.com/mukul975/Anthropic-Cybersecurity-Skills) ⭐ 27,962 | 🐛 46 | 🌐 Python | 📅 2026-08-08** 🟢 — Large community cybersecurity skill library for AI agents, mapped to MITRE ATT\&CK, NIST CSF, MITRE ATLAS, D3FEND, and NIST AI RMF. — **note:** independent community project, not affiliated with Anthropic. *(★ 27,919 · updated 2026-08-08)*
  * **Related:** [sast-skills](https://github.com/utkusen/sast-skills) ⭐ 1,276 | 🐛 1 | 📅 2026-04-08 · [Cisco AI Defense – skill-scanner](https://github.com/cisco-ai-defense/skill-scanner) ⭐ 2,435 | 🐛 7 | 🌐 Python | 📅 2026-08-04
* **[Agent Governance Toolkit](https://github.com/microsoft/agent-governance-toolkit) ⭐ 5,955 | 🐛 189 | 🌐 Python | 📅 2026-08-14** 🟢 — Multi-language toolkit for policy-enforced agent tool calls and audit records, with optional identity, MCP-gateway, sandboxing, reliability, and compliance components. *(Microsoft)* — **note:** official public preview; APIs and deployment patterns may change before general availability. *(★ 5,953 · updated 2026-08-12)*
  * **Related:** [ATR – Agent Threat Rules](https://github.com/Agent-Threat-Rule/agent-threat-rules) ⭐ 371 | 🐛 37 | 🌐 TypeScript | 📅 2026-08-16 · [ToolHive](https://github.com/stacklok/toolhive) ⭐ 2,017 | 🐛 383 | 🌐 Go | 📅 2026-08-16
* **[Claude-BugHunter](https://github.com/elementalsouls/Claude-BugHunter) ⭐ 3,621 | 🐛 0 | 🌐 Python | 📅 2026-08-16** 🟢 — Claude Code / agent-skill bundle for authorized bug hunting and external red-team workflows across web, API, identity, cloud, recon, reporting, Burp MCP, slash commands, and the cbh CLI. — **note:** skill bundle and workflow knowledge base, not a standalone scanner. *(★ 3,616 · updated 2026-08-16)*
  * **Related:** [sast-skills](https://github.com/utkusen/sast-skills) ⭐ 1,276 | 🐛 1 | 📅 2026-04-08 · [Anthropic-Cybersecurity-Skills](https://github.com/mukul975/Anthropic-Cybersecurity-Skills) ⭐ 27,962 | 🐛 46 | 🌐 Python | 📅 2026-08-08
* **[MCP-Security-Checklist](https://github.com/slowmist/MCP-Security-Checklist) ⭐ 835 | 🐛 8 | 📅 2025-04-28** 🟢 — Security checklist for MCP clients, servers, multi-MCP deployments, lifecycle controls, authz/authn, isolation, and crypto-specific MCP integrations. *(SlowMist)* *(★ 835 · updated 2025-04-28)*
  * **Related:** [Cisco AI Defense – mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14 · [ATR – Agent Threat Rules](https://github.com/Agent-Threat-Rule/agent-threat-rules) ⭐ 371 | 🐛 37 | 🌐 TypeScript | 📅 2026-08-16
* **[AgentDojo](https://github.com/ethz-spylab/agentdojo) ⭐ 751 | 🐛 41 | 🌐 Python | 📅 2026-06-02** 🟢🔬 — Benchmark environment for prompt-injection attacks and defenses in tool-using LLM agents. *(★ 749 · updated 2026-06-02)*
  * **Related:** [agent-audit](https://github.com/scadastrangelove/agent-audit) ⭐ 15 | 🐛 2 | 🌐 Python | 📅 2026-07-15 · [ATR – Agent Threat Rules](https://github.com/Agent-Threat-Rule/agent-threat-rules) ⭐ 371 | 🐛 37 | 🌐 TypeScript | 📅 2026-08-16
* **[AI Security Verification Standard (AISVS)](https://github.com/OWASP/AISVS) ⭐ 428 | 🐛 10 | 📅 2026-07-30** 🔬⚠️ — Stable verification standard defining testable security requirements for AI applications across model lifecycle, supply chain, data handling, agentic systems, and MCP integrations. *(OWASP)* — **note:** security standard and checklist, not an executable scanner; share-alike terms apply to adapted material. *(★ 428 · updated 2026-07-30)*
  * **Related:** [asamm](https://github.com/scadastrangelove/asamm) ⭐ 17 | 🐛 2 | 🌐 HTML | 📅 2026-07-26 · [Agent Threat Rules](https://github.com/Agent-Threat-Rule/agent-threat-rules) ⭐ 371 | 🐛 37 | 🌐 TypeScript | 📅 2026-08-16
* **[agent-threat-rules (ATR)](https://github.com/Agent-Threat-Rule/agent-threat-rules) ⭐ 371 | 🐛 37 | 🌐 TypeScript | 📅 2026-08-16** 🟢 — Open, versioned, machine-readable detection rules for AI-agent threats (prompt injection, tool poisoning, MCP attacks, and skill compromise) — "Sigma for agents"; 768 rules across 10 categories with integrations for Microsoft AGT, Cisco AI Defense, MISP, OWASP, FINOS, and SigmaHQ. *(★ 371 · updated 2026-08-16)*
  * **Related:** [agent-audit](https://github.com/scadastrangelove/agent-audit) ⭐ 15 | 🐛 2 | 🌐 Python | 📅 2026-07-15 · [aguara](https://github.com/garagon/aguara) ⭐ 86 | 🐛 1 | 🌐 Go | 📅 2026-08-12
* **[Agent Security Bench (ASB)](https://github.com/agiresearch/ASB) ⭐ 284 | 🐛 4 | 🌐 Python | 📅 2026-04-16** 🟢🔬 — Official ICLR 2025 benchmark for evaluating attacks and defenses in LLM-based agents across ten scenarios, including direct and indirect prompt injection, memory poisoning, and defensive strategies. — **note:** research benchmark rather than a production control; reproducing evaluations requires configured target and evaluator models. *(★ 284 · updated 2026-04-16)*
  * **Related:** [AgentDojo](https://github.com/ethz-spylab/agentdojo) ⭐ 751 | 🐛 41 | 🌐 Python | 📅 2026-06-02 · [Agent3Sigma-Canary](https://github.com/antgroup/Agent3Sigma-Canary) ⭐ 35 | 🐛 0 | 🌐 Python | 📅 2026-08-09
* **[Skill-Inject](https://github.com/aisa-group/skill-inject) ⭐ 91 | 🐛 1 | 🌐 Python | 📅 2026-08-03** 🟢🔬 — Benchmark for measuring prompt-injection vulnerabilities carried by agent skill files across Claude Code, Codex CLI, and Gemini CLI under multiple safety-policy conditions. — **note:** benchmark artifact that executes controlled malicious skill scenarios; run only in an isolated test environment with synthetic data and accounts. *(★ 91 · updated 2026-07-01)*
  * **Related:** [SkillSpector](https://github.com/NVIDIA/SkillSpector) ⭐ 14,677 | 🐛 79 | 🌐 Python | 📅 2026-08-16 · [AgentDojo](https://github.com/ethz-spylab/agentdojo) ⭐ 751 | 🐛 41 | 🌐 Python | 📅 2026-06-02
* **[Agent3Sigma-Canary](https://github.com/antgroup/Agent3Sigma-Canary) ⭐ 35 | 🐛 0 | 🌐 Python | 📅 2026-08-09** 🟢🔬 — Sandboxed research framework for evaluating AI-agent security over complete execution trajectories, covering direct/indirect injection, skill and memory poisoning, and practical risk outcomes. *(Ant Group)* — **note:** research framework that requires Docker plus target and auxiliary LLM configuration; use only in controlled environments. *(★ 35 · updated 2026-08-09)*
  * **Related:** [AgentDojo](https://github.com/ethz-spylab/agentdojo) ⭐ 751 | 🐛 41 | 🌐 Python | 📅 2026-06-02 · [HarmBench](https://github.com/centerforaisafety/HarmBench) ⭐ 1,029 | 🐛 39 | 🌐 Jupyter Notebook | 📅 2024-08-16
* **[asamm](https://github.com/scadastrangelove/asamm) ⭐ 17 | 🐛 2 | 🌐 HTML | 📅 2026-07-26** 🔬 — *Agentic SAMM* — an OWASP SAMM extension for AI-driven development: an entry-point-based threat taxonomy plus 17 controls across 5 SAMM functions (Governance, Design, Implementation, Verification, Operations) with L1/L2/L3 maturity. License: CC BY-SA 4.0. *(CyberOK / S. Gordeychik)* *(★ 17 · updated 2026-07-26)*
  * **Related:** [agent-audit](https://github.com/scadastrangelove/agent-audit) ⭐ 15 | 🐛 2 | 🌐 Python | 📅 2026-07-15
  * **Sources:** [OWASP SAMM](https://owaspsamm.org/) · [NIST AI RMF](https://www.nist.gov/itl/ai-risk-management-framework) · [NCSC Secure AI Guidelines](https://www.ncsc.gov.uk/collection/guidelines-secure-ai-system-development) · [MCP Security Best Practices](https://modelcontextprotocol.io/)

### Runtime Protection & Enforcement

* **[microsandbox](https://github.com/superradcompany/microsandbox) ⭐ 7,552 | 🐛 68 | 🌐 Rust | 📅 2026-08-16** 🟢 — Local-first, microVM-backed programmable sandboxes for AI agents with SDKs, CLI, MCP support, and rootless hardware isolation. *(★ 7,548 · updated 2026-08-16)*
  * **Related:** [agentguard](https://github.com/GoPlusSecurity/agentguard) ⭐ 456 | 🐛 15 | 🌐 TypeScript | 📅 2026-06-25 · [defenseclaw](https://github.com/cisco-ai-defense/defenseclaw) ⭐ 819 | 🐛 42 | 🌐 Go | 📅 2026-08-16
* **[AIO Sandbox](https://github.com/agent-infra/sandbox) ⭐ 5,721 | 🐛 71 | 🌐 Python | 📅 2026-07-02** 🟢⚠️ — All-in-one Docker workspace for AI agents with browser, shell, file, code-execution, MCP, and VSCode interfaces, plus API-key/JWT controls and private-deployment guidance. — **note:** the public repository ships SDKs, integrations, and docs rather than the core runtime service; official Chromium-enabled deployments use `seccomp=unconfined`. Treat it as a trusted execution environment, not a hardened isolation boundary; use separate VMs or a hardened runtime plus network policy for hostile workloads. *(★ 5,719 · updated 2026-07-02)*
  * **Related:** [Kubernetes Agent Sandbox](https://github.com/kubernetes-sigs/agent-sandbox) ⭐ 3,535 | 🐛 225 | 🌐 Go | 📅 2026-08-16 · [microsandbox](https://github.com/superradcompany/microsandbox) ⭐ 7,552 | 🐛 68 | 🌐 Rust | 📅 2026-08-16
* **[Agentgateway](https://github.com/agentgateway/agentgateway) ⭐ 4,376 | 🐛 345 | 🌐 Rust | 📅 2026-08-14** 🟢 — Agent-native proxy and gateway for MCP and A2A traffic with OAuth/JWT/API-key authentication, CEL-based RBAC policies, TLS, rate limiting, and OpenTelemetry observability. *(★ 4,373 · updated 2026-08-14)*
  * **Related:** [MCP Gateway](https://github.com/lasso-security/mcp-gateway) ⭐ 385 | 🐛 12 | 🌐 Python | 📅 2026-01-22 · [Pipelock](https://github.com/luckyPipewrench/pipelock) ⭐ 796 | 🐛 3 | 🌐 Go | 📅 2026-08-16
* **[nono](https://github.com/nolabs-ai/nono) ⭐ 3,676 | 🐛 147 | 🌐 Rust | 📅 2026-08-15** 🟢 — Least-privilege sandbox for AI coding agents that isolates the agent and delegated tools with composable filesystem, network, credential-proxy, and command policies. *(NoLabs)* — **note:** APIs are still stabilizing ahead of the 1.0 release; review every pulled profile before use. *(★ 3,672 · updated 2026-08-13)*
  * **Related:** [microsandbox](https://github.com/superradcompany/microsandbox) ⭐ 7,552 | 🐛 68 | 🌐 Rust | 📅 2026-08-16 · [ToolHive](https://github.com/stacklok/toolhive) ⭐ 2,017 | 🐛 383 | 🌐 Go | 📅 2026-08-16
* **[Kubernetes Agent Sandbox](https://github.com/kubernetes-sigs/agent-sandbox) ⭐ 3,535 | 🐛 225 | 🌐 Go | 📅 2026-08-16** 🟢 — Kubernetes CRDs and controllers for isolated, stateful singleton agent workloads, delegating low-level isolation to configured runtimes such as gVisor or Kata Containers. *(Kubernetes SIG Apps)* — **note:** sandbox orchestrator, not an isolation runtime itself; security depends on the selected RuntimeClass, network policy, and workload configuration. *(★ 3,532 · updated 2026-08-16)*
  * **Related:** [AIO Sandbox](https://github.com/agent-infra/sandbox) ⭐ 5,721 | 🐛 71 | 🌐 Python | 📅 2026-07-02
  * **Sources:** [Kubernetes announcement](https://kubernetes.io/blog/2026/03/20/running-agents-on-kubernetes-with-agent-sandbox/)
* **[onecli](https://github.com/onecli/onecli) ⭐ 3,097 | 🐛 121 | 🌐 TypeScript | 📅 2026-08-15** 🟢 — Credential gateway and encrypted vault for AI agents; injects real API credentials at the gateway so agents only see placeholder keys. *(★ 3,095 · updated 2026-07-31)*
  * **Related:** [agentguard](https://github.com/GoPlusSecurity/agentguard) ⭐ 456 | 🐛 15 | 🌐 TypeScript | 📅 2026-06-25 · [defenseclaw](https://github.com/cisco-ai-defense/defenseclaw) ⭐ 819 | 🐛 42 | 🌐 Go | 📅 2026-08-16
* **[tirith](https://github.com/sheeki03/tirith) ⭐ 2,663 | 🐛 11 | 🌐 Rust | 📅 2026-08-16** 🟢⚠️ — Terminal guard for developers and AI coding agents that intercepts homograph and terminal-injection tricks, obfuscated execution chains, pipe-to-shell patterns, credential exfiltration, and malicious skill/config files. — **note:** AGPL-3.0 with a separate commercial license; shell interception is a host-side guard, not a substitute for sandboxing or least-privilege tool access. *(★ 2,663 · updated 2026-08-13)*
  * **Related:** [nono](https://github.com/nolabs-ai/nono) ⭐ 3,676 | 🐛 147 | 🌐 Rust | 📅 2026-08-15 · [gate.cat](https://github.com/BGMLAI/gate.cat) ⭐ 1 | 🐛 5 | 🌐 Python | 📅 2026-08-16
* **[ToolHive](https://github.com/stacklok/toolhive) ⭐ 2,017 | 🐛 383 | 🌐 Go | 📅 2026-08-16** 🟢 — Platform for running MCP servers in isolated containers with per-request identity/access policy, registry and gateway workflows, audit logs, Kubernetes operator support, and observability hooks. *(Stacklok)* *(★ 2,016 · updated 2026-08-14)*
  * **Related:** [microsandbox](https://github.com/superradcompany/microsandbox) ⭐ 7,552 | 🐛 68 | 🌐 Rust | 📅 2026-08-16 · [defenseclaw](https://github.com/cisco-ai-defense/defenseclaw) ⭐ 819 | 🐛 42 | 🌐 Go | 📅 2026-08-16
* **[ADR](https://github.com/uber/ADR) ⭐ 1,435 | 🐛 8 | 🌐 Python | 📅 2026-08-15** 🟢🔬 — Agentic AI Detection and Response system combining cross-client agent telemetry, ADR-Bench security scenarios, and a dual-agent detector for suspicious intent, tool use, and execution traces. *(Uber)* — **note:** deployed at Uber and published with an MLSys 2026 paper; the open release includes the Sensor, benchmark, and Detector, but not ADR Prevention or the offline ADR Explorer. Default detector configurations require model-provider credentials. *(★ 1,435 · updated 2026-08-10)*
  * **Related:** [Pipelock](https://github.com/luckyPipewrench/pipelock) ⭐ 796 | 🐛 3 | 🌐 Go | 📅 2026-08-16 · [AgentLock](https://github.com/webpro255/agentlock) ⭐ 19 | 🐛 0 | 🌐 Python | 📅 2026-08-12
* **[clawsec](https://github.com/prompt-security/clawsec) ⭐ 1,083 | 🐛 34 | 🌐 JavaScript | 📅 2026-08-16** 🟢⚠️ — Security skill suite for OpenClaw-family agents; AGPL-3.0 licensed. *(Prompt Security)* *(★ 1,083 · updated 2026-08-05)*
  * **Related:** [agentguard](https://github.com/GoPlusSecurity/agentguard) ⭐ 456 | 🐛 15 | 🌐 TypeScript | 📅 2026-06-25 · [Cisco AI Defense – skill-scanner](https://github.com/cisco-ai-defense/skill-scanner) ⭐ 2,435 | 🐛 7 | 🌐 Python | 📅 2026-08-04
* **[defenseclaw](https://github.com/cisco-ai-defense/defenseclaw) ⭐ 819 | 🐛 42 | 🌐 Go | 📅 2026-08-16** 🟠 — Enforcement and evidence layer for agentic deployments: static CodeGuard checks, sandboxing, registry ingestion with SSRF guards, and audit/observability. *(Cisco AI Defense)* *(★ 819 · updated 2026-08-14)*
  * **Related:** [Cisco AI Defense – skill-scanner](https://github.com/cisco-ai-defense/skill-scanner) ⭐ 2,435 | 🐛 7 | 🌐 Python | 📅 2026-08-04 · [agentguard](https://github.com/GoPlusSecurity/agentguard) ⭐ 456 | 🐛 15 | 🌐 TypeScript | 📅 2026-06-25
* **[Pipelock](https://github.com/luckyPipewrench/pipelock) ⭐ 796 | 🐛 3 | 🌐 Go | 📅 2026-08-16** 🟢 — AI-agent firewall and verifiable egress-control layer mediating HTTP, WebSocket, CONNECT, MCP, and A2A traffic to detect prompt injection, secret exfiltration, SSRF, and suspicious outbound actions. — **note:** open-source core is Apache-2.0; commercial reporting/features are also advertised. *(★ 796 · updated 2026-08-16)*
  * **Related:** [ToolHive](https://github.com/stacklok/toolhive) ⭐ 2,017 | 🐛 383 | 🌐 Go | 📅 2026-08-16 · [mcp-context-protector](https://github.com/trailofbits/mcp-context-protector) ⭐ 222 | 🐛 14 | 🌐 Python | 📅 2026-04-14
* **[Arcjet Guard](https://github.com/arcjet/arcjet-js) ⭐ 681 | 🐛 5 | 🌐 TypeScript | 📅 2026-08-15** 🟢🟠 — JavaScript runtime guard for AI-agent tool calls and MCP handlers, with prompt-injection detection, sensitive-data detection/redaction, and custom local policy rules. *(Arcjet)* — **note:** open SDK packages integrate with Arcjet's hosted platform; assess the service, account, and data-processing requirements for the protections you enable. *(★ 680 · updated 2026-08-15)*
  * **Related:** [LLM Guard](https://github.com/protectai/llm-guard) ⚠️ Archived · [AgentLock](https://github.com/webpro255/agentlock) ⭐ 19 | 🐛 0 | 🌐 Python | 📅 2026-08-12
* **[h5i](https://github.com/h5i-dev/h5i) ⭐ 531 | 🐛 8 | 🌐 Rust | 📅 2026-08-16** 🟢 — Local Rust CLI for auditable coding-agent workspaces: per-agent worktrees with sandbox policies, provenance capture, peer review, neutral verification, secret/prompt-injection audit signals, and refs/h5i/\* run metadata. — **note:** security-adjacent agent-workspace governance tool, not a vulnerability scanner or VM-equivalent sandbox. *(★ 531 · updated 2026-08-16)*
  * **Related:** [microsandbox](https://github.com/superradcompany/microsandbox) ⭐ 7,552 | 🐛 68 | 🌐 Rust | 📅 2026-08-16 · [defenseclaw](https://github.com/cisco-ai-defense/defenseclaw) ⭐ 819 | 🐛 42 | 🌐 Go | 📅 2026-08-16
* **[agentguard](https://github.com/GoPlusSecurity/agentguard) ⭐ 456 | 🐛 15 | 🌐 TypeScript | 📅 2026-06-25** 🟢 — Real-time security layer for coding agents: hooks scan every new skill, block dangerous actions before execution, run daily posture patrols, and track which skill triggered each action (incl. Web3-specific checks). *(★ 456 · updated 2026-06-25)*
  * **Related:** [agent-audit](https://github.com/scadastrangelove/agent-audit) ⭐ 15 | 🐛 2 | 🌐 Python | 📅 2026-07-15 · [defenseclaw](https://github.com/cisco-ai-defense/defenseclaw) ⭐ 819 | 🐛 42 | 🌐 Go | 📅 2026-08-16
* **[emisar](https://github.com/AndrewDryga/emisar) ⭐ 416 | 🐛 0 | 🌐 Elixir | 📅 2026-08-15** 🟠⚠️ — Agent-infrastructure control plane that exposes declared, typed actions through MCP, applies policy and approval gates before dispatch, revalidates calls on an outbound-only host runner, and records separate control-plane and host audit trails. — **note:** runner, MCP bridge, and packs are Apache-2.0; the hosted portal/control plane is BSL-1.1 and converts to Apache-2.0 on 2029-07-26. Connecting a runner requires an emisar account and outbound HTTPS to the control plane. *(★ 416 · updated 2026-08-15)*
* **[MCP Gateway](https://github.com/lasso-security/mcp-gateway) ⭐ 385 | 🐛 12 | 🌐 Python | 📅 2026-01-22** 🟢 — Plugin-based MCP gateway that proxies configured MCP servers, sanitizes sensitive request/response data, supports guardrail plugins such as basic masking and Presidio, and runs a server reputation/risk check before loading MCP servers. *(Lasso Security)* *(★ 385 · updated 2026-01-22)*
  * **Related:** [ToolHive](https://github.com/stacklok/toolhive) ⭐ 2,017 | 🐛 383 | 🌐 Go | 📅 2026-08-16 · [Pipelock](https://github.com/luckyPipewrench/pipelock) ⭐ 796 | 🐛 3 | 🌐 Go | 📅 2026-08-16 · [mcp-context-protector](https://github.com/trailofbits/mcp-context-protector) ⭐ 222 | 🐛 14 | 🌐 Python | 📅 2026-04-14
* **[Prismor](https://github.com/PrismorSec/prismor) ⭐ 290 | 🐛 43 | 🌐 Python | 📅 2026-08-16** 🟢 — Self-hosted runtime control plane for coding agents with pre-tool-call hooks, policy-driven observe/approve/block decisions, an MCP gateway, secret and egress controls, and tamper-evident audit evidence. *(★ 290 · updated 2026-08-16)*
  * **Related:** [Armorer Guard](https://github.com/ArmorerLabs/Armorer-Guard) ⭐ 42 | 🐛 7 | 🌐 Rust | 📅 2026-08-09 · [AgentLock](https://github.com/webpro255/agentlock) ⭐ 19 | 🐛 0 | 🌐 Python | 📅 2026-08-12
* **[MCP Defender](https://github.com/MCP-Defender/MCP-Defender) ⭐ 255 | 🐛 5 | 🌐 TypeScript | 📅 2026-06-05** 🟢⚠️ — Desktop app that proxies MCP tool-call requests and responses for Cursor, Claude, VS Code, and Windsurf, checks intercepted traffic against signatures, and prompts users to allow or block suspicious calls. — **note:** AGPL-3.0 licensed; project has been acquired by Docker. *(★ 255 · updated 2026-06-05)*
  * **Related:** [ToolHive](https://github.com/stacklok/toolhive) ⭐ 2,017 | 🐛 383 | 🌐 Go | 📅 2026-08-16 · [mcp-context-protector](https://github.com/trailofbits/mcp-context-protector) ⭐ 222 | 🐛 14 | 🌐 Python | 📅 2026-04-14
* **[mcp-context-protector](https://github.com/trailofbits/mcp-context-protector) ⭐ 222 | 🐛 14 | 🌐 Python | 📅 2026-04-14** 🟢 — MCP security wrapper that sits in front of downstream MCP servers, scans tool responses with guardrail providers, and supports quarantine/review workflows for desktop and coding-agent MCP configs. *(Trail of Bits)* *(★ 222 · updated 2026-02-13)*
  * **Related:** [Cisco AI Defense – mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) ⭐ 1,033 | 🐛 53 | 🌐 Python | 📅 2026-08-14 · [ToolHive](https://github.com/stacklok/toolhive) ⭐ 2,017 | 🐛 383 | 🌐 Go | 📅 2026-08-16 · [Pipelock](https://github.com/luckyPipewrench/pipelock) ⭐ 796 | 🐛 3 | 🌐 Go | 📅 2026-08-16
* **[Agent Memory Guard](https://github.com/OWASP/www-project-agent-memory-guard) ⭐ 126 | 🐛 14 | 🌐 Python | 📅 2026-08-16** 🟢 — Runtime middleware for AI-agent memory reads and writes, screening prompt injection, memory poisoning, secret/PII leakage, protected-key tampering, and size anomalies before persisted memory is reused. *(OWASP)* — **note:** OWASP Incubator project; published benchmark numbers are project-reported and should be independently reproduced before production enforcement. *(★ 125 · updated 2026-08-16)*
* **[DvalinCode](https://github.com/arthurpanhku/dvalincode) ⭐ 112 | 🐛 11 | 🌐 TypeScript | 📅 2026-08-11** 🟢 — Local-first AI coding agent with runtime governance controls: org/repo policy gates for tools, models, MCP servers, paths, and commands, plus provider/shell/MCP egress controls and hash-chained audit logs. — **note:** young project with limited independent adoption signal. *(★ 112 · updated 2026-08-11)*
  * **Related:** [h5i](https://github.com/h5i-dev/h5i) ⭐ 531 | 🐛 8 | 🌐 Rust | 📅 2026-08-16 · [Pipelock](https://github.com/luckyPipewrench/pipelock) ⭐ 796 | 🐛 3 | 🌐 Go | 📅 2026-08-16 · [Armorer Guard](https://github.com/ArmorerLabs/Armorer-Guard) ⭐ 42 | 🐛 7 | 🌐 Rust | 📅 2026-08-09
* **[Armorer Guard](https://github.com/ArmorerLabs/Armorer-Guard) ⭐ 42 | 🐛 7 | 🌐 Rust | 📅 2026-08-09** 🟢 — Local Rust scanner and MCP proxy for AI-agent prompt injection, credential leakage, exfiltration, and risky tool-call arguments, with structured reasons and no scanner network calls. — **note:** young project with limited independent adoption signal. *(★ 42 · updated 2026-08-09)*
  * **Related:** [agentguard](https://github.com/GoPlusSecurity/agentguard) ⭐ 456 | 🐛 15 | 🌐 TypeScript | 📅 2026-06-25 · [ATR – Agent Threat Rules](https://github.com/Agent-Threat-Rule/agent-threat-rules) ⭐ 371 | 🐛 37 | 🌐 TypeScript | 📅 2026-08-16
* **[Parallax](https://github.com/agent-defense/parallax) ⭐ 35 | 🐛 1 | 🌐 Rust | 📅 2026-07-17** 🟢 — Rust runtime policy engine for AI agents: evaluates lifecycle events with regex, keyword, Sigma, CEL, and SQL rules to block or redact prompt injection, data exfiltration, dangerous tool calls, and secret leakage. — **note:** early-stage project with limited adoption signal. *(★ 35 · updated 2026-06-05)*
  * **Related:** [Pipelock](https://github.com/luckyPipewrench/pipelock) ⭐ 796 | 🐛 3 | 🌐 Go | 📅 2026-08-16 · [Armorer Guard](https://github.com/ArmorerLabs/Armorer-Guard) ⭐ 42 | 🐛 7 | 🌐 Rust | 📅 2026-08-09
* **[AgentLock](https://github.com/webpro255/agentlock) ⭐ 19 | 🐛 0 | 🌐 Python | 📅 2026-08-12** 🟢🔬⚠️ — Pre-action authorization gate for LLM agent tool calls that decides from session provenance rather than content, with deny-by-default tool permissions, parameter lineage, Ed25519 signed receipts, and a hash-chained audit log; AGPL-3.0 licensed with commercial options. — **note:** evaluated on AgentDojo with predictions pre-registered before the runs; the published results include a suite where the defense costs more utility than the attack it prevents. *(★ 19 · updated 2026-08-12)*
* **[SourceryKit](https://github.com/ProvablyAI/sourcerykit) ⭐ 18 | 🐛 16 | 🌐 Python | 📅 2026-08-12** 🟠⚠️ — Python SDK for agent guardrails that intercepts outbound HTTP calls, enforces trusted-endpoint policies, logs requests, and checks agent handoff claims against a Provably backend before propagation. *(ProvablyAI)* — **note:** BSL-1.1 licensed; requires Provably backend/API credentials and database setup. *(★ 18 · updated 2026-08-12)*
  * **Related:** [Pipelock](https://github.com/luckyPipewrench/pipelock) ⭐ 796 | 🐛 3 | 🌐 Go | 📅 2026-08-16 · [mcp-context-protector](https://github.com/trailofbits/mcp-context-protector) ⭐ 222 | 🐛 14 | 🌐 Python | 📅 2026-04-14
* **[TAP](https://github.com/holonym-foundation/tap-oss) ⭐ 12 | 🐛 0 | 🌐 Rust | 📅 2026-07-23** 🟢🟠 — Credential-isolation proxy and MCP server for AI agents: agents send placeholder credentials, TAP injects real secrets server-side after per-action policy checks, with optional human approval on sensitive calls. *(human.tech)* — **note:** Apache-2.0 runtime is self-hostable, but the hosted dashboard and managed-service deployment glue are proprietary; self-hosting puts credential/key isolation and policy-engine hardening on the operator. *(★ 12 · updated 2026-07-23)*

***

## AI/ML Supply Chain & Model Security

Tools for securing model artifacts, serialized ML files, AI/ML supply-chain surfaces, and malicious-package detection datasets/benchmarks.

* **[Adversarial Robustness Toolbox (ART)](https://github.com/Trusted-AI/adversarial-robustness-toolbox) ⭐ 6,178 | 🐛 19 | 🌐 Python | 📅 2025-12-12** 🟢 — Flagship machine-learning security library for evaluating and defending models against evasion, poisoning, extraction, and inference attacks across major ML frameworks. *(LF AI & Data / IBM)* *(★ 6,178 · updated 2025-11-13)*
  * **Related:** [Foolbox](https://github.com/bethgelab/foolbox) ⭐ 2,972 | 🐛 29 | 🌐 Python | 📅 2025-12-03 · [PrivacyRaven](https://github.com/trailofbits/PrivacyRaven) ⚠️ Archived
* **[Foolbox](https://github.com/bethgelab/foolbox) ⭐ 2,972 | 🐛 29 | 🌐 Python | 📅 2025-12-03** 🟢 — Classic Python toolbox for generating adversarial examples and benchmarking robustness of PyTorch, TensorFlow, and JAX models. *(★ 2,972 · updated 2024-03-04)*
  * **Related:** [Adversarial Robustness Toolbox](https://github.com/Trusted-AI/adversarial-robustness-toolbox) ⭐ 6,178 | 🐛 19 | 🌐 Python | 📅 2025-12-12
* **[GuardDog](https://github.com/DataDog/guarddog) ⭐ 1,184 | 🐛 18 | 🌐 Python | 📅 2026-08-14** 🟢 — CLI for detecting malicious PyPI, npm, Go, RubyGems, GitHub Actions, and VSCode extension packages using Semgrep rules and package-metadata heuristics. *(Datadog)* *(★ 1,184 · updated 2026-08-14)*
  * **Related:** [malicious-software-packages-dataset](https://github.com/DataDog/malicious-software-packages-dataset) ⭐ 372 | 🐛 9 | 🌐 Python | 📅 2026-08-14 · [Packj](https://github.com/ossillate-inc/packj) ⭐ 691 | 🐛 13 | 🌐 Python | 📅 2026-04-12
* **[Medusa](https://github.com/Pantheon-Security/medusa) ⭐ 964 | 🐛 2 | 🌐 Python | 📅 2026-08-10** 🟢⚠️ — AI-first security scanner for AI/ML repos, agents, and MCP surfaces; AGPL-3.0 licensed. *(Pantheon Security)* *(★ 964 · updated 2026-06-24)*
  * **Related:** [agent-audit](https://github.com/scadastrangelove/agent-audit) ⭐ 15 | 🐛 2 | 🌐 Python | 📅 2026-07-15 · [modelscan](https://github.com/protectai/modelscan) ⭐ 762 | 🐛 77 | 🌐 Python | 📅 2026-02-18
* **[package-analysis](https://github.com/ossf/package-analysis) ⭐ 903 | 🐛 83 | 🌐 Go | 📅 2026-08-07** 🟢🔬 — Sandboxed static/dynamic analysis pipeline for open-source packages, capturing filesystem, process, and network behavior and publishing data for malicious-package research. *(OpenSSF)* *(★ 903 · updated 2026-07-21)*
  * **Related:** [malicious-packages](https://github.com/ossf/malicious-packages) ⭐ 598 | 🐛 47 | 🌐 Go | 📅 2026-08-16 · [package-feeds](https://github.com/ossf/package-feeds) ⭐ 90 | 🐛 33 | 🌐 Go | 📅 2026-06-01
* **[modelscan](https://github.com/protectai/modelscan) ⭐ 762 | 🐛 77 | 🌐 Python | 📅 2026-02-18** 🟢 — Scans ML model files for unsafe serialization patterns and embedded code, with a focus on model serialization attacks. *(Protect AI)* *(★ 762 · updated 2026-02-18)*
  * **Related:** [Fickling](https://github.com/trailofbits/fickling) ⭐ 662 | 🐛 13 | 🌐 Python | 📅 2026-08-13 · [picklescan](https://github.com/mmaitre314/picklescan) ⭐ 418 | 🐛 3 | 🌐 Python | 📅 2026-07-23 · [ai-exploits](https://github.com/protectai/ai-exploits) ⭐ 1,745 | 🐛 3 | 🌐 Python | 📅 2024-10-23
* **[Fickling](https://github.com/trailofbits/fickling) ⭐ 662 | 🐛 13 | 🌐 Python | 📅 2026-08-13** 🟢 — Python pickle decompiler, rewriter, and static analyzer for inspecting and detecting malicious pickle/PyTorch payloads. *(Trail of Bits)* *(★ 662 · updated 2026-08-13)*
  * **Related:** [modelscan](https://github.com/protectai/modelscan) ⭐ 762 | 🐛 77 | 🌐 Python | 📅 2026-02-18 · [picklescan](https://github.com/mmaitre314/picklescan) ⭐ 418 | 🐛 3 | 🌐 Python | 📅 2026-07-23
* **[gym-malware](https://github.com/endgameinc/gym-malware) ⭐ 636 | 🐛 14 | 🌐 Python | 📅 2022-11-21** 🟢🔬 — OpenAI Gym environment for reinforcement-learning agents that mutate PE malware to evade static ML malware detectors. *(★ 636 · updated 2018-06-15)*
* **[deep-pwning](https://github.com/cchio/deep-pwning) ⭐ 571 | 🐛 5 | 🌐 Python | 📅 2023-03-25** 🟢🔬 — Historical "Metasploit for machine learning" framework for experimenting with adversarial robustness of ML models. *(★ 571 · updated 2022-05-17)*
* **[picklescan](https://github.com/mmaitre314/picklescan) ⭐ 418 | 🐛 3 | 🌐 Python | 📅 2026-07-23** 🟢 — Lightweight CLI/library for detecting suspicious Python pickle operations in ML and model artifacts. *(★ 418 · updated 2026-07-01)*
  * **Related:** [modelscan](https://github.com/protectai/modelscan) ⭐ 762 | 🐛 77 | 🌐 Python | 📅 2026-02-18 · [Fickling](https://github.com/trailofbits/fickling) ⭐ 662 | 🐛 13 | 🌐 Python | 📅 2026-08-13
* **[malicious-software-packages-dataset](https://github.com/DataDog/malicious-software-packages-dataset) ⭐ 372 | 🐛 9 | 🌐 Python | 📅 2026-08-14** 🟢🔬 — Human-vetted dataset of malicious software packages across npm, PyPI, IDE extensions, and AI Skills, useful for detector training and evaluation. *(Datadog Security Labs)* — **note:** contains real malware samples; Datadog notes selection bias because many samples were identified by GuardDog. *(★ 371 · updated 2026-08-14)*
  * **Related:** [GuardDog](https://github.com/DataDog/guarddog) ⭐ 1,184 | 🐛 18 | 🌐 Python | 📅 2026-08-14 · [pypi\_malregistry](https://github.com/lxyeternal/pypi_malregistry) ⭐ 129 | 🐛 3 | 🌐 Python | 📅 2026-07-21
* **[PrivacyRaven](https://github.com/trailofbits/PrivacyRaven) ⚠️ Archived** 🟢🔬 — Privacy-testing library for deep-learning systems, covering model extraction and membership-inference style attacks. *(Trail of Bits)* — **note:** archived/hiatus project, but still a useful reference implementation. *(★ 214 · updated 2025-09-05)*
  * **Related:** [Adversarial Robustness Toolbox](https://github.com/Trusted-AI/adversarial-robustness-toolbox) ⭐ 6,178 | 🐛 19 | 🌐 Python | 📅 2025-12-12
* **[Fraim](https://github.com/fraim-dev/fraim) ⭐ 160 | 🐛 22 | 🌐 Python | 📅 2026-02-09** 🟢 — Framework for AI-powered security workflows including LLM SAST and IaC analysis with SARIF/HTML output. *(★ 160 · updated 2025-12-01)*
  * **Related:** [sast-skills](https://github.com/utkusen/sast-skills) ⭐ 1,276 | 🐛 1 | 📅 2026-04-08
* **[malicious-code-ruleset](https://github.com/apiiro/malicious-code-ruleset) ⭐ 149 | 🐛 4 | 🌐 Python | 📅 2025-02-24** 🟢 — Focused Semgrep ruleset for malicious-code patterns such as dynamic execution and obfuscation, used as an OMCBench baseline. *(Apiiro)* *(★ 149 · updated 2025-02-24)*
  * **Related:** [open-malicious-code-benchmark](https://github.com/False-Positive-Community/open-malicious-code-benchmark) ⭐ 17 | 🐛 0 | 🌐 Python | 📅 2026-06-09
* **[pypi\_malregistry](https://github.com/lxyeternal/pypi_malregistry) ⭐ 129 | 🐛 3 | 🌐 Python | 📅 2026-07-21** 🔬⚠️ — ASE'23 / USENIX Security'26 malicious-PyPI dataset with more than 10k malicious package versions. — **note:** no LICENSE file found and the repository contains malware samples; handle in an isolated environment. *(★ 129 · updated 2026-07-21)*
  * **Related:** [malicious-software-packages-dataset](https://github.com/DataDog/malicious-software-packages-dataset) ⭐ 372 | 🐛 9 | 🌐 Python | 📅 2026-08-14
* **[model-provenance-kit](https://github.com/cisco-ai-defense/model-provenance-kit) ⭐ 101 | 🐛 2 | 🌐 Python | 📅 2026-08-12** 🟢 — Toolkit for model-family provenance and fingerprinting across model weights, tokenizers, and architecture signals. *(Cisco AI Defense)* *(★ 101 · updated 2026-08-12)*
  * **Related:** [AIsbom](https://github.com/Lab700xOrg/aisbom) ⭐ 76 | 🐛 2 | 🌐 Python | 📅 2026-08-16
* **[AIsbom](https://github.com/Lab700xOrg/aisbom) ⭐ 76 | 🐛 2 | 🌐 Python | 📅 2026-08-16** 🟢 — AI software bill of materials tooling for AI/ML supply-chain inventory and provenance metadata. *(★ 76 · updated 2026-08-16)*
  * **Related:** [modelscan](https://github.com/protectai/modelscan) ⭐ 762 | 🐛 77 | 🌐 Python | 📅 2026-02-18 · [model-provenance-kit](https://github.com/cisco-ai-defense/model-provenance-kit) ⭐ 101 | 🐛 2 | 🌐 Python | 📅 2026-08-12
* **[pickle-fuzzer](https://github.com/cisco-ai-defense/pickle-fuzzer) ⭐ 17 | 🐛 0 | 🌐 Rust | 📅 2026-08-03** 🟢 — Structure-aware fuzzer for pickle scanners, useful for hardening tools such as modelscan, Fickling, and picklescan. *(Cisco AI Defense)* *(★ 17 · updated 2026-08-03)*
  * **Related:** [modelscan](https://github.com/protectai/modelscan) ⭐ 762 | 🐛 77 | 🌐 Python | 📅 2026-02-18 · [Fickling](https://github.com/trailofbits/fickling) ⭐ 662 | 🐛 13 | 🌐 Python | 📅 2026-08-13 · [picklescan](https://github.com/mmaitre314/picklescan) ⭐ 418 | 🐛 3 | 🌐 Python | 📅 2026-07-23
* **[open-malicious-code-benchmark](https://github.com/False-Positive-Community/open-malicious-code-benchmark) ⭐ 17 | 🐛 0 | 🌐 Python | 📅 2026-06-09** 🟢🔬 — OMCBench benchmark suite for malicious-code/package detection: labeled Python and JavaScript package archives, common runners, and published precision/recall/F1 metrics. *(False Positive Community)* — **note:** evaluates an unreleased commercial ML detector (MOLOT / PT Application Inspector) alongside open-source baselines. *(★ 17 · updated 2026-06-09)*
  * **Related:** [GuardDog](https://github.com/DataDog/guarddog) ⭐ 1,184 | 🐛 18 | 🌐 Python | 📅 2026-08-14 · [OSSGadget](https://github.com/microsoft/OSSGadget) ⭐ 370 | 🐛 66 | 🌐 C# | 📅 2026-07-31 · [malicious-code-ruleset](https://github.com/apiiro/malicious-code-ruleset) ⭐ 149 | 🐛 4 | 🌐 Python | 📅 2025-02-24 · [bandit4mal](https://github.com/lyvd/bandit4mal) ⭐ 31 | 🐛 0 | 🌐 Python | 📅 2022-09-01

***

## Pentest & Red-Team Agents

Autonomous and semi-autonomous AI agents for penetration testing, exploitation, and attack simulation.

* **[Strix](https://github.com/usestrix/strix) ⭐ 53,249 | 🐛 286 | 🌐 Python | 📅 2026-08-14** 🟢 — Autonomous "AI hackers" that dynamically run code and validate vulnerabilities with PoCs (Apache-2.0). *(★ 53,078 · updated 2026-08-14)*
* **[Shannon](https://github.com/KeygraphHQ/shannon) ⭐ 46,863 | 🐛 30 | 🌐 TypeScript | 📅 2026-08-14** 🟢🟠⚠️ — White-box autonomous AI pentester with strong XBOW-benchmark results. *Shannon Lite is AGPL-3.0; Shannon Pro is commercial.* *(★ 46,855 · updated 2026-08-12)*
* **[PentAGI](https://github.com/vxcontrol/pentagi) ⭐ 21,852 | 🐛 44 | 🌐 Go | 📅 2026-08-06** 🟢 — Fully autonomous multi-agent pentest framework with Docker sandboxing. *(VXControl)* *(★ 21,845 · updated 2026-08-06)*
* **[PentestGPT](https://github.com/GreyDGL/PentestGPT) ⭐ 14,894 | 🐛 63 | 🌐 Python | 📅 2026-07-14** 🟢🔬 — The original USENIX'24 LLM pentest agent; re-released as an autonomous pipeline with strong benchmark results. *(★ 14,886 · updated 2026-07-14)*
* **[HexStrike-AI](https://github.com/0x4m4/hexstrike-ai) ⭐ 11,087 | 🐛 103 | 🌐 Python | 📅 2026-08-03** 🟢 — MCP server exposing 150+ security tools (nmap, gobuster, nuclei, …) to AI agents (MIT). *(★ 11,066 · updated 2026-08-03)*
* **[CAI – Cybersecurity AI](https://github.com/aliasrobotics/cai) ⭐ 9,739 | 🐛 14 | 🌐 Python | 📅 2026-07-14** 🟢🟠 — Modular, bug-bounty-ready agent framework supporting 300+ LLM models. MIT for research; separate commercial license for production/on-prem. *(Alias Robotics)* *(★ 9,735 · updated 2026-07-14)*
* **[T3MP3ST](https://github.com/elder-plinius/T3MP3ST) ⭐ 5,593 | 🐛 5 | 🌐 TypeScript | 📅 2026-08-12** 🟢⚠️ — Autonomous offensive-security meta-harness that wraps local or API-backed coding agents into a multi-agent recon-to-exploit workflow with MCP/API, War Room UI, tool arsenal, and committed benchmark artifacts. — **note:** very new AGPL-3.0 project with bold benchmark claims; use only for authorized testing and verify independently before operational use. *(★ 5,587 · updated 2026-08-12)*
  * **Related:** [PentAGI](https://github.com/vxcontrol/pentagi) ⭐ 21,852 | 🐛 44 | 🌐 Go | 📅 2026-08-06 · [HexStrike-AI](https://github.com/0x4m4/hexstrike-ai) ⭐ 11,087 | 🐛 103 | 🌐 Python | 📅 2026-08-03 · [pentest-ai](https://github.com/0xSteph/pentest-ai) ⭐ 1,595 | 🐛 6 | 🌐 Python | 📅 2026-08-16
* **[PentestAgent](https://github.com/GH05TCREW/pentestagent) ⭐ 2,952 | 🐛 25 | 🌐 Python | 📅 2026-08-04** 🟢 — Black-box AI pentest framework with MCP, multi-agent spawning, and persistent sessions. *(★ 2,950 · updated 2026-08-04)*
* **[Pentest-Swarm-AI](https://github.com/Armur-Ai/Pentest-Swarm-AI) ⭐ 2,204 | 🐛 14 | 🌐 Go | 📅 2026-08-04** 🟢 — Swarm-intelligence multi-agent pentest with stigmergic blackboard coordination (Go). *(★ 2,204 · updated 2026-08-04)*
* **[pentest-ai-agents](https://github.com/0xSteph/pentest-ai-agents) ⭐ 2,131 | 🐛 2 | 🌐 Shell | 📅 2026-08-16** 🟢 — Collection of Claude Code offensive-security subagents for authorized penetration-testing research. *(★ 2,130 · updated 2026-08-08)*
  * **Related:** [pentest-ai](https://github.com/0xSteph/pentest-ai) ⭐ 1,595 | 🐛 6 | 🌐 Python | 📅 2026-08-16
* **[Deep Eye](https://github.com/zakirkun/deep-eye) ⭐ 1,969 | 🐛 12 | 🌐 Python | 📅 2026-08-14** 🟢 — AI-assisted penetration-testing scanner that orchestrates multiple LLM providers for payload generation, 45+ vulnerability checks, CVE/RAG-assisted testing, AI triage, scan diffing, browser automation, proxying, and multi-format reports. — **note:** MIT-licensed; authorized use only. Heavy runtime surface: optional browser automation/proxying, plaintext API-key config, plugins with full OS access, and pickle model files called out in SECURITY.md. *(★ 1,968 · updated 2026-08-14)*
  * **Related:** [HexStrike-AI](https://github.com/0x4m4/hexstrike-ai) ⭐ 11,087 | 🐛 103 | 🌐 Python | 📅 2026-08-03 · [pentest-ai](https://github.com/0xSteph/pentest-ai) ⭐ 1,595 | 🐛 6 | 🌐 Python | 📅 2026-08-16
* **[pentest-ai](https://github.com/0xSteph/pentest-ai) ⭐ 1,595 | 🐛 6 | 🌐 Python | 📅 2026-08-16** 🟢 — Offensive-security MCP server with 200+ wrapped tools, specialist agents, and OWASP-oriented probes for authorized testing. *(★ 1,594 · updated 2026-08-08)*
  * **Related:** [pentest-ai-agents](https://github.com/0xSteph/pentest-ai-agents) ⭐ 2,131 | 🐛 2 | 🌐 Shell | 📅 2026-08-16
* **[hackingBuddyGPT](https://github.com/ipa-lab/hackingBuddyGPT) ⭐ 1,209 | 🐛 8 | 🌐 Python | 📅 2026-08-11** 🟢🔬 — Minimal (\~50 LOC) research framework for LLM-driven Linux priv-esc and web pentesting (FSE'23). *(★ 1,209 · updated 2026-08-10)*
* **[hackGPT](https://github.com/NoDataFound/hackGPT) ⭐ 1,199 | 🐛 19 | 🌐 Jupyter Notebook | 📅 2026-08-12** 🟢⚠️ — LLM offensive-security toolkit. *(★ 1,199 · updated 2026-08-12)*
* **[Nebula](https://github.com/berylliumsec/nebula) ⭐ 1,087 | 🐛 7 | 🌐 Python | 📅 2026-08-09** 🟢🟠 — AI pentesting CLI assistant with local-LLM support (Llama-3.1, Mistral, DeepSeek). *(★ 1,087 · updated 2026-07-26)*
* **[Burp Suite MCP Server](https://github.com/PortSwigger/mcp-server) ⭐ 1,070 | 🐛 51 | 🌐 Kotlin | 📅 2026-08-14** 🟢⚠️ — Official Burp Suite extension exposing Burp to AI clients through MCP. *(PortSwigger)* — **note:** GPL-3.0 licensed. *(★ 1,070 · updated 2026-08-12)*
  * **Related:** [HexStrike-AI](https://github.com/0x4m4/hexstrike-ai) ⭐ 11,087 | 🐛 103 | 🌐 Python | 📅 2026-08-03
* **[DarkMoon](https://github.com/ASCIT31/Dark-Moon) ⭐ 841 | 🐛 1 | 🌐 Python | 📅 2026-08-06** 🟢⚠️ — Autonomous AI penetration-testing platform that orchestrates specialized web, AD, Kubernetes, CMS, and framework agents through an MCP-controlled Docker toolbox with local privacy-tokenization for sensitive target data. — **note:** GPL-3.0 licensed; heavy Docker/LLM stack, use only for authorized testing. *(★ 841 · updated 2026-08-06)*
  * **Related:** [PentAGI](https://github.com/vxcontrol/pentagi) ⭐ 21,852 | 🐛 44 | 🌐 Go | 📅 2026-08-06 · [HexStrike-AI](https://github.com/0x4m4/hexstrike-ai) ⭐ 11,087 | 🐛 103 | 🌐 Python | 📅 2026-08-03 · [pentest-ai](https://github.com/0xSteph/pentest-ai) ⭐ 1,595 | 🐛 6 | 🌐 Python | 📅 2026-08-16
* **[MCP Security Hub](https://github.com/FuzzingLabs/mcp-security-hub) ⭐ 761 | 🐛 6 | 🌐 Python | 📅 2026-04-08** 🟢 — Collection of Dockerized MCP servers that expose offensive-security tools such as Nmap, Nuclei, SQLMap, Ghidra, Hashcat, and related assessment utilities to MCP-capable assistants. *(FuzzingLabs)* — **note:** orchestration and wrapper collection rather than a security boundary; its containers invoke offensive tools and must be used only in isolated, explicitly authorized environments. *(★ 760 · updated 2026-04-08)*
  * **Related:** [pentest-ai](https://github.com/0xSteph/pentest-ai) ⭐ 1,595 | 🐛 6 | 🌐 Python | 📅 2026-08-16 · [Burp Suite MCP Server](https://github.com/PortSwigger/mcp-server) ⭐ 1,070 | 🐛 51 | 🌐 Kotlin | 📅 2026-08-14
* **[AIDA](https://github.com/Vasco0x4/AIDA) ⭐ 472 | 🐛 2 | 🌐 JavaScript | 📅 2026-07-19** 🟢⚠️ — Model-agnostic autonomous pentest agent running inside an isolated Docker environment; AGPL-3.0 licensed. *(★ 472 · updated 2026-07-19)*
* **[cyber-security-llm-agents](https://github.com/NVISOsecurity/cyber-security-llm-agents) ⭐ 388 | 🐛 2 | 🌐 Jupyter Notebook | 📅 2024-05-07** 🟢⚠️ — AutoGen-based agents for cybersecurity tasks (shown at RSAC 2024). *(NVISO)* *(★ 388 · updated 2024-05-07)*
* **[HackSynth](https://github.com/aielte-research/HackSynth) ⭐ 314 | 🐛 0 | 🌐 Python | 📅 2025-06-24** 🟢🔬⚠️ — Planner/summarizer LLM-agent framework for autonomous penetration testing and benchmark evaluation; AGPL-3.0 licensed. *(★ 313 · updated 2025-06-24)*
* **[VulnBot](https://github.com/KHenryAegis/VulnBot) ⭐ 185 | 🐛 1 | 🌐 Python | 📅 2025-04-07** 🟢🔬 — Multi-agent collaborative penetration-testing framework with RAG support. *(★ 185 · updated 2025-04-07)*
* **[BugTraceAI](https://github.com/BugTraceAI/BugTraceAI-CLI) ⭐ 174 | 🐛 4 | 🌐 Python | 📅 2026-07-30** 🟢⚠️ — Self-hosted autonomous web-application security scanner that combines reconnaissance, specialist exploit agents, Go fuzzers, and Playwright validation to produce evidence-backed findings. *(BugTraceAI)* — **note:** AGPL-3.0 licensed and beta; use only for authorized testing. Requires an LLM provider or local Ollama endpoint and a substantial Docker/Playwright/Go runtime. *(★ 174 · updated 2026-07-30)*
  * **Related:** [Project overview](https://github.com/BugTraceAI/BugTraceAI) ⭐ 119 | 🐛 1 | 📅 2026-07-27 · [Web dashboard](https://github.com/BugTraceAI/BugTraceAI-WEB) ⭐ 17 | 🐛 0 | 🌐 TypeScript | 📅 2026-07-28 · [Docker launcher](https://github.com/BugTraceAI/BugTraceAI-Launcher) ⭐ 24 | 🐛 0 | 🌐 Shell | 📅 2026-07-27
* **[ShiftGrid](https://github.com/BuFuuu/shiftgrid) ⭐ 39 | 🐛 0 | 🌐 Python | 📅 2026-08-02** 🟢 — Prompt engine that turns Claude Code into a transparent, human-in-the-loop pentester, structuring engagements through checklists, observations, and notes exposed via an agent-facing API. — **note:** early-stage local Docker application with no built-in authentication; keep its API and UI ports bound to localhost. *(★ 38 · updated 2026-08-02)*
* **[HunterX](https://github.com/nullc0d30/HunterX) ⭐ 11 | 🐛 0 | 🌐 Python | 📅 2026-08-16** 🟢 — AI-assisted offensive security engine that orchestrates reconnaissance, security-tool coordination, vulnerability detection and validation, evidence collection, and report-ready findings in one workflow. *(NullC0d3)* — **note:** early-stage and tool-orchestration-heavy; run only in an isolated, authorized assessment environment. *(★ 11 · updated 2026-08-16)*

***

## AI-Powered Recon & Narrow ML Tools

Hyper-specific AI/ML tools for a single offensive-security, recon, or detection step — the subwiz/eyeballer pattern rather than broad autonomous agents. 🅐 = self-contained trained model or learned model/pattern engine; 🅑 = LLM wrapper that calls an external API.

### Subdomain & DNS Prediction

* **[regulator](https://github.com/cramppet/regulator) ⭐ 392 | 🐛 7 | 🌐 Python | 📅 2023-02-18** 🟢⚠️ — 🅐 Learns and ranks regex-like naming patterns from known subdomains to generate likely new candidates. — **note:** no LICENSE file found; treat as source-available until clarified. *(★ 392 · updated 2023-02-18)*
  * **Related:** [subwiz](https://github.com/hadriansecurity/subwiz) ⭐ 388 | 🐛 11 | 🌐 Python | 📅 2025-12-18
* **[subwiz](https://github.com/hadriansecurity/subwiz) ⭐ 388 | 🐛 11 | 🌐 Python | 📅 2025-12-18** 🟢 — 🅐 Lightweight nanoGPT model that predicts resolvable subdomains via beam search; model weights are published on Hugging Face. *(Hadrian Security)* *(★ 388 · updated 2025-12-18)*
  * **Related:** [HadrianSecurity/subwiz model](https://huggingface.co/HadrianSecurity/subwiz)

### Recon Screenshot Triage

* **[eyeballer](https://github.com/BishopFox/eyeballer) ⭐ 1,290 | 🐛 9 | 🌐 Python | 📅 2026-03-08** 🟢⚠️ — 🅐 Convolutional neural network that classifies pentest/recon screenshots (login pages, webapps, old-looking sites, parked domains, and custom 404s) for attack-surface triage. *(Bishop Fox)* — **note:** GPL-3.0 licensed. *(★ 1,290 · updated 2024-02-19)*

### Software / Tech Fingerprinting

* **[GyoiThon](https://github.com/gyoisamurai/GyoiThon) ⭐ 826 | 🐛 20 | 🌐 Python | 📅 2023-04-21** 🟢🔬 — 🅐 Machine-learning-assisted web intelligence tool that fingerprints products, versions, CVEs, login pages, debug messages, and related web-server signals from HTTP responses. — **note:** historical research reference; Apache-2.0 licensed, but maintenance is low. *(★ 826 · updated 2021-06-29)*

### AI-Assisted Fuzzing

* **[ffufai](https://github.com/jthack/ffufai) ⭐ 801 | 🐛 11 | 🌐 Python | 📅 2025-12-04** 🟢⚠️ — 🅑 AI wrapper around the ffuf web fuzzer that suggests file extensions and paths from the target URL and headers using OpenAI or Anthropic models. *(Joseph Thacker)* — **note:** requires an LLM API key; README states MIT but no LICENSE file was found. *(★ 801 · updated 2025-12-04)*

### Password / Credential ML

* **[PassGAN](https://github.com/brannondorsey/PassGAN) ⭐ 2,009 | 🐛 29 | 🌐 Python | 📅 2023-02-24** 🔬 — 🅐 WGAN that learns password distributions from leaks to generate guesses; historical reference implementation of the PassGAN paper (MIT). — **note:** historical research reference; not an actively maintained password-auditing product. *(★ 2,009 · updated 2018-09-30)*
* **[neural\_network\_cracking](https://github.com/cupslab/neural_network_cracking) ⭐ 243 | 🐛 16 | 🌐 JavaScript | 📅 2019-12-02** 🔬 — 🅐 RNN password-guessing model from *Fast, Lean, and Accurate: Modeling Password Guessability Using Neural Networks* (USENIX Security 2016); Apache-2.0 licensed. *(CMU CUPS Lab)* — **note:** historical USENIX research implementation, not a maintained password-auditing product. *(★ 243 · updated 2018-11-30)*
  * **Related:** [PassGPT](https://huggingface.co/javirandor/passgpt-10characters) · [PassGAN](https://github.com/brannondorsey/PassGAN) ⭐ 2,009 | 🐛 29 | 🌐 Python | 📅 2023-02-24
* **[PassGPT](https://huggingface.co/javirandor/passgpt-10characters)** 🔬⚠️ — 🅐 GPT-style password model trained on leaked passwords for research on password generation and strength estimation. *(Rando et al.)* *license: CC BY-NC-4.0 · access: open 10-char model; 16-char variant gated · artifacts: PyTorch/Safetensors.* Research-only / non-commercial use; related code: [javirandor/passgpt](https://github.com/javirandor/passgpt) ⭐ 98 | 🐛 3 | 🌐 Python | 📅 2025-03-13.

### Phishing Detection (Visual / URL)

* **[PhishIntention](https://github.com/lindsey98/PhishIntention) ⭐ 263 | 🐛 29 | 🌐 Python | 📅 2026-06-05** 🔬 — 🅐 Deep-vision phishing detector that infers both brand intention and credential-taking intention from webpage appearance and dynamics (USENIX Security 2022). — **note:** CC0-1.0 licensed. *(★ 263 · updated 2026-06-04)*
* **[VisualPhishNet](https://github.com/S-Abdelnabi/VisualPhishNet) ⭐ 30 | 🐛 3 | 🌐 Jupyter Notebook | 📅 2022-02-09** 🔬⚠️ — 🅐 Triplet CNN for zero-day phishing detection by visual similarity to trusted websites (ACM CCS 2020). *(CISPA)* — **note:** no LICENSE file found; dataset access is research-request based. *(★ 30 · updated 2022-02-09)*
* **[phishing-url-detection](https://huggingface.co/pirocheto/phishing-url-detection)** 🟢 — 🅐 Packaged URL phishing classifier with ONNX and pickle artifacts. *license: MIT · access: open · artifacts: ONNX, pickle.* Model card recommends ONNX over pickle for safer inference.
* **[Phishing Email Detection DistilBERT v2.4.1](https://huggingface.co/cybersectony/phishing-email-detection-distilbert_v2.4.1)** 🟢 — DistilBERT text-classification model for email and URL phishing detection, trained on a public Hugging Face phishing-email dataset. *license: Apache-2.0 · access: open · artifacts: Safetensors.* — **note:** strong download signal, but independently verify the very high published metrics before production use.

### AI/ML-Assisted Detection Rules & Engines

* **[yaraml\_rules](https://github.com/sophos/yaraml_rules) ⭐ 215 | 🐛 4 | 🌐 Python | 📅 2023-07-06** 🟢🔬 — Research code that trains scikit-learn classifiers on malware and benign corpora, then compiles the learned model into deployable YARA rules. *(Sophos)* — **note:** historical research reference; the maintained value is the ML-to-YARA technique, not a current detection product. *(★ 215 · updated 2020-12-18)*
* **[AutoYara](https://github.com/FutureComputing4AI/AutoYara) ⭐ 79 | 🐛 3 | 🌐 Java | 📅 2025-10-08** 🟢🔬 — 🅐 Research implementation of automatic YARA rule generation via biclustering over byte n-grams for malware-family samples. — **note:** Apache-2.0 research code from the ACM AISec 2020 paper; README explicitly says it comes with no warranty or support. *(★ 79 · updated 2025-10-08)*
  * **Related:** [Automatic Yara Rule Generation Using Biclustering](https://arxiv.org/abs/2009.03779)
* **[SYARA](https://github.com/nabeelxy/syara) ⭐ 18 | 🐛 2 | 🌐 Python | 📅 2026-03-05** 🟢🔬 — 🅐 Semantic YARA-like rule engine for text and multimodal signals, adding embedding similarity, classifier-backed rules, LLM evaluators, and pHash matching to familiar YARA-style syntax. — **note:** early-stage engine; useful for LLM-era intent signals such as phishing, prompt injection, jailbreaks, hallucination, and disinformation rather than classic binary-only YARA matching. *(★ 18 · updated 2026-03-05)*
* **[RuleLLM](https://github.com/zhang-xr/RuleLLM) ⭐ 12 | 🐛 2 | 🌐 YARA | 📅 2025-04-25** 🟢🔬 — 🅑 LLM-assisted malware-rule generator that clusters malicious code samples and produces/refines/validates YARA and Semgrep rules. — **note:** MIT-licensed research prototype; requires OpenAI-compatible API access plus YARA/Semgrep validators. *(★ 12 · updated 2025-04-25)*

### Defensive Trained-Model Detectors

* **[deepsecrets](https://github.com/ntoskernel/deepsecrets) ⭐ 171 | 🐛 2 | 🌐 Python | 📅 2026-08-06** 🟢 — Semantic secrets scanner using lexing/parsing, entropy checks, and hashed-known-secret matching across 500+ languages. — **note:** useful narrow detector, but not a trained ML model. *(★ 171 · updated 2026-06-04)*
* **[DeepSQLi](https://github.com/gatewayd-io/DeepSQLi) ⭐ 7 | 🐛 7 | 🌐 Python | 📅 2026-02-21** 🟢⚠️ — 🅐 Deep-learning SQL-injection detector with dataset, trained models, and a Flask Prediction API for GatewayD IDS/IPS integration. *(GatewayD)* — **note:** AGPL-3.0 licensed; defensive detector rather than offensive generator. *(★ 7 · updated 2026-02-21)*
* **[VLAI Vulnerability Severity Classifier](https://huggingface.co/CIRCL/vulnerability-severity-classification-roberta-base)** 🟢🔬 — RoBERTa-based vulnerability-severity classifier trained on CIRCL vulnerability scores to assist triage before manual CVSS scoring. *(CIRCL)* *license: CC-BY-4.0 · access: open · artifacts: Safetensors.*

***

## AI-Powered SAST & Secure Code Review

Static analysis and secure code review enhanced with LLMs.

* **[Codex Security](https://github.com/openai/codex-security) ⭐ 9,883 | 🐛 141 | 🌐 TypeScript | 📅 2026-08-16** 🟠 — CLI and TypeScript SDK that use Codex Security to find, validate, and help fix vulnerabilities in a codebase, with scan comparison and containerized bulk-scan support. *(OpenAI)* — **note:** the CLI/SDK are open source, but scans require Codex Security access and, for best results, OpenAI Trusted Access. *(★ 9,873 · updated 2026-08-16)*
  * **Related:** [deepsec](https://github.com/vercel-labs/deepsec) ⭐ 7,675 | 🐛 62 | 🌐 TypeScript | 📅 2026-08-13 · [defending-code-reference-harness](https://github.com/anthropics/defending-code-reference-harness) ⭐ 7,188 | 🐛 23 | 🌐 Python | 📅 2026-08-06
* **[deepsec](https://github.com/vercel-labs/deepsec) ⭐ 7,675 | 🐛 62 | 🌐 TypeScript | 📅 2026-08-13** 🟢 — Agent-powered security harness for scanning large codebases with coding agents, resumable parallel runs, custom matchers, and optional revalidation. *(Vercel Labs)* *(★ 7,670 · updated 2026-08-13)*
  * **Related:** [claude-code-security-review](https://github.com/anthropics/claude-code-security-review) ⭐ 5,865 | 🐛 78 | 🌐 Python | 📅 2026-02-11 · [sast-skills](https://github.com/utkusen/sast-skills) ⭐ 1,276 | 🐛 1 | 📅 2026-04-08
* **[defending-code-reference-harness](https://github.com/anthropics/defending-code-reference-harness) ⭐ 7,188 | 🐛 23 | 🌐 Python | 📅 2026-08-06** 🟢 — Reference Claude Code skills and autonomous vulnerability-discovery pipeline for threat modeling, static scanning, triage, execution-verified C/C++ memory-bug discovery, reporting, and patch generation. *(Anthropic)* — **note:** official reference implementation, not maintained as a product; the autonomous pipeline executes target code and should be run only inside the documented gVisor sandbox. *(★ 7,131 · updated 2026-08-06)*
  * **Related:** [deepsec](https://github.com/vercel-labs/deepsec) ⭐ 7,675 | 🐛 62 | 🌐 TypeScript | 📅 2026-08-13 · [claude-code-security-review](https://github.com/anthropics/claude-code-security-review) ⭐ 5,865 | 🐛 78 | 🌐 Python | 📅 2026-02-11
* **[Trail of Bits Skills](https://github.com/trailofbits/skills) ⭐ 6,613 | 🐛 33 | 🌐 Python | 📅 2026-08-14** 🟢⚠️ — Claude Code- and Codex-compatible security workflow skills for code review, differential review, false-positive analysis, supply-chain checks, GitHub Actions auditing, Semgrep rule generation, and vulnerability research. *(Trail of Bits)* — **note:** reusable agent workflow instructions rather than a standalone deterministic scanner; share-alike terms apply to adapted material. *(★ 6,612 · updated 2026-08-14)*
  * **Related:** [sast-skills](https://github.com/utkusen/sast-skills) ⭐ 1,276 | 🐛 1 | 📅 2026-04-08 · [Claude-BugHunter](https://github.com/elementalsouls/Claude-BugHunter) ⭐ 3,621 | 🐛 0 | 🌐 Python | 📅 2026-08-16
* **[claude-code-security-review](https://github.com/anthropics/claude-code-security-review) ⭐ 5,865 | 🐛 78 | 🌐 Python | 📅 2026-02-11** 🟠 — Official Claude-based semantic SAST GitHub Action that reviews PR diffs. *(Anthropic)* *(★ 5,863 · updated 2026-02-11)*
* **[Vulnhuntr](https://github.com/protectai/vulnhuntr) ⭐ 2,739 | 🐛 17 | 🌐 Python | 📅 2025-02-06** 🟢 — Zero-shot vulnerability discovery in Python repos via LLM call-chain analysis; credited with a 0-day RCE in Ragflow. *(Protect AI)* *(★ 2,738 · updated 2025-02-06)*
  * **Related:** [IRIS](https://github.com/iris-sast/iris) ⭐ 413 | 🐛 0 | 🌐 Dockerfile | 📅 2026-07-02
* **[Visa Vulnerability Agentic Harness](https://github.com/visa/visa-vulnerability-agentic-harness) ⭐ 2,553 | 🐛 0 | 🌐 Python | 📅 2026-08-04** 🟢 — Agentic SAST pipeline for autonomous vulnerability discovery, exploitability verification, SARIF/Markdown reporting, remediation, and validation using frontier AI models. *(Visa)* — **note:** Apache-2.0; authorized use only. The default `scan` profile can continue into remediation and edit target source files; use `--stop-after s9` for detection-only runs. *(★ 2,553 · updated 2026-08-04)*
  * **Related:** [deepsec](https://github.com/vercel-labs/deepsec) ⭐ 7,675 | 🐛 62 | 🌐 TypeScript | 📅 2026-08-13 · [defending-code-reference-harness](https://github.com/anthropics/defending-code-reference-harness) ⭐ 7,188 | 🐛 23 | 🌐 Python | 📅 2026-08-06
* **[open·kritt](https://github.com/Kritt-ai/open-kritt) ⭐ 1,755 | 🐛 45 | 🌐 JavaScript | 📅 2026-08-16** 🟢⚠️ — Self-hosted platform that orchestrates Codex or Claude Code across focused vulnerability-research workflows, then validates, de-duplicates, ranks, and reports resulting findings. *(Kritt AI)* — **note:** jobs run as root in disposable Docker containers with writable target copies and direct internet access; the stack has no application auth by default and sends scanned code to the configured model provider. Deploy only on a dedicated, access-controlled host and scan authorized targets. *(★ 1,723 · updated 2026-08-12)*
  * **Related:** [deepsec](https://github.com/vercel-labs/deepsec) ⭐ 7,675 | 🐛 62 | 🌐 TypeScript | 📅 2026-08-13 · [Visa Vulnerability Agentic Harness](https://github.com/visa/visa-vulnerability-agentic-harness) ⭐ 2,553 | 🐛 0 | 🌐 Python | 📅 2026-08-04
* **[Buttercup](https://github.com/trailofbits/buttercup) ⭐ 1,676 | 🐛 62 | 🌐 Python | 📅 2026-08-10** 🟢🔬⚠️ — Multi-component cyber reasoning system for finding, validating, and patching software vulnerabilities with coordinated agent workflows. *(Trail of Bits)* — **note:** AGPL-3.0 research/competition system rather than a lightweight scanner; deployment uses multiple services, Docker, and configured model providers. *(★ 1,676 · updated 2026-08-10)*
  * **Related:** [OpenHack](https://github.com/hadriansecurity/OpenHack) ⭐ 730 | 🐛 1 | 🌐 Python | 📅 2026-06-01 · [Visa Vulnerability Agentic Harness](https://github.com/visa/visa-vulnerability-agentic-harness) ⭐ 2,553 | 🐛 0 | 🌐 Python | 📅 2026-08-04
* **[sast-skills](https://github.com/utkusen/sast-skills) ⭐ 1,276 | 🐛 1 | 📅 2026-04-08** 🟢 — Agent skills that turn AI coding assistants into a multi-agent SAST scanner. *(★ 1,276 · updated 2026-04-08)*
  * **Related:** [Fraim](https://github.com/fraim-dev/fraim) ⭐ 160 | 🐛 22 | 🌐 Python | 📅 2026-02-09 · [llm-sast-scanner](https://github.com/SunWeb3Sec/llm-sast-scanner) ⭐ 274 | 🐛 0 | 📅 2026-04-07
* **[OpenHack](https://github.com/hadriansecurity/OpenHack) ⭐ 730 | 🐛 1 | 🌐 Python | 📅 2026-06-01** 🟢 — File-based source-guided white-box security-review workspace that orchestrates agents through reconnaissance, vulnerability hunting, validation, evidence capture, and reporting. *(Hadrian Security)* — **note:** requires an external coding harness/model and can consume substantial model tokens; OpenHack provides workflow state and review artifacts, not sandboxing or an execution-security boundary. Use only on authorized targets. *(★ 730 · updated 2026-06-01)*
  * **Related:** [deepsec](https://github.com/vercel-labs/deepsec) ⭐ 7,675 | 🐛 62 | 🌐 TypeScript | 📅 2026-08-13 · [rust-in-peace](https://github.com/scadastrangelove/rust-in-peace) ⭐ 14 | 🐛 0 | 🌐 Python | 📅 2026-08-11
* **[IRIS](https://github.com/iris-sast/iris) ⭐ 413 | 🐛 0 | 🌐 Dockerfile | 📅 2026-07-02** 🟢🔬 — Neurosymbolic SAST combining LLMs with CodeQL for Java vulnerability detection (MIT). *(★ 413 · updated 2026-07-02)*
* **[llm-sast-scanner](https://github.com/SunWeb3Sec/llm-sast-scanner) ⭐ 274 | 🐛 0 | 📅 2026-04-07** 🟢 — SAST skill for AI coding agents with structured source-to-sink analysis across 34 vulnerability classes. *License: MIT stated in README.* *(★ 274 · updated 2026-04-07)*
  * **Related:** [sast-skills](https://github.com/utkusen/sast-skills) ⭐ 1,276 | 🐛 1 | 📅 2026-04-08
* **[llm-security-scanner](https://github.com/iknowjason/llm-security-scanner) ⭐ 22 | 🐛 0 | 🌐 Python | 📅 2025-04-02** 🟢⚠️ — LLM-powered code scanner that opens GitHub issues for findings. *(★ 22 · updated 2025-04-02)*
* **[sast-ai-workflow](https://github.com/RHEcosystemAppEng/sast-ai-workflow) ⭐ 20 | 🐛 0 | 🌐 Python | 📅 2026-06-29** 🟢 — LangGraph workflow for reviewing static-analysis findings, reducing false positives, and producing vulnerability review output. *(Red Hat Ecosystem AppEng)* *(★ 20 · updated 2026-06-29)*
  * **Related:** [seclab-taskflow-agent](https://github.com/GitHubSecurityLab/seclab-taskflow-agent) ⭐ 221 | 🐛 26 | 🌐 Python | 📅 2026-08-13 · [Fraim](https://github.com/fraim-dev/fraim) ⭐ 160 | 🐛 22 | 🌐 Python | 📅 2026-02-09
* **[rust-in-peace](https://github.com/scadastrangelove/rust-in-peace) ⭐ 14 | 🐛 0 | 🌐 Python | 📅 2026-08-11** 🟢 — Rust-security fork of Anthropic's defending-code reference harness, adding a Rust profile for agentic review of unsafe/FFI memory bugs, panic-DoS, deserialization-trust issues, and Miri/ASan/panic/hang-verified findings. *(Sergey Gordeychik)* — **note:** very new Apache-2.0 fork; autonomous runs execute target code and should use the documented sandbox. *(★ 14 · updated 2026-08-11)*
  * **Related:** [defending-code-reference-harness](https://github.com/anthropics/defending-code-reference-harness) ⭐ 7,188 | 🐛 23 | 🌐 Python | 📅 2026-08-06 · [deepsec](https://github.com/vercel-labs/deepsec) ⭐ 7,675 | 🐛 62 | 🌐 TypeScript | 📅 2026-08-13

***

## AI-Powered Threat Modeling

Architecture-level threat model generation and design-phase risk analysis driven by LLM reasoning.

* **[STRIDE GPT](https://github.com/mrwadams/stride-gpt) ⭐ 1,100 | 🐛 3 | 🌐 Python | 📅 2026-08-12** 🟢 — LLM-powered threat modeling tool that generates STRIDE threat models, attack trees, data flow diagrams, DREAD risk scores, mitigations, and Gherkin test cases from application descriptions, architecture diagrams, or codebases (agentic analysis mode), with OWASP LLM Top 10 and Agentic (ASI) coverage, MITRE ATT\&CK/ATLAS mapping, Markdown/JSON/SARIF/HTML output, and broad LLM provider support via LiteLLM including local hosting. *(Matthew Adams)* *(★ 1,100 · updated 2026-08-12)*
  * **Related:** [tachi](https://github.com/davidmatousek/tachi) ⭐ 89 | 🐛 23 | 🌐 Python | 📅 2026-08-13
* **[tachi](https://github.com/davidmatousek/tachi) ⭐ 89 | 🐛 23 | 🌐 Python | 📅 2026-08-13** 🟢 — Threat modeling and AI-reasoning vulnerability detection harness for Claude Code that dispatches 14 specialized threat agents (6 STRIDE, 5 LLM, 3 agentic) against an architecture description in Mermaid, C4, PlantUML, ASCII, or free text, producing SARIF 2.1.0 for code scanning, MAESTRO seven-layer classification, attack trees, CVSS-aligned composite risk scores, compensating-controls analysis of the target codebase, and a PDF report. *(David Matousek)* — **note:** runs inside Claude Code; architecture descriptions are processed by the configured Claude model. *(★ 89 · updated 2026-08-13)*
  * **Related:** [STRIDE GPT](https://github.com/mrwadams/stride-gpt) ⭐ 1,100 | 🐛 3 | 🌐 Python | 📅 2026-08-12 · [defending-code-reference-harness](https://github.com/anthropics/defending-code-reference-harness) ⭐ 7,188 | 🐛 23 | 🌐 Python | 📅 2026-08-06

***

## LLM-Driven Fuzzing

Two families: (a) LLMs generating harnesses/targets for traditional fuzzing, and (b) fuzzing the LLM itself.

### Harness / target generation

* **[oss-fuzz-gen](https://github.com/google/oss-fuzz-gen) ⭐ 1,430 | 🐛 165 | 🌐 Python | 📅 2026-03-17** 🟢 — LLM-driven fuzz-harness generation for OSS-Fuzz; reported 26 real vulnerabilities (incl. CVE-2024-9143 in OpenSSL). *(Google)* *(★ 1,430 · updated 2026-03-02)*
* **[ChatAFL](https://github.com/ChatAFLndss/ChatAFL) ⭐ 392 | 🐛 6 | 🌐 C | 📅 2025-06-30** 🟢🔬 — LLM-guided protocol fuzzing extending AFLNet (NDSS'24). *(★ 392 · updated 2025-06-20)*
* **[PromptFuzz](https://github.com/PromptFuzz/PromptFuzz) ⭐ 342 | 🐛 2 | 🌐 Rust | 📅 2026-05-15** 🟢🔬⚠️ — LLM-mutated prompts to generate fuzz drivers for C/C++ libraries (Rust). *(★ 342 · updated 2026-05-15)*
* **[Fuzz4All](https://github.com/fuzz4all/fuzz4all) ⭐ 336 | 🐛 4 | 🌐 Python | 📅 2025-08-11** 🟢🔬 — "Universal" LLM-based fuzzer across compilers/languages (ICSE 2024). *(★ 336 · updated 2025-08-11)*
* **[TitanFuzz](https://github.com/ise-uiuc/TitanFuzz) ⭐ 94 | 🐛 5 | 🌐 Python | 📅 2023-09-10** 🟢🔬⚠️ — First LLM-based fuzzer for PyTorch/TensorFlow (ISSTA'23). *(★ 94 · updated 2023-09-10)*

### Fuzzing the LLM

* **[FuzzyAI](https://github.com/cyberark/FuzzyAI) ⭐ 1,561 | 🐛 6 | 🌐 Jupyter Notebook | 📅 2026-02-06** 🟠 — Automated LLM fuzzer for jailbreaks/prompt injection. *(CyberArk)* *(★ 1,561 · updated 2026-02-06)*
* **[promptmap](https://github.com/utkusen/promptmap) ⭐ 1,250 | 🐛 4 | 🌐 Python | 📅 2025-12-01** 🟢⚠️ — Prompt-injection scanner for custom LLM applications in white-box and black-box modes; GPL-3.0 licensed. *(★ 1,250 · updated 2025-12-01)*
  * **Related:** [spikee](https://github.com/ReversecLabs/spikee) ⭐ 231 | 🐛 5 | 🌐 Python | 📅 2026-07-13
* **[ps-fuzz](https://github.com/prompt-security/ps-fuzz) ⭐ 703 | 🐛 20 | 🌐 Python | 📅 2026-02-16** 🟠 — System-prompt hardening fuzzer; 16 attacks × 16 providers. *(Prompt Security)* *(★ 703 · updated 2026-02-16)*
* **[LLMFuzzer](https://github.com/mnns/LLMFuzzer) ⭐ 377 | 🐛 3 | 🌐 Python | 📅 2024-02-12** 🟢🔬 — First open-source fuzzing framework for LLM API integrations. — **note:** historical research reference; maintenance appears low compared with current LLM security scanners. *(★ 377 · updated 2024-02-12)*
* **[spikee](https://github.com/ReversecLabs/spikee) ⭐ 231 | 🐛 5 | 🌐 Python | 📅 2026-07-13** 🟢 — Prompt-injection evaluation and exploitation kit with dataset generation, Burp integration, and pluggable judges. *(ReversecLabs / WithSecure)* *(★ 231 · updated 2026-07-13)*
  * **Related:** [promptmap](https://github.com/utkusen/promptmap) ⭐ 1,250 | 🐛 4 | 🌐 Python | 📅 2025-12-01
* **[ai-prompt-fuzzer](https://github.com/PortSwigger/ai-prompt-fuzzer) ⭐ 36 | 🐛 0 | 🌐 Java | 📅 2025-09-04** 🟢 — Burp Suite extension fuzzing GenAI/LLM prompts. *(PortSwigger)* *(★ 36 · updated 2025-09-04)*

***

## Threat Intelligence

AI/LLM tooling for CTI gathering, IOC/TTP extraction, and analysis.

* **[ThreatIngestor](https://github.com/InQuest/ThreatIngestor) ⭐ 922 | 🐛 15 | 🌐 Python | 📅 2026-05-26** 🟢 — Extracts/aggregates IOCs from feeds; integrates with MISP/ThreatKB (pairs well with LLM post-processing). *(★ 922 · updated 2026-05-26)*
* **[IATelligence](https://github.com/fr0gger/IATelligence) ⭐ 384 | 🐛 0 | 🌐 Python | 📅 2022-12-09** 🟢 — Explains imported Windows APIs in PE files via GPT and maps to MITRE ATT\&CK. *(★ 384 · updated 2022-12-09)*
  * **Related:** [MCP\_Security](https://github.com/fr0gger/MCP_Security) ⭐ 51 | 🐛 2 | 🌐 Python | 📅 2025-01-22
* **[TI-Mindmap-GPT](https://github.com/format81/TI-Mindmap-GPT) ⭐ 111 | 🐛 1 | 🌐 Python | 📅 2026-02-16** 🟢 — Streamlit app: AI summaries, mindmaps, IOC/TTP extraction, and ATT\&CK Navigator layers. *(★ 111 · updated 2026-02-16)*
* **[CTIBench](https://github.com/maveryn/cti-bench) ⭐ 92 | 🐛 1 | 🌐 Jupyter Notebook | 📅 2026-05-07** 🔬⚠️ — NeurIPS 2024 Spotlight benchmark with 4,610 examples across CTI knowledge, CWE root-cause mapping, CVSS prediction, ATT\&CK technique extraction, and threat-actor attribution. — **note:** non-commercial research benchmark; the repository publishes data, evaluation notebooks, model outputs, and raw logs rather than a production CTI service. *(★ 92 · updated 2026-05-07)*
  * **Related:** [CTINexus](https://github.com/peng-gao-lab/ctinexus) ⭐ 85 | 🐛 1 | 🌐 Python | 📅 2026-02-25 · [CTI-BERT](https://huggingface.co/ibm-research/CTI-BERT)
* **[CTINexus](https://github.com/peng-gao-lab/ctinexus) ⭐ 85 | 🐛 1 | 🌐 Python | 📅 2026-02-25** 🟢🔬 — LLM-assisted framework for data-efficient extraction of cyber-threat intelligence and construction of structured cybersecurity knowledge graphs from unstructured reports. — **note:** ships tests, releases, Docker configuration, and a Python package; extraction workflows require a configured supported LLM provider. *(★ 85 · updated 2026-02-25)*
  * **Related:** [threat-intelligence-cti-analysis](https://github.com/AnandBinuArjun/threat-intelligence-cti-analysis) ⭐ 4 | 🐛 0 | 🌐 Python | 📅 2025-11-03 · [CTIBench](https://github.com/maveryn/cti-bench) ⭐ 92 | 🐛 1 | 🌐 Jupyter Notebook | 📅 2026-05-07
* **[MCP\_Security](https://github.com/fr0gger/MCP_Security) ⭐ 51 | 🐛 2 | 🌐 Python | 📅 2025-01-22** 🟢⚠️ — MCP server (ORKL) for querying the ORKL threat-intel API. *(★ 51 · updated 2025-01-22)*
  * **Related:** [IATelligence](https://github.com/fr0gger/IATelligence) ⭐ 384 | 🐛 0 | 🌐 Python | 📅 2022-12-09
* **[aiocrioc](https://github.com/referefref/aiocrioc) ⭐ 38 | 🐛 0 | 🌐 Python | 📅 2024-12-04** 🟢 — LLM + OCR IOC extraction (pulls IOCs from images/PDFs). *(★ 38 · updated 2024-12-04)*
* **[trs](https://github.com/deadbits/trs) ⭐ 10 | 🐛 2 | 🌐 Python | 📅 2023-11-15** 🟢 — LLM + ChromaDB tool to summarize threat reports and extract MITRE TTPs and IOCs. *(★ 10 · updated 2023-11-15)*
* **[threat-intelligence-cti-analysis](https://github.com/AnandBinuArjun/threat-intelligence-cti-analysis) ⭐ 4 | 🐛 0 | 🌐 Python | 📅 2025-11-03** 🟢 — NLP/LLM pipeline for IOC extraction, MITRE ATT\&CK mapping, and knowledge-graph generation from unstructured CTI. *(★ 4 · updated 2025-11-03)*
  * **Related:** [soctalk](https://github.com/soctalk/soctalk) ⭐ 78 | 🐛 34 | 🌐 Python | 📅 2026-08-12
* **[CTI-BERT](https://huggingface.co/ibm-research/CTI-BERT)** 🟢🔬 — BERT model pretrained from scratch on a large cybersecurity text corpus for downstream CTI extraction, classification, and question-answering tasks. *(IBM Research)* *license: Apache-2.0 · access: open · artifacts: PyTorch.*

***

## Log Analysis / SIEM / SOC Triage

AI agents for SOC alert triage, investigation, and incident response.

* **[AttackGen](https://github.com/mrwadams/attackgen) ⭐ 1,234 | 🐛 11 | 🌐 Python | 📅 2026-08-13** 🟢 — LLM-driven incident-response scenario generator using MITRE ATT\&CK + ATLAS. *(★ 1,234 · updated 2026-08-13)*
* **[agentic-soc-platform](https://github.com/FunnyWolf/agentic-soc-platform) ⭐ 1,144 | 🐛 10 | 🌐 Python | 📅 2026-08-05** 🟢 — Agentic SOC platform (LangGraph/Dify) with local-LLM support. *(★ 1,144 · updated 2026-08-05)*
* **[Google Security Operations and Threat Intelligence MCP Server](https://github.com/google/mcp-security) ⭐ 517 | 🐛 87 | 🌐 Python | 📅 2026-08-13** 🟢 — MCP servers and packages that let MCP clients access Google Security Operations, SOAR, Google Threat Intelligence, and Security Command Center for investigation, hunting, and security automation workflows. *(Google Cloud)* — **note:** integration layer rather than an MCP-defense tool; requires Google credentials and access to the connected security products/services. *(★ 517 · updated 2026-04-29)*
  * **Related:** [MCP\_Security](https://github.com/fr0gger/MCP_Security) ⭐ 51 | 🐛 2 | 🌐 Python | 📅 2025-01-22 · [Vigil SOC](https://github.com/Vigil-SOC/vigil) ⭐ 246 | 🐛 89 | 🌐 Python | 📅 2026-08-15
* **[Vigil SOC](https://github.com/Vigil-SOC/vigil) ⭐ 246 | 🐛 89 | 🌐 Python | 📅 2026-08-15** 🟢 — Open-source AI SOC with readable Python agents, Markdown playbooks, and MCP integrations for triage, investigation, hunting, response, reporting, and forensics. *(Vigil SOC)* *(★ 246 · updated 2026-08-15)*
  * **Related:** [soctalk](https://github.com/soctalk/soctalk) ⭐ 78 | 🐛 34 | 🌐 Python | 📅 2026-08-12
* **[ExCyTIn-Bench (SecRL)](https://github.com/microsoft/SecRL) ⭐ 142 | 🐛 11 | 🌐 Jupyter Notebook | 📅 2026-08-05** 🟢🔬 — ICML 2026 benchmark for evaluating LLM agents on cyber-threat investigation and threat hunting through security question-answering over eight anonymized incident databases. *(Microsoft)* — **note:** evaluation requires model-provider credentials, Dockerized MySQL incident databases, and roughly 10 GB for the standard eight-container setup (up to 33 GB for the combined database). *(★ 142 · updated 2026-08-03)*
  * **Related:** [CTIBench](https://github.com/maveryn/cti-bench) ⭐ 92 | 🐛 1 | 🌐 Jupyter Notebook | 📅 2026-05-07 · [Google Security Operations MCP](https://github.com/google/mcp-security) ⭐ 517 | 🐛 87 | 🌐 Python | 📅 2026-08-13
* **[SigmAIQ](https://github.com/AttackIQ/SigmAIQ) ⭐ 97 | 🐛 3 | 🌐 Python | 📅 2025-11-03** 🟢⚠️ — pySigma wrapper and LangChain toolkit for automatic Sigma rule creation and translation; LGPL-2.1 licensed. *(AttackIQ)* *(★ 97 · updated 2025-11-03)*
  * **Related:** [SigmaOptimizer](https://github.com/YusukeJustinNakajima/SigmaOptimizer) ⭐ 11 | 🐛 0 | 🌐 PowerShell | 📅 2025-08-01
* **[soctalk](https://github.com/soctalk/soctalk) ⭐ 78 | 🐛 34 | 🌐 Python | 📅 2026-08-12** 🟢 — LangGraph SOC automation agent with MCP integrations for Wazuh, Cortex, TheHive, and MISP plus mock-agent test lab. *(★ 78 · updated 2026-08-12)*
  * **Related:** [SigmaOptimizer](https://github.com/YusukeJustinNakajima/SigmaOptimizer) ⭐ 11 | 🐛 0 | 🌐 PowerShell | 📅 2025-08-01
* **[AI-SOC-Agent](https://github.com/M507/ai-soc-agent) ⭐ 47 | 🐛 0 | 🌐 Python | 📅 2025-12-28** 🟢 — Black Hat 2025 MCP server exposing security-investigation tools (ELK, IRIS). *(★ 47 · updated 2025-12-28)*
* **[RulePilot](https://github.com/LLM4SOC-Topic/RulePilot) ⭐ 15 | 🐛 0 | 🌐 Python | 📅 2025-10-20** 🟢🔬 — LLM-powered security-rule generation agent for Splunk, Microsoft Sentinel, and Elastic, with field detection from log samples, multi-stage refinement, and cross-platform rule conversion. — **note:** MIT-licensed ICSE 2026 research prototype; requires an OpenAI API key. *(★ 15 · updated 2025-10-20)*
  * **Related:** [SigmAIQ](https://github.com/AttackIQ/SigmAIQ) ⭐ 97 | 🐛 3 | 🌐 Python | 📅 2025-11-03 · [SigmaOptimizer](https://github.com/YusukeJustinNakajima/SigmaOptimizer) ⭐ 11 | 🐛 0 | 🌐 PowerShell | 📅 2025-08-01
* **[SOCGPT](https://github.com/Ninadjos/SOCGPT-AI-Powered-SOC-Assistant) ⭐ 7 | 🐛 1 | 🌐 Python | 📅 2025-06-11** 🟢 — LLM log summarization, severity triage, MITRE mapping, and Q\&A. *(★ 7 · updated 2025-06-11)*

***

## Reverse Engineering

LLM-assisted binary analysis and traffic inspection.

* **[ida-pro-mcp](https://github.com/mrexodia/ida-pro-mcp) ⭐ 11,376 | 🐛 47 | 🌐 Python | 📅 2026-08-09** 🟢 — MCP bridge for IDA Pro exposing decompile, disassemble, xref, rename, and debugging workflows to LLM clients. *(★ 11,375 · updated 2026-08-09)*
* **[GhidraMCP](https://github.com/LaurieWired/GhidraMCP) ⭐ 9,802 | 🐛 82 | 🌐 Java | 📅 2025-06-23** 🟢 — MCP server exposing Ghidra reverse-engineering ops to any MCP-capable LLM. *(★ 9,800 · updated 2025-06-23)*
  * **Related:** [GhidrOllama](https://github.com/lr-m/GhidrOllama) ⭐ 154 | 🐛 3 | 🌐 Python | 📅 2024-11-29 · [OGhidra](https://github.com/llnl/OGhidra) ⭐ 409 | 🐛 19 | 🌐 Python | 📅 2026-08-14
* **[LLM4Decompile](https://github.com/albertan017/LLM4Decompile) ⭐ 6,963 | 🐛 46 | 🌐 Python | 📅 2026-02-12** 🟢🔬⚠️ — Research project for binary-to-C decompilation with LLMs; code is MIT, but model weights use a more restrictive license. *(★ 6,963 · updated 2026-02-12)*
* **[Gepetto](https://github.com/JusticeRage/Gepetto) ⭐ 3,457 | 🐛 14 | 🌐 Python | 📅 2026-08-15** 🟢 — IDA Pro plugin: GPT adds comments and meaningful variable names. *(★ 3,457 · updated 2026-08-15)*
* **[ghidra-mcp](https://github.com/bethington/ghidra-mcp) ⭐ 3,323 | 🐛 19 | 🌐 Java | 📅 2026-08-14** 🟢 — Ghidra MCP server with large tool coverage, GUI plugin, headless server, and lazy tool loading. *(★ 3,322 · updated 2026-08-12)*
  * **Related:** [GhidrAssistMCP](https://github.com/symgraph/GhidrAssistMCP) ⭐ 720 | 🐛 7 | 🌐 Java | 📅 2026-08-03
* **[burpgpt](https://github.com/aress31/burpgpt) ⭐ 2,347 | 🐛 15 | 🌐 Java | 📅 2024-06-09** 🟢 — Burp Suite extension integrating GPT for passive scanning. *(★ 2,347 · updated 2024-06-09)*
  * **Related:** [Burp-extension-for-GPT](https://github.com/tenable/Burp-extension-for-GPT) ⭐ 116 | 🐛 0 | 🌐 Python | 📅 2023-05-01
* **[ReVa](https://github.com/cyberkaida/reverse-engineering-assistant) ⭐ 804 | 🐛 21 | 🌐 Java | 📅 2026-08-11** 🟢 — Ghidra-focused reverse-engineering assistant with MCP support, Claude Skills integration, and long-form analysis workflows. *(★ 803 · updated 2026-07-28)*
  * **Related:** [GhidraMCP](https://github.com/LaurieWired/GhidraMCP) ⭐ 9,802 | 🐛 82 | 🌐 Java | 📅 2025-06-23 · [GhidrAssistMCP](https://github.com/symgraph/GhidrAssistMCP) ⭐ 720 | 🐛 7 | 🌐 Java | 📅 2026-08-03
* **[GhidrAssistMCP](https://github.com/symgraph/GhidrAssistMCP) ⭐ 720 | 🐛 7 | 🌐 Java | 📅 2026-08-03** 🟢 — Native Ghidra MCP extension with broad tool coverage, headless support, and security-sensitive tool gating. *(★ 719 · updated 2026-08-02)*
  * **Related:** [ReVa](https://github.com/cyberkaida/reverse-engineering-assistant) ⭐ 804 | 🐛 21 | 🌐 Java | 📅 2026-08-11 · [ghidra-mcp](https://github.com/bethington/ghidra-mcp) ⭐ 3,323 | 🐛 19 | 🌐 Java | 📅 2026-08-14
* **[GhidraGPT](https://github.com/weirdmachine64/GhidraGPT) ⭐ 657 | 🐛 0 | 🌐 Java | 📅 2026-07-22** 🟢 — Ghidra plugin that integrates LLMs for automated code refactoring and analysis. *(★ 656 · updated 2026-07-22)*
  * **Related:** [GhidraMCP](https://github.com/LaurieWired/GhidraMCP) ⭐ 9,802 | 🐛 82 | 🌐 Java | 📅 2025-06-23 · [ReVa](https://github.com/cyberkaida/reverse-engineering-assistant) ⭐ 804 | 🐛 21 | 🌐 Java | 📅 2026-08-11
* **[OGhidra](https://github.com/llnl/OGhidra) ⭐ 409 | 🐛 19 | 🌐 Python | 📅 2026-08-14** 🟢 — Natural-language Ghidra analysis via Ollama. *(Lawrence Livermore National Lab)* *(★ 409 · updated 2026-08-14)*
  * **Related:** [GhidrOllama](https://github.com/lr-m/GhidrOllama) ⭐ 154 | 🐛 3 | 🌐 Python | 📅 2024-11-29 · [GhidraMCP](https://github.com/LaurieWired/GhidraMCP) ⭐ 9,802 | 🐛 82 | 🌐 Java | 📅 2025-06-23
* **[gpt-wpre](https://github.com/moyix/gpt-wpre) ⭐ 406 | 🐛 0 | 🌐 Python | 📅 2022-12-31** 🔬 — Whole-program reverse engineering with GPT-3. *(★ 406 · updated 2022-12-31)*
* **[REA](https://github.com/morluto/rea) ⭐ 334 | 🐛 51 | 🌐 TypeScript | 📅 2026-08-14** 🟢 — Local CLI and MCP toolkit for agent-assisted reverse engineering of native binaries, managed PE/CLI files, JavaScript/Electron apps, and browser runtimes, using Hopper or an operator-provided Ghidra installation. — **note:** deep native analysis uses separately licensed Hopper or operator-installed Ghidra. Setup can modify agent MCP registrations after interactive approval, and dynamic providers run with the current user's permissions; analyze only authorized artifacts. *(★ 332 · updated 2026-08-14)*
  * **Related:** [GhidraMCP](https://github.com/LaurieWired/GhidraMCP) ⭐ 9,802 | 🐛 82 | 🌐 Java | 📅 2025-06-23 · [ReVa](https://github.com/cyberkaida/reverse-engineering-assistant) ⭐ 804 | 🐛 21 | 🌐 Java | 📅 2026-08-11
* **[ghidra\_tools (G-3PO)](https://github.com/tenable/ghidra_tools) ⭐ 312 | 🐛 1 | 🌐 Python | 📅 2023-05-10** 🟢 — Ghidra plugin for AI-assisted decompiled-code analysis. *(Tenable)* *(★ 312 · updated 2023-05-10)*
* **[GhidrOllama](https://github.com/lr-m/GhidrOllama) ⭐ 154 | 🐛 3 | 🌐 Python | 📅 2024-11-29** 🟢⚠️ — Ghidra script using the Ollama API for function analysis/renaming. *(★ 154 · updated 2024-11-29)*
  * **Related:** [OGhidra](https://github.com/llnl/OGhidra) ⭐ 409 | 🐛 19 | 🌐 Python | 📅 2026-08-14 · [GhidraMCP](https://github.com/LaurieWired/GhidraMCP) ⭐ 9,802 | 🐛 82 | 🌐 Java | 📅 2025-06-23
* **[Burp-extension-for-GPT](https://github.com/tenable/Burp-extension-for-GPT) ⭐ 116 | 🐛 0 | 🌐 Python | 📅 2023-05-01** 🟢 — Burp extension to analyze HTTP traffic with GPT. *(Tenable)* *(★ 116 · updated 2023-05-01)*
  * **Related:** [burpgpt](https://github.com/aress31/burpgpt) ⭐ 2,347 | 🐛 15 | 🌐 Java | 📅 2024-06-09
* **[x64dbg\_mcp](https://github.com/bromoket/x64dbg_mcp) ⭐ 104 | 🐛 1 | 🌐 C++ | 📅 2026-06-08** 🟢 — MCP server exposing x64dbg debugging and reverse-engineering operations to AI clients. *(★ 104 · updated 2026-06-08)*
* **[binaryninja-mcp](https://github.com/MCPPhalanx/binaryninja-mcp) ⭐ 47 | 🐛 10 | 🌐 Python | 📅 2025-05-13** 🟢 — MCP server for Binary Ninja-assisted reverse engineering. *(★ 47 · updated 2025-05-13)*

***

## LLM Red-Teaming & Guardrails

Tools for attacking and defending LLM applications themselves.

### Scanners, Evals & Guardrails

* **[promptfoo](https://github.com/promptfoo/promptfoo) ⭐ 24,276 | 🐛 505 | 🌐 TypeScript | 📅 2026-08-16** 🟢 — LLM eval + red-teaming/pentesting CLI with 50+ attack plugins (MIT). *Note: OpenAI announced an acquisition agreement in March 2026; remains MIT-licensed — track governance.* *(★ 24,270 · updated 2026-08-15)*
* **[garak](https://github.com/NVIDIA/garak) ⭐ 8,827 | 🐛 389 | 🌐 Python | 📅 2026-08-14** 🟢 — The LLM vulnerability scanner — probes for prompt injection, jailbreaks, data leakage, and more. *(NVIDIA)* *(★ 8,824 · updated 2026-08-14)*
  * **Related:** [PyRIT](https://github.com/microsoft/PyRIT) ⭐ 4,312 | 🐛 81 | 🌐 Python | 📅 2026-08-15 · [promptfoo](https://github.com/promptfoo/promptfoo) ⭐ 24,276 | 🐛 505 | 🌐 TypeScript | 📅 2026-08-16
* **[Guardrails AI](https://github.com/guardrails-ai/guardrails) ⭐ 7,290 | 🐛 84 | 🌐 Python | 📅 2026-08-14** 🟢 — Python framework for adding input/output guards, validators, structured-output controls, and Guardrails Hub checks to LLM applications. *(Guardrails AI)* *(★ 7,289 · updated 2026-08-14)*
  * **Related:** [NeMo Guardrails](https://github.com/NVIDIA-NeMo/Guardrails) ⭐ 6,962 | 🐛 217 | 🌐 Python | 📅 2026-08-15 · [LLM Guard](https://github.com/protectai/llm-guard) ⚠️ Archived
* **[NeMo Guardrails](https://github.com/NVIDIA-NeMo/Guardrails) ⭐ 6,962 | 🐛 217 | 🌐 Python | 📅 2026-08-15** 🟢 — Programmable guardrails (input/output/dialog/retrieval rails) for LLM apps. *(NVIDIA)* *(★ 6,959 · updated 2026-08-13)*
* **[Giskard](https://github.com/Giskard-AI/giskard-oss) ⭐ 5,754 | 🐛 61 | 🌐 Python | 📅 2026-08-14** 🟢 — Open-source evaluation, testing, and red-teaming framework for LLM agents, including agent vulnerability scanning and RAG evaluation workflows. *(Giskard AI)* *(★ 5,753 · updated 2026-08-14)*
  * **Related:** [Moonshot](https://github.com/aiverify-foundation/moonshot) ⭐ 347 | 🐛 1 | 🌐 Python | 📅 2026-06-10 · [promptfoo](https://github.com/promptfoo/promptfoo) ⭐ 24,276 | 🐛 505 | 🌐 TypeScript | 📅 2026-08-16
* **[llm-attacks (GCG)](https://github.com/llm-attacks/llm-attacks) ⭐ 4,761 | 🐛 69 | 🌐 Python | 📅 2024-08-02** 🟢🔬 — Canonical Greedy Coordinate Gradient adversarial-suffix attack implementation for transferable attacks on aligned language models. *(★ 4,761 · updated 2024-08-02)*
  * **Related:** [nanoGCG](https://github.com/GraySwanAI/nanoGCG) ⭐ 346 | 🐛 14 | 🌐 Python | 📅 2025-05-13
* **[PurpleLlama](https://github.com/meta-llama/PurpleLlama) ⭐ 4,355 | 🐛 81 | 🌐 Python | 📅 2026-08-14** 🟢 — Llama Guard classifiers, CodeShield, and CyberSecEval. *(Meta)* *(★ 4,352 · updated 2026-08-14)*
* **[PyRIT](https://github.com/microsoft/PyRIT) ⭐ 4,312 | 🐛 81 | 🌐 Python | 📅 2026-08-15** 🟢 — Python Risk Identification Tool; battle-tested across 100+ GenAI red-team operations. *(Microsoft)* *(★ 4,310 · updated 2026-08-14)*
* **[TextAttack](https://github.com/QData/TextAttack) ⭐ 3,467 | 🐛 18 | 🌐 Python | 📅 2026-08-15** 🟢🔬 — Python framework for adversarial attacks, data augmentation, and training for NLP models; useful for robustness testing beyond chat-only LLM scanners. *(★ 3,467 · updated 2026-08-15)*
* **[LLM Guard](https://github.com/protectai/llm-guard) ⚠️ Archived** 🟢 — Suite of input/output scanners (PII, prompt injection, etc.). *(Protect AI)* — **note:** archived by the maintainer; retained as a historical reference for local input/output guardrails. *(★ 3,201 · updated 2026-07-08)*
  * **Related:** [Rebuff](https://github.com/protectai/rebuff) ⚠️ Archived
* **[DeepTeam](https://github.com/confident-ai/deepteam) ⭐ 2,451 | 🐛 55 | 🌐 Python | 📅 2026-08-12** 🟢 — Open-source framework for red-teaming LLMs and LLM systems across jailbreaks, prompt injection, data leakage, and safety risks. *(★ 2,452 · updated 2026-08-12)*
* **[llm-security](https://github.com/greshake/llm-security) ⭐ 2,127 | 🐛 1 | 🌐 Jupyter Notebook | 📅 2025-07-17** 🔬 — Original PoC for indirect prompt-injection attacks. *(★ 2,127 · updated 2025-07-17)*
* **[AI-Red-Teaming-Playground-Labs](https://github.com/microsoft/AI-Red-Teaming-Playground-Labs) ⭐ 2,045 | 🐛 28 | 🌐 TypeScript | 📅 2026-02-13** 🟢 — CTFd-based AI red-team training challenges. *(Microsoft)* *(★ 2,045 · updated 2025-10-07)*
* **[agentic\_security](https://github.com/msoedov/agentic_security) ⭐ 1,966 | 🐛 74 | 🌐 Python | 📅 2026-07-31** 🟢 — Agentic LLM vulnerability scanner and AI red-team kit for jailbreaks, prompt injection, fuzzing, and API stress testing. *(★ 1,966 · updated 2026-07-31)*
  * **Related:** [garak](https://github.com/NVIDIA/garak) ⭐ 8,827 | 🐛 389 | 🌐 Python | 📅 2026-08-14 · [spikee](https://github.com/ReversecLabs/spikee) ⭐ 231 | 🐛 5 | 🌐 Python | 📅 2026-07-13
* **[Rebuff](https://github.com/protectai/rebuff) ⚠️ Archived** 🟢 — Archived prompt-injection detector (heuristics + LLM + vector DB + canary tokens). *(Protect AI)* — **note:** archived by the maintainer; retained as a historical prompt-injection defense reference. *(★ 1,520 · updated 2024-01-25)*
  * **Related:** [LLM Guard](https://github.com/protectai/llm-guard) ⚠️ Archived
* **[wallbreaker](https://github.com/JailbrokenAI/wallbreaker) ⭐ 1,181 | 🐛 6 | 🌐 Python | 📅 2026-08-11** 🟢🔬⚠️ — Claude-Code-style terminal and red-team harness for authorized LLM safety testing, with HarmBench, PAIR/TAP, Crescendo, GCG-style workflows, Parseltongue transforms, MCP tooling, LLM judges, and reproducible run artifacts. — **note:** offensive jailbreak toolkit for authorized testing only; AGPL-3.0 licensed and NOTICE flags external jailbreak corpora with their own or missing upstream licenses. *(★ 1,173 · updated 2026-08-11)*
  * **Related:** [HarmBench](https://github.com/centerforaisafety/HarmBench) ⭐ 1,029 | 🐛 39 | 🌐 Jupyter Notebook | 📅 2024-08-16 · [PyRIT](https://github.com/microsoft/PyRIT) ⭐ 4,312 | 🐛 81 | 🌐 Python | 📅 2026-08-15 · [garak](https://github.com/NVIDIA/garak) ⭐ 8,827 | 🐛 389 | 🌐 Python | 📅 2026-08-14
* **[Anamorpher](https://github.com/trailofbits/anamorpher) ⭐ 1,076 | 🐛 9 | 🌐 Python | 📅 2026-05-19** 🟢🔬 — Research tool with a frontend and Python API for crafting and visualizing image-scaling attacks that reveal hidden prompt injections to multimodal AI systems after downscaling. *(Trail of Bits)* — **note:** active beta research tool for authorized testing; generated payloads are sensitive to the target's image-resampling implementation and preprocessing pipeline. *(★ 1,076 · updated 2026-02-19)*
  * **Related:** [PromptFuzz](https://github.com/PromptFuzz/PromptFuzz) ⭐ 342 | 🐛 2 | 🌐 Rust | 📅 2026-05-15 · [promptfoo](https://github.com/promptfoo/promptfoo) ⭐ 24,276 | 🐛 505 | 🌐 TypeScript | 📅 2026-08-16
  * **Sources:** [Trail of Bits research announcement](https://blog.trailofbits.com/2025/08/21/weaponizing-image-scaling-against-production-ai-systems/)
* **[HarmBench](https://github.com/centerforaisafety/HarmBench) ⭐ 1,029 | 🐛 39 | 🌐 Jupyter Notebook | 📅 2024-08-16** 🟢🔬 — ICML 2024 standardized evaluation framework for automated red-teaming and robust-refusal benchmarking. *(Center for AI Safety)* *(★ 1,029 · updated 2024-08-05)*
  * **Related:** [JailbreakBench](https://github.com/JailbreakBench/jailbreakbench) ⭐ 654 | 🐛 12 | 🌐 Python | 📅 2025-04-04
* **[LangKit](https://github.com/whylabs/langkit) ⭐ 994 | 🐛 37 | 🌐 Jupyter Notebook | 📅 2024-11-22** 🟢 — LLM monitoring toolkit extracting safety/security signals such as jailbreak similarity, prompt-injection similarity, hallucination checks, PII patterns, toxicity, and refusal metrics. *(WhyLabs)* *(★ 994 · updated 2024-11-22)*
* **[Counterfit](https://github.com/Azure/counterfit) ⭐ 934 | 🐛 25 | 🌐 Python | 📅 2025-07-18** 🟢 — ML/AI penetration-testing automation tool. *(Microsoft)* *(★ 934 · updated 2025-07-18)*
* **[EasyJailbreak](https://github.com/EasyJailbreak/EasyJailbreak) ⭐ 886 | 🐛 19 | 🌐 Python | 📅 2026-03-30** 🟢🔬 — Framework for building and testing adversarial jailbreak prompts. *(★ 886 · updated 2026-03-30)*
* **[prompt-injection-defenses](https://github.com/tldrsec/prompt-injection-defenses) ⭐ 724 | 🐛 10 | 📅 2025-02-22** 🟢⚠️ — Curated catalog of practical defenses against prompt injection. *(★ 724 · updated 2025-02-22)*
* **[JailbreakBench](https://github.com/JailbreakBench/jailbreakbench) ⭐ 654 | 🐛 12 | 🌐 Python | 📅 2025-04-04** 🟢🔬 — NeurIPS 2024 open robustness benchmark and leaderboard for generating and defending against LLM jailbreaks. *(★ 654 · updated 2025-03-31)*
* **[GPTFuzz](https://github.com/sherdencooper/GPTFuzz) ⭐ 604 | 🐛 17 | 🌐 Python | 📅 2026-02-27** 🟢🔬 — Research framework for red-teaming LLMs with auto-generated jailbreak prompts. *(★ 604 · updated 2026-02-27)*
* **[Vigil](https://github.com/deadbits/vigil-llm) ⭐ 496 | 🐛 16 | 🌐 Python | 📅 2024-01-31** 🟢🔬 — Library/REST API to scan prompts and responses for prompt injection. *(★ 495 · updated 2024-01-31)*
* **[Open-Prompt-Injection](https://github.com/liu00222/Open-Prompt-Injection) ⭐ 478 | 🐛 14 | 🌐 Python | 📅 2025-10-29** 🟢🔬 — Open-source toolkit and benchmark for implementing and evaluating prompt-injection attacks, defenses, and LLM-integrated applications. *(★ 478 · updated 2025-10-29)*
* **[LLMmap](https://github.com/pasquini-dario/LLMmap) ⭐ 424 | 🐛 6 | 🌐 Python | 📅 2025-07-24** 🟢🔬 — Minimal-query fingerprinting tool for identifying LLMs from behavioral traces, with a pretrained open-set inference model. *(★ 423 · updated 2025-07-24)*
* **[Kiji Privacy Proxy](https://github.com/Dataiku/kiji-proxy) ⭐ 422 | 🐛 38 | 🌐 Go | 📅 2026-08-01** 🟢 — Local privacy proxy for OpenAI-compatible AI API traffic that detects and masks 26 PII types with an ONNX model before forwarding requests, then restores mappings in responses. *(Dataiku 575 Lab)* — **note:** protects configured proxied traffic, not every path by which an application or agent can disclose data; operators retain responsibility for proxy routing and local mapping storage. *(★ 421 · updated 2026-07-27)*
  * **Related:** [LLM Guard](https://github.com/protectai/llm-guard) ⚠️ Archived · [Kiji PII model](https://huggingface.co/DataikuNLP/kiji-pii-model-onnx)
* **[HackAgent](https://github.com/AISecurityLab/hackagent) ⭐ 358 | 🐛 11 | 🌐 Python | 📅 2026-08-15** 🟢 — Python SDK and CLI for red-teaming AI agents with research-backed attacks such as AdvPrefix, AutoDAN-Turbo, PAIR, TAP, FlipAttack, BoN, and static templates across agent frameworks. — **note:** works locally without an API key; optional cloud reporting is available. *(★ 358 · updated 2026-08-15)*
  * **Related:** [PyRIT](https://github.com/microsoft/PyRIT) ⭐ 4,312 | 🐛 81 | 🌐 Python | 📅 2026-08-15 · [garak](https://github.com/NVIDIA/garak) ⭐ 8,827 | 🐛 389 | 🌐 Python | 📅 2026-08-14 · [agentic\_security](https://github.com/msoedov/agentic_security) ⭐ 1,966 | 🐛 74 | 🌐 Python | 📅 2026-07-31
* **[Moonshot](https://github.com/aiverify-foundation/moonshot) ⭐ 347 | 🐛 1 | 🌐 Python | 📅 2026-06-10** 🟢 — Modular tool for benchmarking, red-teaming, and evaluating LLM applications with custom connectors and recipes. *(AI Verify Foundation)* *(★ 347 · updated 2026-02-05)*
* **[nanoGCG](https://github.com/GraySwanAI/nanoGCG) ⭐ 346 | 🐛 14 | 🌐 Python | 📅 2025-05-13** 🟢 — Fast, lightweight PyTorch implementation of the GCG adversarial-suffix algorithm. *(★ 346 · updated 2025-05-13)*
  * **Related:** [llm-attacks (GCG)](https://github.com/llm-attacks/llm-attacks) ⭐ 4,761 | 🐛 69 | 🌐 Python | 📅 2024-08-02
* **[Do-Not-Answer](https://github.com/Libr-AI/do-not-answer) ⭐ 341 | 🐛 0 | 🌐 Jupyter Notebook | 📅 2024-06-07** 🟢🔬 — Dataset for evaluating LLM safeguards on unsafe or policy-sensitive prompts. *(★ 341 · updated 2024-06-07)*
* **[Augustus](https://github.com/praetorian-inc/augustus) ⭐ 279 | 🐛 33 | 🌐 Go | 📅 2026-08-16** 🟢 — Single-binary LLM security testing framework for prompt injection, jailbreaks, and adversarial attacks across many providers. *(Praetorian)* *(★ 278 · updated 2026-08-13)*
  * **Related:** [garak](https://github.com/NVIDIA/garak) ⭐ 8,827 | 🐛 389 | 🌐 Python | 📅 2026-08-14 · [PyRIT](https://github.com/microsoft/PyRIT) ⭐ 4,312 | 🐛 81 | 🌐 Python | 📅 2026-08-15
* **[LLAMATOR](https://github.com/LLAMATOR-Core/llamator) ⭐ 215 | 🐛 11 | 🌐 Python | 📅 2026-05-20** 🟢⚠️ — Red-teaming framework for chatbots and GenAI systems; CC BY-NC-SA 4.0 licensed. *(★ 215 · updated 2026-01-15)*
* **[PINT Benchmark](https://github.com/lakeraai/pint-benchmark) ⚠️ Archived** 🟢🔬 — Prompt-injection test benchmark for evaluating detectors and guardrails across multilingual prompt injection, jailbreak, benign, and hard-negative inputs. *(Lakera)* — **note:** archived benchmark retained as a historical research reference; use newer maintained corpora for current detector comparisons. *(★ 198 · updated 2026-04-02)*
  * **Related:** [Open-Prompt-Injection](https://github.com/liu00222/Open-Prompt-Injection) ⭐ 478 | 🐛 14 | 🌐 Python | 📅 2025-10-29 · [Prompt Guard 86M](https://huggingface.co/meta-llama/Prompt-Guard-86M)
* **[Whistleblower](https://github.com/Repello-AI/whistleblower) ⭐ 177 | 🐛 13 | 🌐 Python | 📅 2025-10-31** 🟢⚠️ — Offensive testing tool for inferring system prompts and discovering capabilities of LLM applications exposed through APIs. *(Repello AI)* — **note:** no LICENSE file found. *(★ 177 · updated 2025-10-27)*
* **[Prompt SIREN](https://github.com/facebookresearch/prompt-siren) ⭐ 61 | 🐛 39 | 🌐 Python | 📅 2026-07-24** 🟢🔬 — Research workbench for developing and evaluating prompt-injection attacks and defenses with state-machine agent control, AgentDojo/SWE-bench integrations, configuration sweeps, and reproducible result aggregation. *(Meta AI)* — **note:** experiment harness; running target evaluations requires model-provider credentials and may need Docker or browser extras depending on the selected environment. *(★ 61 · updated 2026-05-18)*
  * **Related:** [AgentDojo](https://github.com/ethz-spylab/agentdojo) ⭐ 751 | 🐛 41 | 🌐 Python | 📅 2026-06-02 · [PyRIT](https://github.com/microsoft/PyRIT) ⭐ 4,312 | 🐛 81 | 🌐 Python | 📅 2026-08-15
* **[PIArena](https://github.com/sleeepeer/PIArena) ⭐ 46 | 🐛 0 | 🌐 Python | 📅 2026-04-28** 🟢🔬 — ACL 2026 toolbox and benchmark for prompt-injection attacks and defenses, with ready-to-use attacks/defenses, evaluation pipelines, agent benchmarks, a Hugging Face dataset, and leaderboard. *(★ 46 · updated 2026-04-20)*
  * **Related:** [PINT Benchmark](https://github.com/lakeraai/pint-benchmark) ⚠️ Archived · [Open-Prompt-Injection](https://github.com/liu00222/Open-Prompt-Injection) ⭐ 478 | 🐛 14 | 🌐 Python | 📅 2025-10-29
* **[HiveTrace Red](https://github.com/HiveTrace/HiveTraceRed) ⭐ 29 | 🐛 1 | 🌐 Python | 📅 2026-08-13** 🟢 — Early-stage LLM red-teaming framework with 80+ attack templates, async evaluation pipelines, WildGuard evaluators, multi-provider support, and HTML reporting. — **note:** young project with limited independent adoption signal. *(★ 29 · updated 2026-08-13)*
  * **Related:** [garak](https://github.com/NVIDIA/garak) ⭐ 8,827 | 🐛 389 | 🌐 Python | 📅 2026-08-14 · [PyRIT](https://github.com/microsoft/PyRIT) ⭐ 4,312 | 🐛 81 | 🌐 Python | 📅 2026-08-15 · [promptfoo](https://github.com/promptfoo/promptfoo) ⭐ 24,276 | 🐛 505 | 🌐 TypeScript | 📅 2026-08-16
* **[little-canary](https://github.com/hermes-labs-ai/little-canary) ⭐ 27 | 🐛 0 | 🌐 Python | 📅 2026-08-14** 🟢🔬 — Prompt-injection preflight risk sensor that routes untrusted input through a powerless sacrificial model, then reads response residue to return pass/flag/block before the primary agent acts. — **note:** experimental sensing layer, not a security guarantee or runtime containment. A failed canary can return availability-first routing with explicit degraded coverage; remote/OpenAI-compatible canary or judge endpoints receive raw input. *(★ 27 · updated 2026-08-14)*
  * **Related:** [Rebuff](https://github.com/protectai/rebuff) ⚠️ Archived · [prompt-injection-defenses](https://github.com/tldrsec/prompt-injection-defenses) ⭐ 724 | 🐛 10 | 📅 2025-02-22
* **[NuGuard](https://github.com/NuGuardAI/nuguard) ⭐ 23 | 🐛 49 | 🌐 Python | 📅 2026-08-15** 🟢 — Generates an AI-SBOM, statically analyzes agentic applications, red-teams live targets for prompt injection/tool misuse/data exfiltration, and validates behavioral policy compliance with SARIF, JSON, and Markdown reports. *(NuGuard AI)* — **note:** beta project; live red-team scans actively probe the target and require authorization. LLM-assisted features need provider credentials, and the optional NuGuard.ai hosted offering adds commercial features. *(★ 23 · updated 2026-08-14)*
  * **Related:** [garak](https://github.com/NVIDIA/garak) ⭐ 8,827 | 🐛 389 | 🌐 Python | 📅 2026-08-14 · [Medusa](https://github.com/Pantheon-Security/medusa) ⭐ 964 | 🐛 2 | 🌐 Python | 📅 2026-08-10
* **[JailbreakLLMs](https://github.com/TrustAIRLab/JailbreakLLMs) ⭐ 23 | 🐛 0 | 📅 2024-02-21** 🔬⚠️ — Research dataset of 6,387 ChatGPT prompts, including in-the-wild jailbreak prompts from Reddit, Discord, websites, and open datasets. *(★ 23 · updated 2024-02-21)*

### Prompt-Injection Classifier Models

* **[Wolf Defender Prompt Injection](https://huggingface.co/patronus-studio/wolf-defender-prompt-injection)** 🟢 — Hugging Face text-classification model for prompt-injection detection in agents, chatbots, and CI workflows. *(Patronus Studio / Casdo Labs)* *license: Apache-2.0 · access: open · artifacts: Safetensors, ONNX.*
* **[DeBERTa v3 Prompt Injection v2](https://huggingface.co/protectai/deberta-v3-base-prompt-injection-v2)** 🟢 — Apache-licensed prompt-injection classifier usable via Transformers pipelines and ONNX. *(Protect AI)* *license: Apache-2.0 · access: open · artifacts: Safetensors, ONNX.*
* **[PromptGuard](https://huggingface.co/codeintegrity-ai/promptguard)** 🟢⚠️ — ModernBERT-based prompt-injection and jailbreak classifier. *(CodeIntegrity AI)* *license: Apache-2.0 · access: gated auto · artifacts: Safetensors.*
* **[Prompt Guard 86M](https://huggingface.co/meta-llama/Prompt-Guard-86M)** 🟠⚠️ — Meta prompt-injection and jailbreak classifier from the Llama Guard family. *(Meta)* *license: Llama 3.1 · access: gated manual · artifacts: Safetensors.*
* **[prompt-injection-sentinel](https://huggingface.co/qualifire/prompt-injection-sentinel)** 🔬⚠️ — ModernBERT-large classifier for prompt-injection and jailbreak detection. *(Qualifire)* *license: other · access: gated auto · artifacts: Safetensors.*

### Specialty Security LLMs

* **[SecGPT](https://github.com/Clouditera/SecGPT) ⭐ 3,099 | 🐛 52 | 🌐 Python | 📅 2025-06-25** 🟢 — Open cybersecurity-tuned LLM family for vulnerability analysis, log/traffic investigation, anomaly detection, attack/defense reasoning, command analysis, and security Q\&A. *(Clouditera)* *(★ 3,099 · updated 2025-06-25)*
  * **Related:** [SecGPT model](https://huggingface.co/clouditera/secgpt)
* **[Antares-1B](https://huggingface.co/fdtn-ai/antares-1b)** 🟢⚠️ — Open-weight security SLM specialized for agentic vulnerability localization: it explores repository snapshots through a terminal-style loop and ranks likely vulnerable files for analyst review. *(Cisco Foundation AI)* *license: Apache-2.0 · access: gated manual · artifacts: Safetensors + CLI ZIP.* — **note:** HF access is gated/manual; related smaller model: [Antares-350M](https://huggingface.co/fdtn-ai/antares-350m), benchmark: [VLoc Bench](https://cisco-foundation-ai.github.io/vulnerability-localization-benchmark/).
* **[Trendyol Cybersecurity LLM v2 70B](https://huggingface.co/Trendyol/Trendyol-Cybersecurity-LLM-v2-70B-Q4_K_M)** 🟢 — Defense-focused cybersecurity LLM based on Llama-3.3-70B, trained on an alignment-safe security instruction dataset for SOC, cloud, AppSec, detection, and vulnerability-management workflows. *(Trendyol Group Security Team)* *license: Apache-2.0 · access: open · artifacts: GGUF.*
* **[WhiteRabbitNeo 2.5 Qwen Coder 7B](https://huggingface.co/WhiteRabbitNeo/WhiteRabbitNeo-2.5-Qwen-2.5-Coder-7B)** 🟢⚠️ — Cybersecurity-oriented Qwen2.5-Coder fine-tune positioned for offensive and defensive security assistance. *(WhiteRabbitNeo)* *license: Apache-2.0 + WhiteRabbitNeo restrictions · access: open · artifacts: Safetensors.*
* **[Lily-Cybersecurity-7B-v0.2](https://huggingface.co/segolilylabs/Lily-Cybersecurity-7B-v0.2)** 🟢 — Mistral-7B-Instruct fine-tune for cybersecurity assistance, trained on hand-crafted security and hacking-related instruction pairs. *(Segolily Labs)* *license: Apache-2.0 · access: open · artifacts: Safetensors.*
* **[RavenX CyberAgent 35B Q4\_K\_M](https://huggingface.co/deadbydawn101/RavenX-CyberAgent-Qwen3.6-35B-A3B-Opus-4.7-OpenMythos-Pentester-BugHunter-RATH-GGUF)** 🟢⚠️ — GGUF security-specialized text-generation model positioned for pentest, bug-bounty, tool-calling, MCP, CVSS/CWE, and MITRE ATT\&CK workflows. *(RavenX LLC / DeadByDawn101)* *license: Apache-2.0 · access: open · artifacts: GGUF.* — **note:** built from an abliterated base model and marketed for autonomous security assessment; use only in authorized, sandboxed agent harnesses with tool-call validation.

***

## LLM Honeypots & Deception

Honeypots and deception that use LLMs to simulate convincing systems.

* **[Beelzebub](https://github.com/beelzebub-labs/beelzebub) ⭐ 2,149 | 🐛 6 | 🌐 Go | 📅 2026-08-11** 🟢⚠️ — Low-code honeypot using LLMs to simulate SSH/HTTP/MCP services (Go). — **note:** GPL-3.0 licensed. *(★ 2,149 · updated 2026-08-11)*
* **[DECEIVE](https://github.com/splunk/DECEIVE) ⭐ 288 | 🐛 14 | 🌐 Python | 📅 2026-08-05** 🟢🔬 — Proof-of-concept LLM-powered SSH honeypot that evaluates sessions as benign, suspicious, or malicious. *(Splunk)* *(★ 288 · updated 2026-05-13)*
* **[VelLMes](https://github.com/stratosphereips/VelLMes-AI-Honeypot) ⭐ 78 | 🐛 1 | 🌐 Python | 📅 2025-02-18** 🟢🔬 — Multi-protocol LLM honeypot framework (successor to shelLM). *(★ 78 · updated 2025-02-18)*
  * **Related:** [shelLM](https://github.com/stratosphereips/shelLM) ⭐ 64 | 🐛 2 | 🌐 Python | 📅 2026-06-25
* **[shelLM](https://github.com/stratosphereips/shelLM) ⭐ 64 | 🐛 2 | 🌐 Python | 📅 2026-06-25** 🟢🔬 — LLM-powered SSH honeypot (paper *"LLM in the Shell"*). *(★ 64 · updated 2026-06-25)*
  * **Related:** [VelLMes](https://github.com/stratosphereips/VelLMes-AI-Honeypot) ⭐ 78 | 🐛 1 | 🌐 Python | 📅 2025-02-18
* **[llm-honeypot](https://github.com/PalisadeResearch/llm-honeypot) ⭐ 60 | 🐛 1 | 🌐 HTML | 📅 2026-08-10** 🔬⚠️ — Cowrie SSH honeypot extended with prompt-injection traps to detect LLM hacker agents. *(Palisade Research)* *(★ 60 · updated 2026-01-23)*
* **[TRAP](https://github.com/parameterlab/trap) ⭐ 15 | 🐛 0 | 🌐 Jupyter Notebook | 📅 2024-11-20** 🟢🔬 — Research code for Targeted Random Adversarial Prompt honeypots that identify black-box LLM usage through model-specific prompt suffixes (ACL 2024 Findings). *(★ 15 · updated 2024-11-20)*

***

## CTF / Exploit / Bug-Bounty Agents & Benchmarks

Offensive agents and the benchmarks used to evaluate them.

* **[SWE-agent (EnIGMA)](https://github.com/SWE-agent/SWE-agent) ⭐ 20,064 | 🐛 74 | 🌐 Python | 📅 2026-08-10** 🟢🔬 — EnIGMA offensive-CTF mode; SOTA on NYU CTF, InterCode-CTF, and Cybench (v0.7 branch). *(★ 20,063 · updated 2026-07-16)*
  * **Related:** [Cybench](https://github.com/andyzorigin/cybench) ⭐ 311 | 🐛 103 | 🌐 HTML | 📅 2026-07-09 · [NYU CTF Bench](https://github.com/NYU-LLM-CTF/NYU_CTF_Bench) ⭐ 169 | 🐛 4 | 🌐 Python | 📅 2025-09-22 · [InterCode](https://github.com/princeton-nlp/intercode) ⭐ 254 | 🐛 13 | 🌐 Python | 📅 2024-05-05
* **[claude-bug-bounty](https://github.com/shuvonsec/claude-bug-bounty) ⭐ 4,228 | 🐛 1 | 🌐 Python | 📅 2026-08-10** 🟢 — Claude Code plugin orchestrating recon → vuln classes → reporting. *(★ 4,227 · updated 2026-08-10)*
* **[ai-exploits](https://github.com/protectai/ai-exploits) ⭐ 1,745 | 🐛 3 | 🌐 Python | 📅 2024-10-23** 🟢 — Real-world AI/ML exploits (Metasploit modules + Nuclei templates) for MLflow, Ray, H2O. *(Protect AI)* *(★ 1,745 · updated 2024-10-23)*
* **[CyberGym](https://github.com/sunblaze-ucb/cybergym) ⭐ 730 | 🐛 6 | 🌐 Python | 📅 2026-08-04** 🟢🔬 — Large-scale evaluation framework for AI-agent vulnerability analysis on real-world tasks, with locally deployed challenge infrastructure, task generation, and proof-of-concept validation. *(UC Berkeley / Sunblaze)* — **note:** deploy only in an isolated local environment; the full benchmark runtime is extremely large (documentation cites up to \~10 TB) and must not be exposed to the public internet. *(★ 727 · updated 2026-08-04)*
  * **Related:** [Cybench](https://github.com/andyzorigin/cybench) ⭐ 311 | 🐛 103 | 🌐 HTML | 📅 2026-07-09 · [CVE-Bench](https://github.com/uiuc-kang-lab/cve-bench) ⭐ 270 | 🐛 3 | 🌐 Python | 📅 2026-01-14
* **[inspect\_evals](https://github.com/UKGovernmentBEIS/inspect_evals) ⭐ 627 | 🐛 153 | 🌐 Python | 📅 2026-08-16** 🟢🔬 — Maintained Inspect AI evaluation suite containing multiple cyber benchmarks and tasks. *(UK AI Security Institute)* *(★ 627 · updated 2026-08-14)*
* **[Damn Vulnerable LLM Agent](https://github.com/ReversecLabs/damn-vulnerable-llm-agent) ⭐ 504 | 🐛 4 | 🌐 Python | 📅 2025-06-25** 🟢🔬 — Deliberately vulnerable LangChain ReAct agent for practicing prompt-injection and Thought/Action/Observation injection attacks. *(ReversecLabs / WithSecure)* *(★ 504 · updated 2025-06-25)*
  * **Related:** [spikee](https://github.com/ReversecLabs/spikee) ⭐ 231 | 🐛 5 | 🌐 Python | 📅 2026-07-13
* **[Bug-Bounty-Agents](https://github.com/matty69v/Bug-Bounty-Agents) ⭐ 369 | 🐛 0 | 🌐 Shell | 📅 2026-04-30** 🟢 — 43 AI agent personas for Claude Code / Copilot / Cursor across the bug-bounty lifecycle. *(★ 368 · updated 2026-04-30)*
* **[AI Goat](https://github.com/dhammon/ai-goat) ⭐ 355 | 🐛 2 | 🌐 Python | 📅 2024-08-22** 🟢🔬⚠️ — Vulnerable-by-design local LLM CTF for learning prompt injection, insecure output handling, data leakage, excessive agency, and related LLM app risks. — **note:** GPL-2.0 licensed. *(★ 355 · updated 2024-08-22)*
* **[ExploitBench](https://github.com/exploitbench/exploitbench) ⭐ 344 | 🐛 9 | 🌐 Python | 📅 2026-07-04** 🔬 — Measures AI-agent progress on V8/Chromium exploit ladders. *(★ 344 · updated 2026-07-04)*
* **[Cybench](https://github.com/andyzorigin/cybench) ⭐ 311 | 🐛 103 | 🌐 HTML | 📅 2026-07-09** 🔬 — 40 professional CTF tasks across 4 competitions; widely used by AI safety institutes. *(★ 311 · updated 2026-07-09)*
* **[LLMVault](https://github.com/CyberSunil/LLMVault) ⭐ 295 | 🐛 2 | 🌐 Python | 📅 2026-08-10** 🟢🔬 — Intentionally vulnerable LLM security-training platform with OWASP LLM Top 10 labs, CTF-style challenges, hints, scoring, and mitigation guidance. — **note:** deliberately vulnerable training target; run only in an isolated, authorized environment. Live Mode optionally requires Ollama or provider credentials. *(★ 295 · updated 2026-08-10)*
* **[CVE-Bench](https://github.com/uiuc-kang-lab/cve-bench) ⭐ 270 | 🐛 3 | 🌐 Python | 📅 2026-01-14** 🟢🔬 — ICML 2025 benchmark that evaluates AI agents against reproducible Docker environments for real critical-severity web-application CVEs and exploit objectives. — **note:** runs intentionally vulnerable services and should be used only in isolated environments; arm64 support is experimental. *(★ 270 · updated 2026-01-14)*
  * **Related:** [CyberGym](https://github.com/sunblaze-ucb/cybergym) ⭐ 730 | 🐛 6 | 🌐 Python | 📅 2026-08-04 · [BountyBench](https://github.com/bountybench/bountybench) ⭐ 102 | 🐛 105 | 🌐 Jupyter Notebook | 📅 2025-07-24
* **[InterCode](https://github.com/princeton-nlp/intercode) ⭐ 254 | 🐛 13 | 🌐 Python | 📅 2024-05-05** 🔬 — Interactive-coding benchmark incl. InterCode-CTF. *(★ 254 · updated 2024-05-05)*
* **[NYU CTF Bench](https://github.com/NYU-LLM-CTF/NYU_CTF_Bench) ⭐ 169 | 🐛 4 | 🌐 Python | 📅 2025-09-22** 🔬 — Dockerized CSAW CTF challenges for LLM-agent evaluation. *(★ 169 · updated 2025-09-22)*
* **[BountyBench](https://github.com/bountybench/bountybench) ⭐ 102 | 🐛 105 | 🌐 Jupyter Notebook | 📅 2025-07-24** 🔬 — 25 real systems / 40 bug bounties for Detect-Exploit-Patch evaluation. *(★ 102 · updated 2025-06-22)*
* **[Cyber-Zero](https://github.com/amazon-science/Cyber-Zero) ⚠️ Archived** 🔬 — Trains cybersecurity agents without runtime; ships an EnIGMA+ scaffold. *(Amazon Science)* — **note:** archived research artifact retained as a historical reference for training cybersecurity agents without a live runtime. *(★ 101 · updated 2025-09-02)*
  * **Sources:** [SWE-agent](https://github.com/SWE-agent/SWE-agent) ⭐ 20,064 | 🐛 74 | 🌐 Python | 📅 2026-08-10
  * **Related:** [SWE-agent](https://github.com/SWE-agent/SWE-agent) ⭐ 20,064 | 🐛 74 | 🌐 Python | 📅 2026-08-10
* **[AIGoat](https://github.com/AISecurityConsortium/AIGoat) ⭐ 75 | 🐛 1 | 🌐 JavaScript | 📅 2026-04-24** 🟢🔬⚠️ — Local-first vulnerable LLM security playground with guided OWASP LLM Top 10 attack labs, CTF challenges, progressive defenses, and an Ollama-backed AI shopping-assistant target. — **note:** platform code is Apache-2.0, but training/challenge content is CC BY-NC-SA-4.0 and requires permission for commercial workshops. *(★ 75 · updated 2026-04-24)*
* **[CTFTiny](https://github.com/NYU-LLM-CTF/CTFTiny) ⭐ 18 | 🐛 1 | 🌐 Python | 📅 2026-03-10** 🔬⚠️ — Lightweight CTF benchmark from the NYU LLM CTF group; GPL-2.0 licensed. *(★ 18 · updated 2026-03-10)*
  * **Related:** [NYU CTF Bench](https://github.com/NYU-LLM-CTF/NYU_CTF_Bench) ⭐ 169 | 🐛 4 | 🌐 Python | 📅 2025-09-22

***

## Cloud / IaC / DFIR / OSINT / Phishing

AI tooling for cloud/IaC security, digital forensics, OSINT, and phishing detection.

* **[osintgpt](https://github.com/estebanpdl/osintgpt) ⭐ 525 | 🐛 0 | 🌐 Python | 📅 2023-12-11** 🟢⚠️ — OpenAI embeddings + Qdrant over OSINT corpora. *(★ 524 · updated 2023-12-11)*
* **[llm\_osint](https://github.com/sshh12/llm_osint) ⭐ 317 | 🐛 0 | 🌐 Python | 📅 2024-11-02** 🟢🔬 — Proof-of-concept LLM OSINT framework using knowledge and web agents for internet research workflows. *(★ 316 · updated 2024-11-02)*
* **[Julius](https://github.com/praetorian-inc/julius) ⭐ 208 | 🐛 16 | 🌐 Go | 📅 2026-08-11** 🟢 — Local Go tool that fingerprints LLM service infrastructure on authorized endpoints, identifies 60+ serving, gateway, MCP, and RAG platforms, and can enumerate exposed models. *(Praetorian)* — **note:** use only against endpoints you own or are authorized to assess. *(★ 208 · updated 2026-08-06)*
  * **Related:** [AI-Infra-Guard](https://github.com/Tencent/AI-Infra-Guard) ⭐ 4,513 | 🐛 18 | 🌐 Python | 📅 2026-08-12 · [ai\_osint](https://github.com/7WaySecurity/ai_osint) ⭐ 154 | 🐛 0 | 📅 2026-06-19
* **[Cynative](https://github.com/cynative/cynative) ⭐ 190 | 🐛 15 | 🌐 Go | 📅 2026-08-14** 🟢 — Local AI security research agent for cloud, code, and runtime environments across GitHub, GitLab, AWS, GCP, Azure, and Kubernetes, with read-only action gates, sandboxed code execution, evidence-backed verification, and audit logs. *(★ 190 · updated 2026-08-14)*
  * **Related:** [Fraim](https://github.com/fraim-dev/fraim) ⭐ 160 | 🐛 22 | 🌐 Python | 📅 2026-02-09 · [EscalateGPT](https://github.com/tenable/EscalateGPT) ⭐ 122 | 🐛 29 | 🌐 Python | 📅 2026-08-05
* **[ai\_osint](https://github.com/7WaySecurity/ai_osint) ⭐ 154 | 🐛 0 | 📅 2026-06-19** 🟢 — Curated AI-OSINT dorks, queries, and techniques for discovering exposed LLM and AI infrastructure. *(★ 154 · updated 2026-06-19)*
* **[EscalateGPT](https://github.com/tenable/EscalateGPT) ⭐ 122 | 🐛 29 | 🌐 Python | 📅 2026-08-05** 🟢 — GPT-based discovery of privilege-escalation paths in AWS IAM policies. *(Tenable)* *(★ 122 · updated 2024-01-17)*
* **[mcp-dnstwist](https://github.com/BurtTheCoder/mcp-dnstwist) ⭐ 51 | 🐛 7 | 🌐 JavaScript | 📅 2025-03-03** 🟢 — MCP server for dnstwist DNS fuzzing to support typosquatting, phishing, and lookalike-domain analysis. *(★ 51 · updated 2025-03-03)*
* **[Volatility-MCP-Server](https://github.com/bornpresident/Volatility-MCP-Server) ⭐ 39 | 🐛 3 | 🌐 Python | 📅 2025-07-07** 🟢 — MCP exposing Volatility 3 plugins for natural-language memory forensics. *(★ 39 · updated 2025-07-07)*
  * **Related:** [MemoryInvestigator](https://github.com/jan-hendrik-lang/MemoryInvestigator) ⭐ 13 | 🐛 0 | 🌐 Python | 📅 2025-09-16
* **[PhishLLM](https://github.com/code-philia/PhishLLM) ⭐ 39 | 🐛 0 | 🌐 Python | 📅 2026-06-04** 🔬⚠️ — Reference-less phishing detection via LLM brand recognition (USENIX'24). *(★ 39 · updated 2026-06-04)*
  * **Related:** [PhishVLM](https://github.com/code-philia/PhishVLM) ⭐ 39 | 🐛 0 | 🌐 Python | 📅 2026-06-04
* **[MemoryInvestigator](https://github.com/jan-hendrik-lang/MemoryInvestigator) ⭐ 13 | 🐛 0 | 🌐 Python | 📅 2025-09-16** 🔬 — Volatility 3 + LLM + RAG for memory-forensic triage. *(★ 13 · updated 2025-09-16)*
  * **Related:** [Volatility-MCP-Server](https://github.com/bornpresident/Volatility-MCP-Server) ⭐ 39 | 🐛 3 | 🌐 Python | 📅 2025-07-07

***

## Related Awesome Lists

* **[awesome-threat-intelligence](https://github.com/hslatman/awesome-threat-intelligence) ⭐ 10,538 | 🐛 116 | 📅 2026-05-31** — Classic CTI list (pairs with the AI-CTI section). *(★ 10,538 · updated 2026-05-31)*
* **[awesome-ml-for-cybersecurity](https://github.com/jivoi/awesome-ml-for-cybersecurity) ⭐ 9,286 | 🐛 33 | 📅 2024-08-19** — Large classic list of machine-learning-for-cybersecurity resources (stale-ish but still useful). *(★ 9,285 · updated 2024-04-11)*
* **[awesome-threat-modelling](https://github.com/hysnsec/awesome-threat-modelling) ⭐ 1,793 | 🐛 23 | 🌐 Dockerfile | 📅 2024-08-02** — General-purpose threat modeling list — methodologies and non-AI tools (Threat Dragon, pytm, Threagile); dormant since 2023 but a solid reference. *(★ 1,793 · updated 2023-07-15)*
* **[Awesome-LLM4Cybersecurity](https://github.com/tmylla/Awesome-LLM4Cybersecurity) ⭐ 1,747 | 🐛 3 | 🌐 JavaScript | 📅 2026-07-08** — 600+ papers on LLMs for cybersecurity. *(★ 1,746 · updated 2026-07-08)*
* **[awesome-llm-security](https://github.com/corca-ai/awesome-llm-security) ⭐ 1,683 | 🐛 184 | 📅 2025-08-20** — Securing LLMs. *(★ 1,683 · updated 2025-08-20)*
* **[awesome-ai-security](https://github.com/ottosulin/awesome-ai-security) ⭐ 1,389 | 🐛 139 | 📅 2026-08-16** — AI security resources. *(★ 1,386 · updated 2026-08-16)*
* **[Awesome-LLMs-for-Vulnerability-Detection](https://github.com/huhusmang/Awesome-LLMs-for-Vulnerability-Detection) ⭐ 1,238 | 🐛 4 | 🌐 Python | 📅 2026-08-16** — Focused, continuously updated index of LLM-based software-vulnerability detection research across function, repository, agentic, and smart-contract analysis, including datasets, benchmarks, and surveys. *(★ 1,237 · updated 2026-08-16)*
* **[Awesome-AI-Security](https://github.com/TalEliyahu/Awesome-AI-Security) ⭐ 853 | 🐛 15 | 📅 2026-07-18** — AI security resources. *(★ 853 · updated 2026-07-18)*
* **[awesome-mcp-security](https://github.com/Puliczek/awesome-mcp-security) ⭐ 728 | 🐛 161 | 📅 2026-03-03** — MCP security resources, tools, writeups, and server/client risk references. *(★ 728 · updated 2026-03-03)*
* **[awesome-gpt-security](https://github.com/cckuailong/awesome-gpt-security) ⭐ 668 | 🐛 23 | 📅 2026-07-24** — GPT/LLM security tools and cases. *(★ 668 · updated 2026-07-24)*
* **[awesome-ml-privacy-attacks](https://github.com/stratosphereips/awesome-ml-privacy-attacks) ⭐ 640 | 🐛 1 | 📅 2024-03-18** — Machine-learning privacy-attack papers and resources. *(★ 640 · updated 2024-03-18)*
* **[awesome-cybersecurity-agentic-ai](https://github.com/raphabot/awesome-cybersecurity-agentic-ai) ⭐ 536 | 🐛 10 | 🌐 Shell | 📅 2026-06-28** — Agentic-AI cybersecurity tools and security MCP servers. *(★ 536 · updated 2026-06-28)*
* **[awesome-llm-cybersecurity-tools](https://github.com/tenable/awesome-llm-cybersecurity-tools) ⚠️ Archived** — Tenable's list (archived but a strong reference). *(★ 488 · updated 2024-04-08)*
* **[awesome-MLSecOps](https://github.com/RiccardoBiosas/awesome-MLSecOps) ⭐ 450 | 🐛 14 | 🌐 Astro | 📅 2026-08-15** — Curated MLSecOps resources spanning adversarial ML, LLM security, AI red teaming, model scanning, supply-chain protection, and MLOps pipeline security. *(★ 450 · updated 2026-08-15)*
* **[Awesome-Offensive-AI-Agentic-Landscape](https://github.com/Yeti-791/Awesome-Offensive-AI-Agentic-Landscape) ⭐ 212 | 🐛 0 | 📅 2026-07-20** — Offensive AI-agent landscape covering open-source pentest/red-team agents, offensive/security-specialized models, papers, benchmarks, and commercial tools. *(★ 211 · updated 2026-07-20)*
* **[awesome-ml-security](https://github.com/trailofbits/awesome-ml-security) ⭐ 170 | 🐛 6 | 📅 2026-02-06** — Trail of Bits' curated machine-learning security resources. *(★ 170 · updated 2026-02-06)*
* **[awesome-ai-cybersecurity](https://github.com/ElNiak/awesome-ai-cybersecurity) ⭐ 151 | 🐛 4 | 📅 2026-08-13** — Broad AI-for-security collection. *(★ 151 · updated 2026-08-13)*
* **[Awesome-AI-For-Security](https://github.com/AmanPriyanshu/Awesome-AI-For-Security) ⭐ 146 | 🐛 2 | 📅 2026-08-13** — AI-for-security tools, papers, and datasets. *(★ 146 · updated 2026-08-13)*
* **[open-source-llm-scanners](https://github.com/psiinon/open-source-llm-scanners) ⭐ 109 | 🐛 3 | 📅 2026-02-05** — Open-source LLM scanners and testing tools. *(★ 109 · updated 2026-02-05)*
* **[awesome-ai-agent-attacks](https://github.com/webpro255/awesome-ai-agent-attacks) ⭐ 65 | 🐛 0 | 📅 2026-08-11** — Sourced timeline of real AI-agent security incidents, breaches, vulnerabilities, and attack techniques. *(★ 65 · updated 2026-08-11)*
* **[awesome-ai-guardrails](https://github.com/enguard-ai/awesome-ai-guardrails) ⭐ 64 | 🐛 1 | 🌐 Python | 📅 2026-07-30** — Catalog of AI guardrail models, tools, organizations, datasets, and papers, with useful Hugging Face model coverage. *(★ 64 · updated 2026-07-30)*
* **[awesome-ai-agents-security](https://github.com/ProjectRecon/awesome-ai-agents-security) ⭐ 63 | 🐛 64 | 📅 2026-06-12** — Focused map of AI-agent security resources across runtime protection, red-teaming scanners, static analysis, sandboxing, guardrails, benchmarks, and identity. *(★ 63 · updated 2026-06-12)*
* **[awesome-genai-cyberhub](https://github.com/Ashfaaq98/awesome-genai-cyberhub) ⭐ 54 | 🐛 0 | 📅 2026-08-07** — GenAI-driven cybersecurity resources. *(★ 54 · updated 2026-08-07)*
* **[awesome-ai-security](https://github.com/gmh5225/awesome-ai-security) ⭐ 39 | 🐛 0 | 📅 2026-08-16** — For pentesters, bug hunters, and researchers. *(★ 39 · updated 2026-08-10)*
* **[Awesome-AI4DevSecOps](https://github.com/awsm-research/Awesome-AI4DevSecOps) ⭐ 19 | 🐛 0 | 📅 2025-07-02** — Taxonomy of AI-driven security solutions for DevSecOps. *(★ 19 · updated 2025-07-02)*
* **[AI Security Repository Radar](https://github.com/Zero0x00/Ai-Security-radar-) ⭐ 5 | 🐛 0 | 📅 2026-08-16** — Daily-updated AI/LLM/MCP/RAG security repository radar with category, license, stars, and quality/relevance metadata. *(★ 5 · updated 2026-08-16)*

***

## Contributing

Contributions are welcome! This README is generated from structured data.

1. Edit `data/sections.json` (validated by `data/schema.json`).
2. Use structured fields such as `status`, `flags`, and `license`; do not paste rendered emoji tags into the data.
3. Regenerate and check the README:

```bash
python3 scripts/update_github_metrics.py
python3 gen_readme.py
python3 gen_readme.py --check
```

Example entry:

```json
{
  "name": "ExampleTool",
  "repo": "OWNER/REPO",
  "status": ["open_source"],
  "license": "MIT",
  "flags": ["early_stage"],
  "desc": "One factual sentence about what the tool does.",
  "related": [
    {"label": "Sibling tool", "url": "https://github.com/OWNER/SIBLING"}
  ]
}
```

Status values: `open_source`, `research`, `commercial_open`. Common flags: `license_caveat`, `early_stage`, `archived`, `heavy_runtime`, `requires_api_key`, `authorized_testing_only`, `commercial_features`, `no_license`, `noncommercial`, `copyleft`, `abliterated_or_uncensored`.

Guidelines: link the canonical upstream repo (not a fork); verify the URL resolves; tag the correct type and add a caveat flag/note for non-permissive, non-commercial, unclear, missing, or restrictive licenses; prefer real, installable projects over blog-only references.

For Hugging Face model entries, include the model id, license, access status (open/gated), and artifact formats (for example Safetensors or ONNX).

## Contact

Maintained by **Sergey Gordeychik** — <scadastrangelove@gmail.com> · [blog](https://scadastrangelove.blogspot.com/) · [@scadasl](https://x.com/scadasl).

## License

To the extent possible under law, the contributors have waived all copyright and related rights to this list ([CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/)). Linked projects retain their own licenses — check each before use.

***

> _Enhansomed by [enhansome](https://github.com/enhansome) on 2026-08-16._
