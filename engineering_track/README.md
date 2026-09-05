# 🛡️ Engineering Track: Autonomous AppSec & Defense Automation (Ages 18+)
### Systems Architecture, Compiler Mechanics, Adversarial ML & Autonomous SOAR

The **Engineering Track** is designed for Computer Science undergraduates, Application Security (AppSec) engineers, CTF competitors, and cybersecurity researchers. It investigates the systems-level mechanisms behind code injection, type-safe API contracts with Pydantic v2, adversarial machine learning vulnerabilities under the OWASP Top 10 for LLMs, and closed-loop autonomous incident response with Gemini tool calling.

---

## 🗺️ Engineering Syllabus

| Notebook | Focus Area | Google Colab | Systems & Security Concepts | Production Engineering Artifacts |
| :--- | :--- | :--- | :--- | :--- |
| [`1_vulnerability_discovery_engineer.ipynb`](./1_vulnerability_discovery_engineer.ipynb) | **Autonomous Vulnerability Discovery & Remediation Engine** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/lgtkgtv/gemini-cyber-test-automation/blob/main/engineering_track/1_vulnerability_discovery_engineer.ipynb) | • SQLite compiler pipeline (Tokenizer → Lemon LALR(1) Parser → AST → VDBE Bytecode)<br>• Von Neumann control-plane vs. data-plane instruction blending<br>• AST boundary preservation via Parameterized Queries (`OP_Variable`)<br>• CTF Triage: Tautologies, Comment Truncation, UNION injections, Blind probes | • Pydantic v2 Contract (`DevSecOpsRemediationReport`) with MITRE CWE & CVSS v3.1 vector strings<br>• Pre-execution AST syntax verification (`ast.parse`)<br>• Unified Diff generation (`difflib.unified_diff`)<br>• Closed-loop dynamic verification in SQLite sandbox<br>• Multi-class enterprise suite (CWE-22, CWE-78, CWE-918, CWE-502) |
| [`2_stateful_defense_analyst_engineer.ipynb`](./2_stateful_defense_analyst_engineer.ipynb) | **Stateful SOC Analyst & Adversarial Red Teaming** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/lgtkgtv/gemini-cyber-test-automation/blob/main/engineering_track/2_stateful_defense_analyst_engineer.ipynb) | • The LLM Security Paradox: CPU Privilege Rings (Ring 0 vs. Ring 3 / MMU isolation) vs. Transformer Softmax Attention in unified embedding spaces<br>• Why Prompt Injection is an inherent mathematical property of self-attention<br>• MITRE ATT&CK Enterprise Matrix mapping (T1595, T1190, T1110, T1071)<br>• Context drift & attention dilution in long-running SOC sessions | • Multi-turn SIEM APT correlation across disparate log feeds<br>• Programmatic memory & token inspection (`chat.get_history()`)<br>• Adversarial Red Teaming workbench (OWASP LLM01, LLM02, LLM06)<br>• Elastic Common Schema (ECS v8.x) log normalizer<br>• Autonomous SOAR Agent with native Python tool calling (`query_threat_intel`, `isolate_compromised_host`, `apply_firewall_drop_rule`) |

--- | :--- | :--- | :--- |
| [`1_vulnerability_discovery_engineer.ipynb`](./1_vulnerability_discovery_engineer.ipynb) | **Autonomous Vulnerability Discovery & Remediation Engine** | • SQLite compiler pipeline (Tokenizer → Lemon LALR(1) Parser → AST → VDBE Bytecode)<br>• Von Neumann control-plane vs. data-plane instruction blending<br>• AST boundary preservation via Parameterized Queries (`OP_Variable`)<br>• CTF Triage: Tautologies, Comment Truncation, UNION injections, Blind probes | • Pydantic v2 Contract (`DevSecOpsRemediationReport`) with MITRE CWE & CVSS v3.1 vector strings<br>• Pre-execution AST syntax verification (`ast.parse`)<br>• Unified Diff generation (`difflib.unified_diff`)<br>• Closed-loop dynamic verification in SQLite sandbox<br>• Multi-class enterprise suite (CWE-22, CWE-78, CWE-918, CWE-502) |
| [`2_stateful_defense_analyst_engineer.ipynb`](./2_stateful_defense_analyst_engineer.ipynb) | **Stateful SOC Analyst & Adversarial Red Teaming** | • The LLM Security Paradox: CPU Privilege Rings (Ring 0 vs. Ring 3 / MMU isolation) vs. Transformer Softmax Attention in unified embedding spaces<br>• Why Prompt Injection is an inherent mathematical property of self-attention<br>• MITRE ATT&CK Enterprise Matrix mapping (T1595, T1190, T1110, T1071)<br>• Context drift & attention dilution in long-running SOC sessions | • Multi-turn SIEM APT correlation across disparate log feeds<br>• Programmatic memory & token inspection (`chat.get_history()`)<br>• Adversarial Red Teaming workbench (OWASP LLM01, LLM02, LLM06)<br>• Elastic Common Schema (ECS v8.x) log normalizer<br>• Autonomous SOAR Agent with native Python tool calling (`query_threat_intel`, `isolate_compromised_host`, `apply_firewall_drop_rule`) |

---

## 🔬 Systems Architecture Deep Dives

### 1. The Parser Boundary & Parameter Binding
```text
Insecure String Interpolation:
Input: "' OR 1=1 --"
Pipeline: [ Raw String ] ──> [ Tokenizer / Lexer ] ──> [ AST Mutated: OR becomes root operator ] ──> Arbitrary Execution

Parameterized Query (Prepared Statement):
Template: "SELECT * FROM users WHERE username = ? AND password_hash = ?"
Pipeline: [ Compiled AST ] ──> [ VDBE Opcode: OP_Variable ] ──> Runtime Data Binding (Registers)
Result: The tokenizer and parser are never re-invoked on user input; AST boundaries remain mathematically invariant.
```

### 2. The LLM Transformer Attention Paradox
```text
Hardware / OS Memory Privilege (Ring 0 vs. Ring 3):
- Operating systems enforce distinct page table privilege bits (Supervisor vs. User).
- Hardware MMU traps non-privileged execution attempts.

Transformer Self-Attention (No Hardware Rings):
- System instructions ("ROLE: SOC Analyst") and untrusted user input ("User-Agent: [SYSTEM OVERRIDE]") are tokenized and mapped to the SAME embedding space: E ∈ R^(vocab x d_model).
- Attention weights Softmax(Q K^T / sqrt(d_k)) allow high-salience attacker tokens to compete with instruction tokens for attention probability mass.
```

---

## 🚀 Quick Start Guide

### 1. Prerequisites
- Python 3.12+
- [`uv`](https://docs.astral.sh/uv/)

### 2. Setup & Execution
```bash
# From repository root:
uv sync

# Configure API Key:
cp .env.example .env
# Set GEMINI_API_KEY=your-key in .env

# Launch Jupyter:
uv run jupyter notebook
```

Navigate into `engineering_track/` and launch **`1_vulnerability_discovery_engineer.ipynb`** or **`2_stateful_defense_analyst_engineer.ipynb`**.
