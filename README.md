# MyLearning_on_LLM

I am consistently learning and building in Generative AI, Agents, and LLMs.  
This repository contains my projects, experiments, and notes on Large Language Models (LLMs).

---

## 📅 Day 1 - Git Learning (Merge vs Rebase) + Environment Setup

Today I learned how Git handles situations where my local branch and the remote branch (GitHub) have different commit histories.

### Problem I Faced

While pushing my code, I encountered a **non-fast-forward error**, which means my local branch was behind the remote branch.

### Root Cause

- GitHub already had some commits (like `README`).
- My local repository had separate commits.
- Git prevents overwriting remote history.

### Solution I Used (Rebase)

```bash
git pull origin main --rebase
```

### What Rebase Does

- Temporarily removes my local commits
- Applies latest changes from GitHub
- Re-applies my commits on top

Before: `A -> B` (GitHub), `A -> C` (Local)  
After: `A -> B -> C'`

### Merge vs Rebase

| Feature  | Merge                | Rebase              |
| -------- | -------------------- | ------------------- |
| History  | Keeps all branches   | Linear history      |
| Commit   | Creates merge commit | No extra commit     |
| Use Case | Team collaboration   | Clean local history |

### Key Learnings

- Always sync before pushing:

```bash
git pull origin main --rebase
```

- Rebase creates a clean commit history.
- Avoid rebasing shared/public commits.
- Non-fast-forward errors happen when histories diverge.

### Final Workflow I Will Follow

```bash
git add .
git commit -m "message"
git pull origin main --rebase
git push
```

### Outcome

Successfully pushed my local project to GitHub after resolving history conflicts using rebase.

---

## 📅 Day 2 - Setting Up the Environment for LLM Learning

Today I set up my environment for learning LLMs and Agents using:

- Groq API key
- Gemini API key

I also learned to troubleshoot model/API errors such as:

- `404 Not Found` (wrong or unsupported model name)
- `429 Resource Exhausted` (quota/billing limit)
 created a manual calclator tool and make a small agent with that tool basic agent understanding
---

## 📅 Day 3 - Exploring OpenAI SDK

- Implemented OpenAI Agents SDK basics using `Agent`, `Runner.run`, and `async/await`.
- Learned that `trace()` is optional and mainly used for observability/debugging.
- Understood tool usage in agents:
  - Custom function tools
  - Platform-dependent built-in tools
- Created and used a built-in tool in practice.

