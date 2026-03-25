# norml-claude-skills

Shared Claude skills for the Norml Studio team. Install once, available in every session.

## Skills

| Skill | What it does |
|-------|-------------|
| **seo-writer** | SEO content writing with staged human review. Blog posts, descriptions, landing pages — researched, outlined, drafted, and humanized. |

More skills coming: dev, design, PM workflows.

---

## Installation

### Claude Desktop (Cowork)

1. Download `norml-claude-skills.plugin` from the [latest release](https://github.com/norml-studio/norml-claude-skills/releases)
2. Open Claude Desktop
3. Drag the `.plugin` file into any chat, or open it from Finder/Explorer
4. Click "Install" when prompted

The skills will be available in all your Cowork sessions.

**To update:** download the new `.plugin` file and install again — it overwrites the previous version.

### Claude Code (terminal)

Clone the repo and copy the skills to your global Claude directory:

```bash
git clone https://github.com/maxtymosh/norml-claude-skills.git
cp -r norml-claude-skills/skills/* ~/.claude/skills/
```

The skills will be available in every Claude Code session on your machine.

**To update:**

```bash
cd norml-claude-skills
git pull
cp -r skills/* ~/.claude/skills/
```

### Project-specific install (Claude Code)

If you only want the skills in a specific project:

```bash
cp -r norml-claude-skills/skills/* /path/to/your/project/.claude/skills/
```

---

## Usage

Once installed, skills trigger automatically from natural language. Examples:

**seo-writer:**
- "Write a blog post targeting 'best CRM for small business'"
- "Create a category description for our running shoes collection"
- "I need landing page copy for [keyword]"

If a skill doesn't trigger automatically, reference it by name: "Use the seo-writer skill to..."

---

## Ahrefs integration

The seo-writer skill uses Ahrefs for keyword research if your team has it connected as an MCP server. Without Ahrefs, it falls back to web search.

---

## Adding new skills

Create a new folder under `skills/` following this structure:

```
skills/your-skill-name/
├── SKILL.md              # Main instructions (required)
└── references/           # Supporting docs (optional)
    └── some-reference.md
```

See `skills/seo-writer/` for a working example. The SKILL.md needs YAML frontmatter with `name` and `description` fields.

After adding, rebuild the `.plugin` file:

```bash
cd norml-claude-skills
zip -r norml-claude-skills.plugin . -x "*.DS_Store" -x ".git/*" -x ".gitignore"
```

Then attach it to a new GitHub release.

---

## File structure

```
norml-claude-skills/
├── .claude-plugin/
│   └── plugin.json
├── skills/
│   └── seo-writer/
│       ├── SKILL.md
│       └── references/
│           ├── content-types.md
│           ├── seo-rules.md
│           └── quality-checklist.md
└── README.md
```
