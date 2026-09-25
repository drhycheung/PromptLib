# 📚 PromptLib

A collection of education-oriented AI chatbot prompts and Agent Skills by [@drhycheung](https://poe.com/profile/drhycheung).

## 🤖 Agent Skills (recommended)

Agent Skills are structured, reusable prompts that work with AI coding assistants like [OpenCode](https://opencode.ai), [Cursor](https://cursor.sh), and other Agent Skills-compatible tools.

### ✨ Available Skills

| Skill | Purpose | Language | Agent Skill |
|---|---|---|---|
| 📝 LessonDesigner | Guided lesson design (LILOs → assessment → activities → plan) | Multilingual | [`.agents/skills/lesson-design/`](.agents/skills/lesson-design/) |

### 📦 Installation

**Option 1: Clone the repository**
```bash
git clone https://github.com/drhycheung/PromptLib.git
cd PromptLib
# Agent Skills in .agents/skills/ are ready to use
```

**Option 2: Copy specific skills**
Copy the `.agents/skills/lesson-design/` folder to your project:
```bash
mkdir -p your-project/.agents/skills
cp -r PromptLib/.agents/skills/lesson-design your-project/.agents/skills/
```

**Option 3: Submodule (for teams)**
```bash
git submodule add https://github.com/drhycheung/PromptLib.git skills/PromptLib
ln -s skills/PromptLib/.agents/skills/lesson-design .agents/skills/lesson-design
```

See [INSTALL.md](INSTALL.md) for detailed installation instructions.

### 🔗 Legacy & Source Documents

Each Agent Skill has a corresponding legacy prompt file. Both versions work — the Agent Skill adds structured error handling, language adaptation, and quality checks.

| Agent Skill | Legacy Prompt | Notes |
|---|---|---|
| [`lesson-design`](.agents/skills/lesson-design/) | [LessonDesigner.md](LessonDesigner.md) | Agent Skill adds Chinese language support, Bloom level guide, single-output enforcement, continuous numbering |

---

## 💬 Legacy Chatbot Prompts (Poe / Gemini / ChatGPT)

These bots were originally built on Poe. Since Poe has reduced the number of free daily credits, they are now being migrated to Gemini.

To use them, copy the prompt from any file into a custom bot on Poe, ChatGPT, Gemini, or your platform of choice. Each file contains the bot's description, welcome message, and full prompt (typos and grammar lightly corrected), so feel free to copy and adapt them for your own chatbots.

## 🧑‍🏫 Teaching design & assessment

For teachers preparing lessons and tests.

| Bot | Purpose | Language | File |
|---|---|---|---|
| 📝 LessonDesigner | Guided lesson design (LILOs → assessment → activities → plan) | English | [LessonDesigner.md](LessonDesigner.md) |
| ❓ TestGen | ILO-aligned test question generation (MCQ + long questions) | English | [TestGen.md](TestGen.md) |

## ✅ Marking & feedback

For speeding up feedback on student work.

| Bot | Purpose | Language | File |
|---|---|---|---|
| 💬 FeedbackHelper | Generating student feedback from draft marking comments | English | [FeedbackHelper.md](FeedbackHelper.md) |

## 🎓 Tutoring & coaching

For students to learn, practise, and build projects.

| Bot | Purpose | Language | File |
|---|---|---|---|
| 🎮 LetsLearn | Adaptive learning quiz game with hints and feedback | English | [LetsLearn.md](LetsLearn.md) |
| 🏛️ MrSocrates | Socratic tutoring for active learning | Multilingual | [MrSocrates.md](MrSocrates.md) |
| 🇯🇵 NihongoABC | Japanese translation and learning tutor | EN/中文 → 日本語 | [NihongoABC.md](NihongoABC.md) |
| 🚀 StartupAdvisorEdUHK | Lean canvas and timeline coaching for student startups | English | [StartupAdvisorEdUHK.md](StartupAdvisorEdUHK.md) |

## 🧘 Reflection & wellbeing

For personal reflection and life advice.

| Bot | Purpose | Language | File |
|---|---|---|---|
| 🪷 BigBuddha | Life advice through a Buddha persona | 中文 | [BigBuddha.md](BigBuddha.md) |
| 📊 SWOTReflect_zh | SWOT analysis of work journals, with improvement suggestions | 中文 | [SWOTReflect_zh.md](SWOTReflect_zh.md) |
| ☯️ YangmingBot | Life advice through a Wang Yangming persona | 中文 | [YangmingBot.md](YangmingBot.md) |
