# 🧠 Multi-Expert AI Panel
### Ask once. Get three expert perspectives. One clear answer.

> **Built by Nagabandi Swathvika** — B.Tech CSE, 1st Year, KITSW Warangal  
> Independent project · No team · No mentor · Built from scratch using the Anthropic Claude API

---

## 🎯 What This Is

A structured AI panel system where a user submits **one question** and receives responses from **three domain-expert AI personas** — each analysing the problem from a completely different angle. A **Moderator AI** then reads all three responses and synthesises them into **one clear, actionable recommendation**.

This is not a chatbot. It is an orchestration layer over Claude that simulates the experience of having a panel of real human experts debate your problem before giving you a unified answer.

---

## 💡 The Problem It Solves

When you face a real problem, you rarely have access to multiple experts at once.

A student who wants to learn *while* gaming needs:
- A **gamer** who understands flow states and game mechanics
- A **high-achieving student** who knows proven study techniques  
- A **game designer** who understands educational psychology and learning UX

Right now, most AI tools give one generic answer. Real human need is for **multiple expert perspectives** that debate, challenge each other, and synthesise into one recommendation.

This is especially true for students from Tier 2 and Tier 3 cities in India who have no access to diverse expert networks. This product is **democratised expertise at scale**.

---

## 🎮 Live Demo

Open `index.html` in any browser. Enter your Anthropic API key and start asking.

**No build step. No dependencies. No server. One file.**

---

## 🔧 How It Works

```
User Question
     │
     ├──▶ The Gamer        (game strategy, engagement, flow state)
     ├──▶ The Topper       (study techniques, memory, productivity)
     └──▶ The Game Designer (gamification, learning UX, mechanics)
                │
                ▼
         The Moderator
    (reads all three → synthesises one unified recommendation)
```

**Technically:**
- All three expert calls run **in parallel** using `Promise.all()` for speed
- Each persona is a distinct Claude system prompt engineering a specific expert worldview
- The Moderator receives all three full responses as context and synthesises them
- Fully streamed — text appears word by word as it is generated
- Runs entirely in the browser — no backend, no server, no database

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| AI Model | Anthropic Claude (`claude-sonnet-4-20250514`) |
| API | Anthropic Messages API with streaming (`stream: true`) |
| Prompting | Structured JSON system prompts per persona |
| Frontend | Vanilla HTML + CSS + JavaScript (zero dependencies) |
| State | In-memory session history |
| Storage | `sessionStorage` for API key only |

---

## 🚀 Getting Started

**1. Clone the repo**
```bash
git clone https://github.com/NagabandiSwathvika/multi-expert-ai-panel.git
cd multi-expert-ai-panel
```

**2. Open in browser**
```bash
open index.html
# or just double-click index.html
```

**3. Enter your Anthropic API key**

Get a key at [console.anthropic.com](https://console.anthropic.com).  
Your key is stored only in your browser's `sessionStorage` — it is never sent anywhere except Anthropic's official API endpoint.

**4. Ask a question**

Try: *"How do I stay focused while playing games and also keep up with my studies?"*

Press **Convene Panel** or hit `Ctrl+Enter`.

---

## 🧪 Example Questions

| Topic | Question |
|---|---|
| Study + Gaming | How do I balance gaming with serious exam preparation? |
| Career | Should I take the high-paying job or join an early-stage startup? |
| Health | How do I build a workout habit when I have no motivation after classes? |
| Startup | I have a working AI prototype. What is the fastest way to validate it? |
| Learning | What is the best way to learn to code from scratch in 3 months? |

---

## 📁 Project Structure

```
multi-expert-ai-panel/
│
├── index.html        ← The entire application (HTML + CSS + JS, one file)
└── README.md         ← This file
```

---

## 🔬 Research Question Behind This Project

> *Does structured multi-persona LLM orchestration produce measurably better outcomes than single-model responses for personalised learning and advisory tasks?*

This prototype is the working demonstration of that hypothesis. The three-persona + moderator architecture is designed to test whether **structured disagreement and synthesis** between AI agents produces higher-quality recommendations than a single model asked the same question directly.

This is the research question I want to investigate formally at a university research lab.

---

## 🗺️ Roadmap

- [ ] **v1 (current):** Study + Gaming panel (Gamer, Topper, Game Designer)
- [ ] **v2:** User-configurable personas — input your own expert types for any domain
- [ ] **v3:** Health advisory panel (Doctor, Nutritionist, Physiotherapist)
- [ ] **v4:** Startup panel (Product Manager, Finance Expert, Marketing Strategist)
- [ ] **v5:** API backend + user accounts for saving session history
- [ ] **v6:** Vertical-specific SaaS product

---

## ⚠️ Security Note

This project calls the Anthropic API directly from the browser.  
- Your API key is stored in `sessionStorage` only (cleared when tab closes)
- Never commit your API key to this repository
- For production use, proxy all API calls through a backend server

---

## 👩‍💻 About the Builder

**Nagabandi Swathvika**  
B.Tech Computer Science & Engineering — 1st Year  
Kakatiya Institute of Technology and Science (KITSW), Warangal, Telangana  
CGPA: 8.45 / 10

- 📧 nagabandiswathvika277@gmail.com  
- 🏆 Smart India Hackathon 2025 (national level)
- 🎓 Generative AI Mastermind — Outskill (2025)
- 💡 Ideathon 2026 — KITSW Centre for Innovation

Built this independently — no team, no lab, no supervisor — because I experienced the problem directly as a student from a Tier 2 city with no expert network.

---

## 📄 License

MIT License — free to use, modify, and build on.

---

*"The best product ideas come from people who experience the problem directly, not from those who study it from a distance."*
