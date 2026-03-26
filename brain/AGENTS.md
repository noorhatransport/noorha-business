# AI Second Brain

> Your intelligent business companion that compounds knowledge with every project.

---

## Quick Start



### Skills Management in Codex

**Important:** Codex loads skills at startup, not runtime.

**When to restart Codex:**
- After adding new skills to `.codex/skills/`
- After modifying AGENTS.md
- After updating skill frontmatter

**To verify loaded skills:** Run `codex` and type `/skills` to list available skills.

### Codex File Loading Behavior

**Unlike Claude Code's proactive scanning, Codex uses conservative file loading:**
- Skills must explicitly request file reads (e.g., "Read memory/company/products.md")
- Not automatic - reduces token usage for simple tasks
- More efficient for straightforward workflows

**In practice:** Skills should include explicit Read commands in their instructions.

 (5 Minutes to First Value)

### Step 1: Fill "About Me" below (2 min)
Scroll down and fill in your name, role, and what you do.

### Step 2: Run `/ask` (3 min)
```
/ask "Help me write a follow-up email to a prospect"
```

That's it. Your brain is working. Everything else builds on this.

---

## Ready for More?

| What You Want | Command | Time |
|--------------|---------|------|
| Quick help with any task | `/ask [question]` | 30 sec |
| Systematic project execution | `/plan [task]` | 3 min |
| Check your brain's growth | `/grow` | 5 sec |
| Search past work & patterns | `/recall [topic]` | 10 sec |

---

## About Me

### Who I Am
- **Name**: [Your Full Name]
- **Role**: [Your Professional Title]
- **Industry/Focus**: [Your Primary Industry or Expertise Area]

> 💡 **Quick Start Tip**: Fill in your basic details above, then run `/ask` to start using your Second Brain. You can come back and add more details later.

### What I Do
[2-3 sentences describing your professional work. What problems do you solve? Who do you serve? What makes your approach unique?]

**Example**: "I help growing SaaS companies scale their operations without sacrificing quality. My work focuses on building systems and processes that enable teams to work more efficiently while maintaining high standards."

### My Expertise
- [Core Expertise Area 1]
- [Core Expertise Area 2]
- [Core Expertise Area 3]
- [Core Expertise Area 4]
- [Add more as needed]

**💡 Tip**: List 3-7 areas where you have deep knowledge or unique insights.

### My Goals with This Brain
- **[Goal Category 1]**: [Specific outcome you want, e.g., "Save 5 hours/week on content creation"]
- **[Goal Category 2]**: [Another specific outcome]
- **[Goal Category 3]**: [Another specific outcome]
- **[Add More Goals]**: [The more specific you are, the better your brain performs]

**💡 Tip**: Start with 3-5 concrete goals. You can add more as you discover new use cases.

---

## My Business Context

### Services & Offerings
See: `memory/personal/services.md`

### Audience
See: `memory/audience/ideal-client.md`

### Positioning & Differentiation
See: `memory/personal/positioning.md` and `memory/personal/differentiators.md`

### Values & Frameworks
See: `memory/values-beliefs/` - The core context that shapes all my work

---

## The 4-Command Workflow

This brain uses a systematic approach to every task:

```
/plan [task]  →  /work [plan]  →  /review [output]  →  /learn
    ↓               ↓                  ↓                 ↓
 Research       Execute with       6-agent           Extract
 + Plan         todo tracking      quality check     patterns
```

### Command Reference

| Command | Purpose | Time |
|---------|---------|------|
| `/start` | First win in 30 seconds | 30 sec |
| `/setup` | Guided brain configuration | 10 min |
| `/plan [task]` | Create systematic execution plan | 2-3 min |
| `/work [plan.md]` | Execute with todo tracking | Varies |
| `/review [output.md]` | 6-agent parallel quality review | 30 sec |
| `/learn` | Extract patterns to memory | 3 min |
| `/recall [topic]` | Search memory for relevant context | 10 sec |
| `/grow` | View brain health metrics | 5 sec |

---

## Repository Navigation

### Memory (Semantic Knowledge)

**Core Context (Critical for Content)**
- `memory/values-beliefs/` - Core values, beliefs, frameworks, principles, POVs
- `memory/style-voice/` - Writing style, tone, vocabulary, structure preferences
- `memory/personal/` - Expertise, services, positioning, differentiators
- `memory/audience/` - Ideal clients, pain points, objections

**Patterns & Examples**
- `memory/patterns/` - Extracted wisdom (grows with each /learn)
  - `content-patterns.md` - What works in writing
  - `offer-patterns.md` - Successful offers
  - `messaging-patterns.md` - Communication that lands
- `memory/examples/` - Best-in-class content organized by type
  - `meeting-summaries/` - Effective meeting summaries and transcripts
  - `proposals/` - Winning client proposals and SOWs
  - `cx-audits/` - CX assessment and audit reports
  - `outreach/` - Successful fractional opportunity outreach
  - `linkedin/` - CX thought leadership content
  - `emails/` - Email templates for clients and prospects

**Knowledge Repository (Your Idea Vault)**
- `memory/knowledge-repo/` - Never lose a thought again
  - `ideas/` - Raw ideas and insights
  - `concepts/` - Developed concepts
  - `insights/` - Key learnings
  - `papers/` - Research notes

### Experiences (Episodic Memory)
- `experiences/content/` - Content creation projects
- `experiences/clients/` - Client work
- `experiences/products/` - Product development
- Each experience folder contains: plan → research → output → review → learnings

### Brain Health
- `brain-health/growth-log.md` - Timeline of brain updates
- `brain-health/pattern-confidence.md` - Pattern strength tracking
- `brain-health/quality-metrics.md` - Review score trends

---

## Skill Unlock Progress

Track your mastery level:

### Level 1: Foundation
- [ ] Run `/ask` for first quick win
- [ ] Fill `memory/values-beliefs/` with core values and frameworks
- [ ] Fill `memory/personal/` basics (expertise, services, positioning)
- [ ] Populate `memory/style-voice/` with writing guidelines

### Level 2: Core Workflow
- [ ] Complete first `/plan → /work → /review → /learn` cycle
- [ ] See first pattern extracted to memory
- [ ] Achieve 8+ quality score on /review

### Level 3: Pattern Power
- [ ] Have 5+ patterns in memory
- [ ] See time savings on repeated task types
- [ ] Have at least one HIGH confidence pattern

### Level 4: Expert Mode
- [ ] 20+ experiences logged
- [ ] Consistent 9+ quality scores
- [ ] Compound time savings visible in /grow

---

## MCP Integrations (Optional)

Enhance your brain with external tools:

- **HubSpot**: CRM data for prospect research
- **LinkedIn**: Professional context discovery
- **Google Workspace**: Calendar, email, docs access
- **Custom MCPs**: Add your own integrations

Configure in: `~/.codex/mcp.json`

---

## Best Practices

1. **Always /plan first** - Never jump straight into work
2. **Complete the cycle** - /plan → /work → /review → /learn
3. **Trust the /review** - 6 agents catch what you miss
4. **Feed the brain** - Run /learn after every project
5. **Check /grow weekly** - See your compound returns

---

## Troubleshooting

### Brain feels empty?
- Fill `memory/values-beliefs/` with your core values and frameworks
- Populate `memory/personal/` with your expertise and positioning
- Capture writing samples in `memory/style-voice/examples.md`
- Complete one full cycle to seed patterns

### /review too harsh?
- Review agents calibrate over time
- Feed them examples in `memory/examples/`
- They learn your brand voice through patterns

### Not seeing improvements?
- Run `/grow` to check metrics
- Ensure you're running `/learn` after each project
- Check `brain-health/pattern-confidence.md`

---

**Version**: 1.0.0
**Template**: AI Second Brain by AI Maturity Index


---

## Platform: OpenAI Codex CLI

This repository is configured for **OpenAI Codex CLI** (experimental Skills support).

**Also compatible with:** Claude Code CLI (uses CLAUDE.md instead)

**To switch platforms:**
- For Codex: Use this AGENTS.md file and `.codex/skills/`
- For Claude Code: Use CLAUDE.md file and `.claude/commands/` or `.claude/skills/`

Both platforms work with the same memory structure (platform-agnostic).
