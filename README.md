# WebGL Creative Experience Skill

A skill for Claude Code to create premium, immersive creative agency websites using WebGL technology.

## For Plugins

### Add as Skill

To use this skill in your Claude Code plugin, add it to your plugin's skills directory:

```bash
mkdir -p your-plugin/skills/webgl-creative
cp -r /path/to/webgl-creative/* your-plugin/skills/
```

Or add as a git submodule:

```bash
git submodule add https://github.com/Abdulhadi446/webgl-creative-skill.git your-plugin/skills/webgl-creative
```

### Add Slash Command

To create a slash command that triggers this skill, add a command file in your plugin's commands directory:

```yaml
---
name: /webgl
description: Create immersive WebGL creative experiences
permissions:
  - role: user
skill: webgl-creative
---

Create a premium WebGL-powered creative agency website.
```

Or use the Command Development skill to create a proper slash command with the `skill` field pointing to `webgl-creative`.

## Trigger Phrases

This skill activates when users ask to:
- "build a creative agency website"
- "create immersive WebGL experience"
- "build award-winning portfolio site"
- "create full-screen 3D canvas website"
- "edit the activetheory site"
- "modify the WebGL site"
- or similar high-end creative digital experiences

## Workflow

1. **Clone** the base repository: `https://github.com/Abdulhadi446/activetheory.net.git`
2. **Understand** the structure (see SKILL.md)
3. **Modify** based on user request
4. **Test** changes locally

## What This Skill Provides

- Cloning existing WebGL starter template
- Understanding the codebase structure
- Common modification patterns
- Testing procedures

## Files

```
├── SKILL.md              # Main skill documentation
├── README.md             # This file
├── references/
│   ├── tech-stack.md     # Framework options, shaders, performance
│   └── additional-guides.md
└── examples/
    └── index.html        # Base HTML template
```

See [SKILL.md](./SKILL.md) for full documentation.

## Related Skills

- **frontend-design** - General frontend UI/UX design