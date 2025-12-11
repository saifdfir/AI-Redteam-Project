# 🛡️ AI Red Teaming: Prompt Injection & Safety Evaluation

<p align="center">
  <img src="https://img.shields.io/badge/AI-Red_Teaming-red" />
  <img src="https://img.shields.io/badge/LLM-Security-orange" />
  <img src="https://img.shields.io/badge/Prompt-Injection-yellow" />
</p>

> **Adversarial testing of a local LLM to analyze safety, robustness, and misuse potential.**

---

## 📌 Project Overview
This project evaluates how a local Large Language Model (LLM) responds to **prompt injection attacks**, attempts to bypass content filters, and adversarial manipulation.

The goal is to demonstrate practical skills in **AI Red Teaming**, **prompt engineering techniques**, and **safety alignment analysis**. All testing was performed on an offline local model for research and learning purposes.

---

## 🎯 Objectives
- 🔍 **Identify weaknesses** in LLM instruction-following hierarchies.
- 🔓 **Test safety guidelines** against Jailbreak and Roleplay attacks.
- 🤖 **Analyze responses** for hallucinations and unsafe compliance.
- 🗣️ **Evaluate multi-turn manipulation** capabilities.
- 📝 **Document threats** and real-world misuse potential.
- 🛡️ **Recommend mitigations** to improve model safety.

---

## 🧰 Tools & Environment

| Component | Details |
|-----------|---------|
| **Model Tested** | Mistral 7B (Local / Quantized) |
| **Inference Tool** | LM Studio |
| **System** | Windows Host (Local Environment) |
| **Techniques** | Prompt Injection, Jailbreaking, Roleplay, Indirect Injection |

---

## 🔍 Attack Categories Tested

### 1️⃣ Basic Prompt Injection
Commands like *“Ignore all previous instructions…”* or *“Repeat this text verbatim.”*
* **Measured:** Safety bypass success rate, internal instruction leakage.

### 2️⃣ Jailbreak / Roleplay Attacks
Prompts granting the model an unrestricted persona (e.g., DAN mode, Dev Mode, Hypothetical Scenarios).
* **Measured:** Collapse of safety boundaries under roleplay framing.

### 3️⃣ Multi-turn Manipulation
Gradual boundary-pushing across several messages to wear down refusals (the "Frog in boiling water" technique).
* **Measured:** Susceptibility to emotional manipulation or context fatigue.

### 4️⃣ Indirect Prompt Injection
Malicious instructions hidden inside user-provided text chunks to trigger unintended actions.
* **Measured:** Whether the model executes hidden vs. explicit prompts.

### 5️⃣ Harmful Content Pressure Testing
Requests for disallowed or risky outputs within a "research" or "educational" context.
* **Measured:** Consistency of refusal when asked **directly** versus **indirectly**.

---

## 🧪 Results Summary

| Test Type | Outcome | Notes |
|-----------|:-------:|-------|
| **Basic Injection** | 🟡 Partial Success | Some refusals bypassed; system prompts leaked. |
| **Jailbreak Attempts** | 🔴 High Success | Safety alignment collapsed during roleplay scenarios. |
| **Multi-turn Manipulation** | 🟡 Moderate Success | Boundaries eroded slowly over 5+ turns. |
| **Indirect Injection** | 🟢 Mostly Blocked | Model successfully ignored most embedded malicious text. |
| **Harmful Content** | 🟢 Strong Refusal | **Direct** requests for malware/hate speech were blocked. |

---

## ⚠️ Risk Assessment

- **Jailbreakability:** `High` (Susceptible to persona-based attacks)
- **Hallucination Risk:** `Medium`
- **Manipulation Susceptibility:** `Medium`
- **Potential Impact:** Generation of misinformation, assistance in social engineering, bypass of safety guardrails.

---

## 🛡 Recommended Mitigations
Based on the findings, the following defenses are recommended:

1.  **Reinforce Instruction Hierarchy:** Clearly separate "System" instructions from "User" data using delimiters (e.g., XML tagging).
2.  **Strengthen Refusal Patterns:** Fine-tune the model against common jailbreak templates (DAN, etc.).
3.  **Sanitize User Input:** Filter for indirect injection markers before passing data to the context window.
4.  **Limit Roleplay Depth:** Add system-side guardrails to detect persona-based drift.

---

## 📁 Repository Structure

```text
AI-RedTeam-LLM-Testing/
│
├── screenshots/
│   ├── basic-injection.png
│   ├── jailbreak-success.png
│   ├── indirect-injection.png
│   ├── refusal-correct.png
│   └── analysis-notes.png
│
└── README.md
````

-----

## 🧭 What This Project Demonstrates

  - ✅ Understanding of **LLM vulnerabilities** (OWASP Top 10 for LLMs).
  - ✅ Ability to simulate an **attacker mindset** (Red Teaming).
  - ✅ Structured **safety evaluation workflow**.
  - ✅ Documentation similar to a **real security assessment**.

-----

## 📬 Contact

  - *📧 Email:* [saifcyb@gmail.com](mailto:saifcyb@gmail.com)
  - *🔗 Portfolio:* [saifdfir.github.io/portfolio](https://saifdfir.github.io/portfolio/)
  - *🔗 LinkedIn:* [Mohammed Saif Ul Islam](https://linkedin.com/in/mohammed-saif-ul-islam-85a68639a)

-----

### ⚖️ Disclaimer

*This project is for educational and research purposes only. The testing was conducted on a locally hosted model in a controlled environment. No public services were harmed or violated.*
