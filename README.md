# Interview Scheduling Automation 🗓️

> **AI Automation Intern Assessment — Problem 2**

An AI-powered interview scheduling tool that eliminates back-and-forth emails by intelligently matching candidate and interviewer availability.

---

## 🔗 Live Demo

**[➜ Open the tool]([https://erudite13.github.io/interview-scheduler/]**

---

## 🎯 What It Does

Enter availability windows for a candidate and 3–5 interviewers. The tool uses Claude AI to:

- **Find overlapping slots** across all participants
- **Rank the top 3 options** by quality (time of day, number of available interviewers, etc.)
- **Resolve conflicts** and explain any trade-offs
- **Output a structured recommendation** with reasoning

---

## 📥 Inputs

| Field | Example |
|---|---|
| Candidate name | Priya Sharma |
| Role applied for | AI Automation Intern |
| Candidate availability | Tuesday 2–6 PM, Thursday 10 AM–1 PM |
| Interviewer availability (3–5) | Rahul: Tue 3–6 PM, Ananya: Tue 1–5 PM, Karan: Fri 9 AM–12 PM |
| Interview duration | 30 / 45 / 60 / 90 minutes |
| Format | 1-on-1 / Panel / Sequential |

---

## 📤 Outputs

```
Slot #1 — Best slot
Tuesday, 3:00 PM – 4:00 PM
Interviewers: Rahul Mehta, Ananya Singh
Reason: Both interviewers and candidate are free during this window.

Slot #2 — Good option
Tuesday, 4:00 PM – 5:00 PM
...

Slot #3 — Fallback
...

Summary: 3 valid slots found. No hard conflicts. Panel format not possible on Friday.
```

---

## 🛠️ Tools Used

- **HTML / CSS / Vanilla JS** — Single-file frontend, no build step required
- **Claude API (claude-sonnet-4-20250514)** — Availability analysis & slot recommendation
- **Google Fonts** — DM Sans, Instrument Serif, DM Mono

---

## 🚀 How to Run Locally

```bash
# Just open the file in a browser — no server needed
open index.html
```

> The app calls the Anthropic API directly. The API key is injected automatically when hosted via Claude.ai artifacts or configured via the Anthropic platform.

---

## 🧠 Approach

1. **Collect inputs** — Parse candidate and interviewer availability as natural time ranges (e.g. "Tuesday 2:00 PM – 6:00 PM")
2. **Build a structured prompt** — Send all availability data to Claude with clear rules about what constitutes a valid slot
3. **Parse JSON response** — Claude returns a ranked list of slots with reasons and conflict notes
4. **Render results** — Display ranked slots with colour-coded cards, interviewer pills, and a summary

The AI handles the hard parts: overlapping time windows, conflict detection, and ranking heuristics — so no manual calendar math is needed.

---

## 📁 File Structure

```
interview-scheduler/
└── index.html      # Complete app — single self-contained file
└── README.md       # This file
```

---

## ✅ Assessment Checklist

- [x] Top 3 suggested interview time slots
- [x] Conflict resolution with explanations
- [x] Final recommendation with reasoning
- [x] Works with realistic sample data (pre-filled)
- [x] Clean, usable UI
- [x] AI-powered (Claude API)
