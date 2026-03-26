# norml-claude-skills

Shared Claude skills for the Norml Studio team. Install once, available in every session.

## Skills

| Skill | What it does |
|-------|-------------|
| **norml-seo-writer** | SEO content writing with staged human review. Blog posts, descriptions, landing pages — researched, outlined, drafted, and humanized. |

More skills coming: dev, design, PM workflows.

---

## Installation

### Claude Code (terminal, Desktop, claude.ai/code)

Run these two commands in Claude Code:

```
/plugin add marketplace maxtymosh/norml-claude-skills norml
/plugin install norml-claude-skills@norml
```

The skills will be available in all Claude Code sessions on your machine — terminal, Desktop, and web.

**To update** when new skills are added:

```
/plugin update
```

### Project-specific install

To add skills only to a specific project, copy the skills folder into the repo:

```bash
cp -r skills/* /path/to/your/project/.claude/skills/
```

Commit `.claude/skills/` to the repo — teammates get the skills automatically on `git pull`.

---

## Usage

Once installed, skills trigger automatically from natural language. Examples:

**norml-seo-writer:**
- "Write a blog post targeting 'best CRM for small business'"
- "Create a category description for our running shoes collection"
- "I need landing page copy for [keyword]"

If a skill doesn't trigger automatically, reference it by name: "Use the norml-seo-writer skill to..."

---

## Ahrefs integration

The norml-seo-writer skill uses Ahrefs for keyword research if your team has it connected as an MCP server. Without Ahrefs, it falls back to web search.

---

## Adding new skills

Create a new folder under `skills/` following this structure:

```
skills/your-skill-name/
├── SKILL.md              # Main instructions (required)
└── references/           # Supporting docs (optional)
    └── some-reference.md
```

See `skills/norml-seo-writer/` for a working example. The SKILL.md needs YAML frontmatter with `name` and `description` fields.

Push to `main` — teammates run `/plugin update` to get the new skills.

---

## File structure

```
norml-claude-skills/
├── .claude-plugin/
│   └── plugin.json
├── skills/
│   └── norml-seo-writer/
│       ├── SKILL.md
│       └── references/
│           ├── content-types.md
│           ├── seo-rules.md
│           └── quality-checklist.md
└── README.md
```
