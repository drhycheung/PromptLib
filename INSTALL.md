# 📦 Installing Agent Skills from PromptLib

This guide explains how to install and use Agent Skills from this repository with AI coding assistants like OpenCode, Cursor, and other Agent Skills-compatible tools.

## What are Agent Skills?

Agent Skills are structured, reusable prompts that define specific capabilities for AI assistants. They follow the [Agent Skills specification](https://agentskills.io/specification) and work with any compatible tool.

Each skill is a folder containing:
- `SKILL.md` — the main skill definition with frontmatter metadata
- `references/` — supporting documents like templates, guides, or examples

## Quick Start

### Option 1: Clone the entire repository

```bash
git clone https://github.com/drhycheung/PromptLib.git
cd PromptLib
```

The Agent Skills in `.agents/skills/` are immediately usable with your Agent Skills-compatible tool.

### Option 2: Copy a specific skill to your project

If you only need one skill, copy its folder to your project:

```bash
# Create the skills directory in your project
mkdir -p your-project/.agents/skills

# Copy the lesson-design skill
cp -r PromptLib/.agents/skills/lesson-design your-project/.agents/skills/
```

### Option 3: Use as a Git submodule (recommended for teams)

Add PromptLib as a submodule and symlink the skills you need:

```bash
# Add the repository as a submodule
cd your-project
git submodule add https://github.com/drhycheung/PromptLib.git skills/PromptLib

# Create a symlink to the skill you want
mkdir -p .agents/skills
ln -s ../skills/PromptLib/.agents/skills/lesson-design .agents/skills/lesson-design

# Commit the submodule and symlink
git add .gitmodules skills/ .agents/skills/lesson-design
git commit -m "Add PromptLib lesson-design skill as submodule"
```

To update later:
```bash
git submodule update --remote skills/PromptLib
```

## Using Skills with OpenCode

1. Install OpenCode following the [official documentation](https://opencode.ai/docs/installation).

2. Place the `.agents/skills/` folder in your project root (or use one of the options above).

3. OpenCode will automatically discover and load skills when you start a session:
   ```bash
   cd your-project
   opencode
   ```

4. Trigger the skill with a relevant request:
   ```
   Help me design a 50-minute lesson on peer feedback for first-year students.
   ```

5. OpenCode will automatically load and apply the `lesson-design` skill.

## Using Skills with Cursor

1. Install Cursor from [cursor.sh](https://cursor.sh).

2. Place the `.agents/skills/` folder in your project root.

3. In Cursor settings, ensure Agent Skills support is enabled.

4. Start a chat and make a relevant request. Cursor will automatically detect and use matching skills.

## Using Skills with Other Tools

Agent Skills follow an open specification. Any tool that supports the [Agent Skills specification](https://agentskills.io/clients) can read and use these skills. Check your tool's documentation for specifics.

## Available Skills

| Skill | Folder | Purpose |
|---|---|---|
| **lesson-design** | `.agents/skills/lesson-design/` | Design university lesson plans with constructive alignment and Bloom's taxonomy |

## Skill Structure

Each skill folder contains:

```
.agents/skills/lesson-design/
├── SKILL.md                    # Main skill definition
└── references/
    ├── bloom-levels.md        # Bloom taxonomy guide
    └── lesson-plan-template.md # Output template
```

The `SKILL.md` file includes:
- YAML frontmatter with metadata (name, description, version)
- Instructions for when to use the skill
- Step-by-step workflow
- Quality checklist
- Boundary conditions

## Verifying Installation

To check if a skill is properly installed:

```bash
# List the skill folder
ls -la .agents/skills/lesson-design/

# Should show:
# SKILL.md
# references/
#   ├── bloom-levels.md
#   └── lesson-plan-template.md
```

## Testing a Skill

For OpenCode users, you can test a skill using the non-interactive runner:

```bash
opencode run "Help me design a 50-minute lesson about photosynthesis for Year 7 students."
```

Check that:
- The skill is loaded (look for `skill: lesson-design` in the output)
- The response follows the skill's template structure
- The output language matches your request

## Troubleshooting

### Skill not loading

- Ensure the `.agents/skills/` folder is in your project root
- Check that `SKILL.md` has valid YAML frontmatter (between `---` markers)
- Verify the skill name matches the folder name (`lesson-design` folder → `name: lesson-design` in frontmatter)

### Wrong language output

The `lesson-design` skill writes in the language you use. Write your request in Chinese to receive a Chinese lesson plan, or in English for an English plan.

### Output doesn't match template

Some sections may be omitted if not applicable (e.g., "Lecture outline" for a workshop). The skill automatically renumbers sections to stay consecutive.

## Contributing

To contribute new skills or improvements:

1. Follow the [Agent Skills specification](https://agentskills.io/specification)
2. Structure your skill as:
   ```
   .agents/skills/your-skill-name/
   ├── SKILL.md
   └── references/
       └── (supporting files)
   ```
3. Add corresponding eval cases in `evals/your-skill-name/cases.json`
4. Submit a pull request

## Further Reading

- [Agent Skills Specification](https://agentskills.io/specification)
- [Agent Skills Quickstart](https://agentskills.io/skill-creation/quickstart)
- [Agent Skills Best Practices](https://agentskills.io/skill-creation/best-practices)
- [OpenCode Documentation](https://opencode.ai/docs/skills/)
