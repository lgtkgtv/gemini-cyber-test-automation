# 🎮 AI Cyber Academy: Junior Track (Ages 12+)
### Hands-On Cybersecurity & AI Defense Missions

Welcome, future cybersecurity defender! 🚀

The **Junior Track** is designed for middle and high school students, young coders, and beginners who want to learn how computers think, why locks break, and how to build smart AI guards to protect networks.

---

## 🗺️ Mission Syllabus

| Mission Notebook | Title & Theme | Hacker Detective Puzzle | Real-World Defense Skill |
| :--- | :--- | :--- | :--- |
| [`1_vulnerability_discovery_junior.ipynb`](./1_vulnerability_discovery_junior.ipynb) | **Level 1: The Code Doctor**<br>*(Finding & Healing Broken Locks)* | **The Secret Coin Riddle:**<br>Can you trick the database into unlocking every secret account with math? | **SQL Injection Defense:**<br>Put user inputs into an *unbreakable glass envelope* (`?`) so computers never mistake words for commands! |
| [`2_stateful_defense_analyst_junior.ipynb`](./2_stateful_defense_analyst_junior.ipynb) | **Level 2: The AI Security Guard**<br>*(Catching Burglars & Base Lockdown)* | **The AI Trickster Challenge:**<br>Can you disguise yourself as a teacher or robot boss to fool the AI guard? | **Stateful AI Security:**<br>Teach an AI agent to remember past clues, stop sneaky burglars, and trigger emergency lockdown! |

---

## 💡 What You Will Learn

- **The Golden Rule of Computers:** *Never let a guest write instructions for the restaurant's kitchen.* Computers follow instructions literally—if you don't keep user words separate from computer commands, attackers can rewrite the program!
- **Interactive Puzzles:** Click buttons, try different sneaky passwords, and watch the database react in real time.
- **Side-by-Side Code Diffs:** See before-and-after comparisons showing how the AI "Code Doctor" fixes security bugs.
- **The Blast Chamber Test:** Prove that the fix works! We test the hacker's attack on the healed code to make sure it's blocked, and make sure regular users can still log in.
- **Autonomous Emergency Lockdown:** Watch our AI security guard call automatic tools to block bad IP addresses and isolate infected computers.

---

## 🚀 Quick Start Guide

### 1. Requirements
Make sure you have Python 3.12+ and [`uv`](https://docs.astral.sh/uv/) installed.

### 2. Setup Environment
Open your terminal and run:

```bash
# From the repository root:
uv sync

# Configure your Google Gemini API key:
cp .env.example .env
# Edit .env and add your GEMINI_API_KEY

# Launch Jupyter Notebook:
uv run jupyter notebook
```

Navigate into the `junior_track/` folder and open **`1_vulnerability_discovery_junior.ipynb`** to start Level 1!
