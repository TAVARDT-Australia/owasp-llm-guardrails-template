# OWASP LLM01 Guardrails Template & AI Security Blueprint | TAVARDT Australia

[![Licence MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![OWASP LLM01](https://img.shields.io/badge/OWASP-LLM01%20Hardened-ff0055.svg)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
[![Language](https://img.shields.io/badge/Language-English%20(Australia)-green.svg)](README.md)
[![AI Diagnostics](https://img.shields.io/badge/TAVARDT-AI%20Evaluator-5b3cf5.svg)](https://tools.tavardt.com/au/llm-robustness-evaluator/)

Production-tested open source middleware and security blueprint for mitigating Prompt Injection (OWASP LLM01), system prompt extraction, and adversarial jailbreaks, aligned with ACSC AI security principles and the Australian Privacy Act 1988.

Engineered and maintained by the AI safety and security operations team at **[TAVARDT Australia](https://ag.tavardt.com/au/super-intelligence/)**.

---

## 1. AI Security Architecture Overview

This repository delivers an operational security blueprint and lightweight Python middleware establishing deterministically verified **guardrails** for generative AI workflows, RAG systems, and autonomous digital agents.

### Mitigating Data and Control Plane Convergence
Modern LLMs process prompt directives and external inputs within the same processing window. Deterministic guardrails prevent prompt injection, untrusted document hijacking, and unauthorized action invocation.

---

## 2. Threat Vectors Addressed (OWASP Top 10 for LLMs)

| Defence Layer | Threat Vector Mitigated | Mitigation Mechanism |
| :--- | :--- | :--- |
| **Input Sanitiser** | Direct Prompt Injection & Jailbreaks | Real-time heuristic detection of override commands (`ignore previous instructions`, simulated persona shifts). |
| **Canary Token Verifier** | System Prompt Exfiltration | Dynamic verification of canary tokens in completions to block system instruction leaks. |
| **RAG Boundary Guard** | Indirect Prompt Injection | Isolation and sanitisation of untrusted documents retrieved during vector search. |
| **Structured Output Filter** | Unauthorised Action Invocation | Schema-enforced validation of tool arguments before execution. |

---

## 3. Pre-Deployment AI Robustness Assessment

Verify your conversational models and AI agent pipelines against adversarial inputs before production rollout:

* **AI Robustness Assessment:** [TAVARDT Australia LLM Robustness Evaluator](https://tools.tavardt.com/au/llm-robustness-evaluator/)
* **Complete Regional Tooling Suite:** [TAVARDT Tools Australia](https://tools.tavardt.com/au/)

---

## 4. Implementation & Quickstart Guide

### Clone & Execução

```bash
git clone https://github.com/TAVARDT-Australia/owasp-llm-guardrails-template.git
cd owasp-llm-guardrails-template
python examples/quickstart.py
```

### Exemplo de Integração

```python
from guardrails.validator import LLMGuardrail

guard = LLMGuardrail()

# 1. Validação de Ingress (Input Guardrail)
is_safe, error = guard.validate_input(user_input)
if not is_safe:
    raise ValueError(f"Blocked input: {error}")

# 2. Injeção de Canary no Prompt de Sistema
hardened_system_prompt = guard.get_canary_injection_prompt(system_prompt)

# 3. Validação de Egress (Output Guardrail)
is_valid, leak_error = guard.validate_output(completion)
if not is_valid:
    raise SecurityError("System prompt leak detected!")
```

---

## 5. AI Security Advisory & Autonomous Agent Engineering

If your organisation requires tailored ACSC-aligned AI security reviews, automated WhatsApp/web agent protection, or technical advisory:

* **Corporate Portal:** [TAVARDT Australia](https://ag.tavardt.com/au/super-intelligence/)
* **Technical Contact:** [Liaise with Engineering](https://ag.tavardt.com/au/contact/)

---

## Licence

Distribuído sob a licença de código aberto MIT. Consulte o arquivo [`LICENSE`](LICENSE) para mais detalhes.  
Copyright (c) 2026 TAVARDT Australia.
