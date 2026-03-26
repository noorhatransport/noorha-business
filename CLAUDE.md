# Noorha Transport — Business Operations Monorepo

> One repo, one brain, everything connected.

---

## Monorepo Structure

```
noorha-business/
├── CLAUDE.md              ← You are here (root instructions)
├── .claude/               ← Agents, commands, skills, hooks
├── brain/                 ← AI Second Brain (knowledge & memory)
│   ├── memory/            ← Semantic knowledge (company, customers, patterns)
│   ├── experiences/       ← Episodic memory (past projects)
│   ├── brain-health/      ← Growth metrics & quality tracking
│   ├── prompts/           ← Reusable prompt templates
│   └── projects/          ← Active project workspaces
├── apps/
│   └── website/           ← noorhatransport.com Next.js codebase (git submodule)
├── assets/
│   └── vehicles/          ← Fleet photography
├── docs/                  ← Strategy docs, guides, playbooks
├── INDEX.md               ← Full directory navigation
└── README.md              ← Quick overview
```

---

## About Me

### Who I Am
- **Name**: Zulfan Hameed
- **Role**: Founder / Owner
- **Company**: Noorha Transport
- **Industry/Focus**: Premium Transportation Services in Saudi Arabia

### What I Do
I run a premier transportation service in Saudi Arabia specializing in cross-border travel between KSA and Bahrain, corporate transportation for Aramco contractors, and airport transfers across the Eastern Province.

### My Expertise
- Cross-border transportation operations (KSA-Bahrain corridor)
- Corporate client management and B2B transportation services
- Aramco compliance and safety protocols
- Fleet management and premium vehicle operations
- Transportation logistics and route optimization
- Client relationship management in Saudi Arabia's business landscape

### My Goals
- **Operational Efficiency**: Generate all client communications 70% faster with consistent professional tone and standardized templates
- **Financial Clarity**: Create clear systems for tracking invoices, payments, and weekly financial snapshots
- **Team Structure**: Document roles, responsibilities, and create scalable onboarding processes
- **Business Intelligence**: Capture all key decisions and project status for better visibility
- **Scalable Foundation**: Build processes that don't depend on memory alone, enabling confident delegation
- **Communication Excellence**: Streamline driver coordination, client emails, and WhatsApp messaging
- **Compliance Management**: Systematize Aramco documentation and safety protocols

---

## My Business Context

### Services & Offerings
See: `brain/memory/company/products.md`

### Customers
See: `brain/memory/customers/ideal-customer-profile.md`

### Differentiation
See: `brain/memory/company/differentiators.md`

### Values & Frameworks
See: `brain/memory/values-beliefs/` - The core context that shapes all my work

---

## Working in This Monorepo

### Website Codebase (`apps/website/`)

The website is a **git submodule** pointing to `github.com/noorhatransport/noorhatransport`. It has its own CLAUDE.md with specific rules:

- **Git Workflow**: Never push directly to main. Always create feature branches and open PRs.
- **Analytics**: All events go through `src/lib/analytics.ts`. See `apps/website/docs/analytics-events.md`.
- **Deployment**: Vercel auto-deploys from main. PRs get preview deployments.

To work on the website:
```bash
cd apps/website
git pull origin main        # Update submodule
# ... make changes ...
git checkout -b feat/my-change
git commit && git push
gh pr create
```

### Brain / Knowledge Base (`brain/`)

The AI Second Brain captures and compounds business knowledge. Key directories:

**Core Context (Critical for Content)**
- `brain/memory/values-beliefs/` - Core values, beliefs, frameworks, principles, POVs
- `brain/memory/style-voice/` - Writing style, tone, vocabulary, structure preferences
- `brain/memory/personal/` - Expertise, services, positioning, differentiators
- `brain/memory/audience/` - Ideal clients, pain points, objections

**Patterns & Examples**
- `brain/memory/patterns/` - Extracted wisdom (grows with each /learn)
- `brain/memory/examples/` - Best-in-class content organized by type

**Knowledge Repository**
- `brain/memory/knowledge-repo/` - Ideas, concepts, insights, research notes

**Experiences (Episodic Memory)**
- `brain/experiences/` - Past project work with plan → output → review → learnings

**Brain Health**
- `brain/brain-health/` - Growth log, pattern confidence, quality metrics

### Docs (`docs/`)

Strategy documents, guides, and playbooks:
- SEO strategy and execution tracking
- Google Ads campaign docs
- Analytics and tracking plans
- Operational playbooks

### Assets (`assets/`)

Shared media files:
- `assets/vehicles/` - Fleet photography (BMW 520i, Cadillac Escalade, GMC Yukon, Lexus, Mercedes Van, Tahoe, Sequoia)

---

## The 4-Command Workflow

```
/plan [task]  →  /work [plan]  →  /review [output]  →  /learn
    ↓               ↓                  ↓                 ↓
 Research       Execute with       6-agent           Extract
 + Plan         todo tracking      quality check     patterns
```

### Command Reference

| Command | Purpose | Time |
|---------|---------|------|
| `/ask [question]` | Quick help with any task | 30 sec |
| `/setup` | Guided brain configuration | 10 min |
| `/plan [task]` | Create systematic execution plan | 2-3 min |
| `/work [plan.md]` | Execute with todo tracking | Varies |
| `/review [output.md]` | 6-agent parallel quality review | 30 sec |
| `/learn` | Extract patterns to memory | 3 min |
| `/recall [topic]` | Search memory for relevant context | 10 sec |
| `/grow` | View brain health metrics | 5 sec |

---

## Git Workflow

This monorepo uses **git submodules** for the website codebase:

```bash
# Clone with submodules
git clone --recurse-submodules git@github.com:noorhatransport/noorha-business.git

# Update website submodule to latest
cd apps/website && git pull origin main && cd ../..
git add apps/website && git commit -m "chore: update website submodule"

# Work on brain/docs (commit directly to this repo)
git add brain/ docs/
git commit -m "brain: add new patterns from project X"
git push
```

---

## Best Practices

1. **Always /plan first** - Never jump straight into work
2. **Complete the cycle** - /plan → /work → /review → /learn
3. **Trust the /review** - 6 agents catch what you miss
4. **Feed the brain** - Run /learn after every project
5. **Check /grow weekly** - See your compound returns
6. **Keep submodule updated** - Pull website changes regularly

---

**Version**: 2.0.0
**Repo**: github.com/noorhatransport/noorha-business
