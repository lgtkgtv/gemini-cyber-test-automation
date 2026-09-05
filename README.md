# 🛡️ AI Cyber Academy: Dual-Track Cybersecurity Automation with Google Gemini

A comprehensive, two-tier cybersecurity engineering and defense automation curriculum leveraging the modern Google GenAI SDK (`google-genai`) and Gemini reasoning models (`gemini-3.8-flash`, `gemini-2.5-flash`, and `gemini-2.5-pro`).

---

## 🗺️ Dual-Track Curriculum Architecture

To serve diverse learning goals, the repository is partitioned into two dedicated learning tracks:

```text
cyber-test-automation/
├── junior_track/                          <-- Track 1: Ages 12+ / Beginners / Visual Learners
│   ├── README.md                          <-- Junior track guide & mission syllabus
│   ├── 1_vulnerability_discovery_junior.ipynb
│   └── 2_stateful_defense_analyst_junior.ipynb
│
├── engineering_track/                     <-- Track 2: Ages 18+ / CS Undergrads / DevSecOps & CTF
│   ├── README.md                          <-- Systems & compiler engineering syllabus
│   ├── 1_vulnerability_discovery_engineer.ipynb
│   └── 2_stateful_defense_analyst_engineer.ipynb
│
├── .env.example                           <-- API key configuration template
├── pyproject.toml                         <-- Project dependencies managed with uv
└── README.md                              <-- Master repository landing page
```

---

## 📊 Track Comparison Matrix

| Dimension | 🧒 [Junior Track](./junior_track/) | 🛡️ [Engineering Track](./engineering_track/) |
| :--- | :--- | :--- |
| **Target Audience** | Ages 12–17, coding beginners, educators, STEM clubs | College CS students, AppSec engineers, CTF competitors, security researchers |
| **Prerequisites** | Curiosity, basic logic, introductory Python | Systems programming, compiler basics, Python 3.12+, relational databases, networking |
| **Core Metaphors** | *The Broken Lock*, *Bob the Sneaky Hacker*, *The Robot Butler*, *The Magic Password Trick* | *Von Neumann Instruction Blending*, *Lexer AST Tokenization*, *CPU Privilege Rings vs. Transformer Attention Space* |
| **Interactive Labs** | Gamified multiple-choice radio button attack challenges & puzzle solvers | Interactive CTF Triage Console with raw SQL inspection & live VDBE execution, interactive Red-Team workbench |
| **Contract Validation** | Simple structured fields | Strict Pydantic v2 schemas (`DevSecOpsRemediationReport`) with CVSS v3.1 Base Scores, CVSS Vectors, and MITRE CWE links |
| **AST & Diff Gates** | Visual line-by-line diffs | `ast.parse()` static compilation verification + line-level unified diffs (`difflib.unified_diff`) |
| **Verification Harness** | Dynamic test verifying bad password fails & good password passes | Closed-loop dynamic verification harness in ephemeral SQLite sandbox asserting exploit neutralization and functional non-regression |
| **Vulnerability Breadth** | SQL Injection + Multi-Class demo | In-depth audit suite covering CWE-89, CWE-22 (Path Traversal), CWE-78 (Command Injection), CWE-918 (SSRF), CWE-502 (Insecure Deserialization) |
| **SOC & Defense Scope** | Detective story, catching burglars across a 3-step timeline | Multi-turn SIEM APT correlation, token memory inspection, RFC 5424 / ECS log normalization, autonomous SOAR tool calling |
| **Adversarial Red Teaming** | Trick the Robot Butler | OWASP Top 10 for LLMs: Direct Jailbreak (LLM01), Log/RAG Poisoning (LLM01/02), Stored XSS (LLM02), Excessive Agency (LLM06) |
| **Autonomous SOAR** | AI guard triggering emergency locks | Gemini Tool Calling (`query_threat_intel`, `isolate_compromised_host`, `apply_firewall_drop_rule`) with automated incident resolution |

---

## 🧭 Curriculum Tracks

### 🧒 Track 1: Junior Academy (Ages 12+)
* **Folder:** [`junior_track/`](./junior_track/)
* **Mission 1:** [`1_vulnerability_discovery_junior.ipynb`](./junior_track/1_vulnerability_discovery_junior.ipynb) — **Level 1: The Code Doctor (Finding & Healing Broken Locks)**
  * *Story:* Discovering the broken lock on the high-score vault.
  * *Puzzle:* Interactive multiple-choice challenge proving how `' OR '1'='1` tricks databases.
  * *Heal:* Placing user words in an *unbreakable glass envelope* (`?`).
  * *Blast Chamber:* Verifying the fix blocked the attack and kept normal logins working.
* **Mission 2:** [`2_stateful_defense_analyst_junior.ipynb`](./junior_track/2_stateful_defense_analyst_junior.ipynb) — **Level 2: The AI Security Guard (Catching Burglars & Base Lockdown)**
  * *Story:* Catching the three-step burglar across time.
  * *Puzzle:* The AI Trickster challenge—can you trick the AI guard with fake orders?
  * *Lockdown:* Autonomous SOAR response isolating bad actors automatically.

---

### 🛡️ Track 2: Engineering Track (Ages 18+ / CS & Security)
* **Folder:** [`engineering_track/`](./engineering_track/)
* **Lab 1:** [`1_vulnerability_discovery_engineer.ipynb`](./engineering_track/1_vulnerability_discovery_engineer.ipynb) — **Autonomous Vulnerability Discovery & Verification Engine**
  * *Systems Mechanics:* SQL query compilation pipeline (Tokenizer → Lemon LALR(1) Parser → AST → VDBE Bytecode).
  * *CTF Triage Console:* Evaluating Tautologies, Comment Truncation (`--`), UNION injections, and Blind Probes.
  * *Type-Safe Contracts:* Pydantic v2 schemas with CVSS v3.1 vector strings and CWE taxonomy mappings.
  * *Static & Dynamic Gates:* Pre-execution AST validation (`ast.parse()`), unified diffs, and closed-loop sandbox verification in SQLite.
  * *DevSecOps Suite:* Automated batch audit covering CWE-22, CWE-78, CWE-918, and CWE-502.
* **Lab 2:** [`2_stateful_defense_analyst_engineer.ipynb`](./engineering_track/2_stateful_defense_analyst_engineer.ipynb) — **Stateful SOC Analyst & Adversarial Red Teaming**
  * *Systems Theory:* The LLM Security Paradox—Hardware Privilege Rings (x86 Ring 0 vs. Ring 3 / MMU) vs. Transformer Softmax Attention in a unified embedding space ($E \in \mathbb{R}^{\text{vocab} \times d_{\text{model}}}$).
  * *Kill Chain Correlation:* Correlating Nmap sweeps, web exploit probes, and SSH brute-force spikes.
  * *Adversarial Red Teaming:* Live testing against OWASP Top 10 for LLMs (Direct Jailbreaks, Indirect Log Poisoning, Stored XSS, Excessive Agency).
  * *Enterprise Schemas:* Normalizing raw logs into Elastic Common Schema (ECS v8.x) JSON-LD objects.
  * *Autonomous SOAR:* Native Python tool calling (`query_threat_intel`, `isolate_compromised_host`, `apply_firewall_drop_rule`) with closed-loop incident containment.

---

## 🏷️ Industry Standards & Taxonomy Mapping

| Framework | Identifier | Description | Covered In |
| :--- | :--- | :--- | :--- |
| **MITRE CWE** | [`CWE-89`](https://cwe.mitre.org/data/definitions/89.html) | Improper Neutralization of Special Elements in SQL Command (SQLi) | Track 1 & Track 2 (Lab 1) |
| **MITRE CWE** | [`CWE-22`](https://cwe.mitre.org/data/definitions/22.html) | Improper Limitation of a Pathname to a Restricted Directory (Path Traversal) | Track 1 & Track 2 (Lab 1) |
| **MITRE CWE** | [`CWE-78`](https://cwe.mitre.org/data/definitions/78.html) | OS Command Injection | Track 1 & Track 2 (Lab 1) |
| **MITRE CWE** | [`CWE-918`](https://cwe.mitre.org/data/definitions/918.html) | Server-Side Request Forgery (SSRF) | Track 1 & Track 2 (Lab 1) |
| **MITRE CWE** | [`CWE-502`](https://cwe.mitre.org/data/definitions/502.html) | Deserialization of Untrusted Data | Track 1 & Track 2 (Lab 1) |
| **OWASP LLM** | `LLM01` | Prompt Injection (Direct & Indirect) | Track 1 & Track 2 (Lab 2) |
| **OWASP LLM** | `LLM02` | Insecure Output Handling (Reflected/Stored XSS) | Track 1 & Track 2 (Lab 2) |
| **OWASP LLM** | `LLM06` | Excessive Agency & Autonomous Tool Abuse | Track 2 (Lab 2) |
| **MITRE ATT&CK** | `T1595` / `T1190` / `T1110` | Active Scanning, Exploit Public-Facing App, Brute Force | Track 1 & Track 2 (Lab 2) |
| **SIEM Schemas** | `ECS v8.x` / `RFC 5424` | Elastic Common Schema & Structured Syslog Normalization | Track 2 (Lab 2) |

---

## ⚡ Technical Benchmarks (Gemini Cyber Capabilities)

Gemini reasoning models replace pattern-matching static analysis with contextual, multi-step agentic reasoning:

| Metric / Benchmark | Gemini 3.8 Flash Cyber | Industry Standard / Competitors |
| :--- | :--- | :--- |
| **Vulnerability Discovery** | **>70%** (across 20 languages) | Highly variable across models |
| **CyberGym Overall Score** | **86.2%** | ~83.8% (Anthropic Opus 5) |
| **CWE-Bench Patching Rate** | **47.2%** | Limited autonomous remediation |
| **Chrome Security Patching** | **2.6x more correct patches** | Standard large language models |
| **Inference Latency** | Optimized for fast agentic tool-calling loops | High latency on frontier models |

---

## 🚀 Quick Start Guide

### 1. Prerequisites
- Python 3.12+
- [`uv`](https://docs.astral.sh/uv/) (Extremely fast Python package manager)
- A Google Gemini API Key (obtain from [Google AI Studio](https://aistudio.google.com/))

### 2. Installation & Environment
```bash
# Clone the repository and navigate into it
cd cyber-test-automation

# Synchronize virtual environment and dependencies using uv
uv sync

# Configure your Google Gemini API key
cp .env.example .env
# Edit .env to set GEMINI_API_KEY=your-key-here
```

### 3. Launching the Lab
```bash
# Launch Jupyter Notebook
uv run jupyter notebook
```

From the Jupyter file explorer:
- Open [`junior_track/`](./junior_track/) for the intuitive, gamified **Junior Academy Track**.
- Open [`engineering_track/`](./engineering_track/) for the deep systems, compiler, and CTF **Engineering Track**.

### 💡 Model Selection & Free-Tier Quota Notice
Every notebook includes an interactive **Dynamic Model Selector** dropdown:
- **`gemini-3.8-flash` (Default):** Frontier cyber reasoning and tool calling.
- **`gemini-2.5-flash` (Fallback):** High-throughput, generous free-tier quotas. If you encounter a `429 RESOURCE_EXHAUSTED` error on free-tier limits, switch the dropdown to `gemini-2.5-flash`.
- **`gemini-2.5-pro`:** Deep multi-step reasoning for complex exploitation and architectural analysis.
