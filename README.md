# AI Failure Playbook — Recovery Edition ⚡

A practical recovery guide for software engineers — **15 expert-written prompts** to fix and recover from the most common AI/LLM failure modes.

This project is packaged as a lightweight, interactive, single-page web application. It serves as an offline-first tool for developers to quickly diagnose unexpected LLM behaviors, copy targeted recovery prompts, and apply prevention strategies in their daily engineering workflows.

---

## 🔍 Why AI Fails (Root Causes)

The playbook identifies **6 core reasons** behind common AI failure modes:

1. **No Grounding**: The model invents facts when the necessary context is missing.
2. **Instruction Distance**: Rules placed at the beginning of a long prompt are ignored (recency bias).
3. **Context Decay**: The model loses track of constraints after 8+ turns in a single conversation.
4. **Format Ambiguity**: Vague requests like *"be concise"* lead to erratic formatting.
5. **Task Blending**: Requesting multiple tasks in a single message leads to blended, confused outputs.
6. **Confidence Blindness**: The model sounds highly authoritative even when guessing or fabricating info.

---

## 🛠️ The 15 Recovery Scenarios

The playbook catalogs **15 specific failure modes** split across **6 categories**:

| # | Scenario | Category | Diagnostic / Symptoms |
|---|---|---|---|
| **01** | **Model Hallucinating Facts** | `Hallucination` | Fabricates APIs, fake documentation, incorrect version numbers, or dates. |
| **02** | **Output Truncated Mid-Way** | `Output` | Stops generating response mid-sentence or mid-file with `...` or silence. |
| **03** | **Model Ignoring Instructions** | `Reliability` | Acknowledges constraints then ignores them (e.g. outputs prose instead of requested format). |
| **04** | **Inconsistent Output Across Runs** | `Reliability` | Same prompt yields different schemas or naming styles across runs, breaking parser code. |
| **05** | **Model Refuses Valid Request** | `Refusal` | Refuses legitimate engineering tasks like security research, penetration testing, or debugging. |
| **06** | **Context Window / Model Forgets** | `Context` | Loses original constraints, style guides, or design decisions in long conversations. |
| **07** | **Model Loops / Repeats Itself** | `Output` | Circles back to previous points, repeating prior content without producing new value. |
| **08** | **Wrong Output Format Returned** | `Output` | Returns bullet points instead of JSON, or prose instead of a table. |
| **09** | **Model Loses Thread** | `Context` | Contradicts or forgets a decision made 3+ turns ago during multi-turn chats. |
| **10** | **Few-Shot Examples Backfiring** | `Reliability` | Over-indexes on examples, copying their literal variable names and quirks instead of the logic. |
| **11** | **Chain-of-Thought (CoT) Failure** | `Hallucination` | Build-up of incorrect assumptions leads to a highly plausible but wrong conclusion. |
| **12** | **No Uncertainty Signaling** | `Hallucination` | Outputs guesses and facts with the exact same level of high confidence. |
| **13** | **Model Merges Multiple Tasks** | `Context` | Blends distinct requirements or applies Task A's rules to Task B. |
| **14** | **Verbose / Padded Response** | `Output` | Piles on preambles, recaps, and fluff when you need only the raw value or code snippet. |
| **15** | **Prompt Injection in Input** | `Injection` | Untrusted user data contains instructions that hijack/override system commands. |

---

## ✨ Features

- **Interactive Search**: Search across failure descriptions, categories, keywords, and tags in real time.
- **Categorized Filters**: Click on categories (`Hallucination`, `Output`, `Context`, `Refusal`, `Reliability`, `Injection`) to filter cards instantly.
- **One-Click Copy**: Copy recovery prompts directly to your clipboard using the built-in copy buttons.
- **Diagnosis & Pro-Tips**: Every card outlines *"What Went Wrong"*, the desired *"Output Shape"*, and a *"Prevention Tip"* to stop it from happening again.
- **Sleek Dark Mode**: Responsive, premium dark UI designed with HSL-tailored colors, subtle animations, and zero page load delay.

---

## 🚀 How to Use

The application is completely self-contained and requires **no installation, build steps, or local servers**.

1. Clone this repository (or download `index.html`):
   ```bash
   git clone <your-repo-url>
   ```
2. Open `index.html` directly in your favorite web browser (Chrome, Firefox, Safari, Edge):
   - Double-click the file, or run:
     ```bash
     # macOS/Linux
     open index.html
     
     # Windows
     start index.html
     ```
3. Use the search bar or tags to find your failure mode, copy the recovery prompt, replace any `{{PLACEHOLDERS}}` with your context, and paste it back into your LLM conversation.

---

## 📦 Project Structure

```text
.
├── .gitignore         # Ignores local editor configurations and system files
├── index.html         # The complete interactive playbook (HTML, CSS, JS)
└── README.md          # Project documentation (this file)
```

---

## 🤝 Contributing

Contributions are welcome! If you have a recovery prompt that works consistently, or a new failure mode that needs listing:

1. Fork the repository.
2. Edit `index.html` to add a new card template inside the `#cards` container.
3. Submit a Pull Request.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
