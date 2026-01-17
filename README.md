# Brand Studio

<div align="center">

[![Claude Code Plugin](https://img.shields.io/badge/Claude%20Code-Plugin-7C3AED)](https://claude.ai/code)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-0.1.0-blue.svg)]()

**Complete brand identity toolkit for Claude Code. Copywriting, visual design, and brand guidelines — all from your terminal.**

### Quick Install

```bash
# Add the marketplace
claude plugin marketplace add https://github.com/ProofOfReach/brand-studio-plugin.git

# Install the plugin
claude plugin install brand-studio@brand-studio-plugin
```

</div>

---

## TL;DR

**The Problem**: Building a brand requires juggling copywriters, designers, and brand strategists. You end up with inconsistent messaging, mismatched visuals, and brand guidelines nobody follows.

**The Solution**: Brand Studio gives Claude Code three specialized skills that work together — research-driven copywriting, principled visual design, and unified brand system orchestration.

### Why Use Brand Studio?

| Feature | What It Does |
|---------|--------------|
| **Research-First Copy** | Headlines and sales copy grounded in Hopkins, Cialdini, Schwartz frameworks |
| **Awareness-Level Matching** | Automatically adapts messaging to cold, warm, or hot audiences |
| **AI-Powered Design** | Logo concepts, color palettes, typography via nano-banana MCP |
| **Brand Kit Orchestration** | Full brand guidelines from strategy through visual identity to voice |
| **Reference Libraries** | 15+ specialized frameworks loaded on-demand per task |

---

## Quick Example

```bash
# Write a complete landing page with research phase
/copywriting
> "Write a landing page for MenuFlow, an AI-powered inventory
   management tool for restaurant owners"

# Create a color palette with accessibility checks
/designing
> "Create a color palette for MenuFlow - mood: trustworthy,
   modern, appetizing. Must pass WCAG AA."

# Build a full brand kit from scratch
/brand-building
> "Create brand guidelines for MenuFlow with values:
   efficiency, reliability, simplicity"
```

---

## How Brand Studio Compares

| Capability | Brand Studio | Generic AI | Copywriter + Designer | DIY |
|------------|--------------|------------|----------------------|-----|
| Research-first process | ✅ Built-in | ❌ Skips research | ✅ Manual | ❌ |
| Awareness-level matching | ✅ Automatic | ❌ Generic | ⚠️ If experienced | ❌ |
| Proven frameworks | ✅ 15+ loaded | ❌ Generic prompts | ⚠️ Varies | ❌ |
| Visual + verbal alignment | ✅ Integrated | ❌ Separate | ⚠️ Coordination needed | ❌ |
| Brand guidelines output | ✅ Complete doc | ❌ Fragments | ✅ Manual assembly | ❌ |

**When to use Brand Studio:**
- Building a new brand from scratch
- Creating landing pages, emails, ads with proven conversion frameworks
- Need consistent visual identity with strategic rationale

**When Brand Studio might not be ideal:**
- Highly regulated industries requiring legal review
- Established brands with strict existing guidelines (use those instead)

---

## Installation

### Via CLI (Recommended)

```bash
# Add the marketplace
claude plugin marketplace add https://github.com/ProofOfReach/brand-studio-plugin.git

# Install the plugin
claude plugin install brand-studio@brand-studio-plugin
```

### Per-Session Loading

```bash
claude --plugin-dir /path/to/brand-studio-plugin
```

---

## Skills

### Copywriting Skill (`/copywriting`)

Generate research-driven marketing copy using proven frameworks.

| Use Case | Example |
|----------|---------|
| Landing pages | `/copywriting` then describe your product and audience |
| Headlines | Ask for headline variations for your offer |
| Email sequences | Request email copy with awareness-level matching |
| Ad copy | Generate Facebook/Google ad variations |

### Designing Skill (`/designing`)

Create visual brand concepts with principled design rationale.

| Use Case | Example |
|----------|---------|
| Logo concepts | `/designing` then describe brand personality |
| Color palettes | Request palette with mood and accessibility requirements |
| Typography | Get font pairing recommendations for your industry |

### Brand-Building Skill (`/brand-building`)

Orchestrate complete brand guidelines combining copy and design.

| Use Case | Example |
|----------|---------|
| New brand | `/brand-building` with name, values, and target audience |
| Brand refresh | Provide existing assets for cohesive update |
| Brand guidelines doc | Generate complete brand book |

---

## Architecture

```
brand-studio/
│
├── skills/
│   ├── copywriting/             # Copywriting skill
│   │   ├── SKILL.md             # Write Mode + Review Mode workflows
│   │   ├── references/          # 11 framework files
│   │   │   ├── headlines.md     # Headline formulas, swipe file
│   │   │   ├── landing-pages.md # LIFT Model, conversion principles
│   │   │   ├── psychology.md    # Cialdini's 6 principles
│   │   │   ├── awareness-levels.md # Schwartz's 5 levels
│   │   │   └── ...
│   │   └── scripts/             # Analysis tools
│   │
│   ├── designing/               # Visual design skill
│   │   ├── SKILL.md             # 5-stage design process
│   │   └── references/          # 4 principle files
│   │       ├── logo-design-principles.md
│   │       ├── color-theory-principles.md
│   │       ├── typography-principles.md
│   │       └── brand-strategy-principles.md
│   │
│   └── brand-building/          # Orchestration skill
│       └── SKILL.md             # 5-phase brand creation workflow
│
└── .claude-plugin/
    └── plugin.json              # Plugin manifest
```

---

## The Methodology

### Copywriting Foundations

Brand Studio's copy skill is built on four masters:

| Author | Framework | Applied To |
|--------|-----------|------------|
| **Claude Hopkins** | Scientific Advertising | Specificity, testing, proof |
| **Robert Cialdini** | 6 Principles of Influence | Reciprocity, scarcity, authority |
| **Eugene Schwartz** | 5 Awareness Levels | Message-to-market matching |
| **Chip & Dan Heath** | SUCCESs (Made to Stick) | Memorable, sticky messaging |

### Design Foundations

| Domain | Core Principles |
|--------|----------------|
| **Logo Design** | Simplicity, memorability, versatility, appropriateness, timelessness |
| **Color Theory** | Harmony, contrast, psychology, context, accessibility (WCAG) |
| **Typography** | Hierarchy, legibility, personality, pairing, restraint |
| **Brand Strategy** | Positioning, differentiation, consistency, evolution |

---

## Configuration

### Image Generation (Optional)

For AI-generated logos and visual concepts, configure nano-banana MCP:

```bash
# In your Claude Code MCP config
{
  "mcpServers": {
    "nano-banana": {
      "command": "npx",
      "args": ["-y", "nano-banana-mcp"]
    }
  }
}
```

---

## Troubleshooting

### "Reference file not found"

**Cause:** Skill is looking for a framework file that wasn't loaded.

**Solution:** Ensure the plugin is installed completely:
```bash
claude plugin remove brand-studio
claude plugin add proofofreach/brand-studio
```

### Design commands not generating images

**Cause:** nano-banana MCP not configured.

**Solution:** The design skill works without image generation (provides specs and directions), but for actual asset creation, configure the MCP as shown above.

### Still having issues?

1. Search [existing issues](https://github.com/ProofOfReach/copywriting-plugin/issues)
2. Open a [new issue](https://github.com/ProofOfReach/copywriting-plugin/issues/new)

---

## Limitations

### What Brand Studio Doesn't Do (Yet)

- **Legal/compliance review** — Copy is marketing-focused, not legal-reviewed
- **Actual asset files** — Outputs specs and concepts; final production requires design tools
- **Brand enforcement** — Audits are advisory, not automated enforcement

### Known Constraints

| Constraint | Workaround |
|------------|------------|
| Image generation requires MCP | Design skill still provides detailed specs without it |
| No direct Figma/Sketch export | Use specs to recreate in design tools |

---

## FAQ

### Why "Brand Studio"?

It's a complete studio for brand creation — not just copywriting, not just design, but the full integrated workflow.

### What happened to "copywriting-plugin"?

Brand Studio is the evolution. The original copywriting skill is now `/copywriting`, joined by `/designing` and `/brand-building` for complete brand creation.

### Can I use just the copywriting skill?

Yes. Each skill works independently. Use `/copywriting` without touching designing or brand-building.

### Does it work with my existing brand?

Yes. Use `/copywriting` to review existing copy, or provide your brand guidelines when using any skill to generate on-brand content.

### Can I use this commercially?

Yes — MIT license. Use it for client work, your own brands, whatever you need.

---

## Contributing

Contributions welcome. Please open an issue to discuss proposed changes before submitting a PR.

**Areas we'd love help with:**
- Additional copywriting frameworks (VSL, webinar scripts)
- Industry-specific reference files
- Integration with more design MCPs

---

## License

MIT

---

<div align="center">

*Built by [ProofOfReach](https://github.com/ProofOfReach)*

</div>
