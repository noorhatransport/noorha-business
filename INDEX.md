# Noorha Transport — Business Operations Monorepo

> One repo for the entire business: website, knowledge, strategy, and operations.

---

## Directory Index

### `apps/` — Applications
- **[`apps/website/`](./apps/website/)** — noorhatransport.com Next.js codebase (git submodule → github.com/noorhatransport/noorhatransport)

### `brain/` — AI Second Brain
Your semantic and episodic knowledge base that compounds with every project.

- **[`brain/memory/`](./brain/memory/INDEX.md)** — Semantic knowledge
  - [`brain/memory/company/`](./brain/memory/company/) — Products, positioning, differentiators
  - [`brain/memory/customers/`](./brain/memory/customers/) — ICP, pain points, objections
  - [`brain/memory/audience/`](./brain/memory/audience/) — Ideal clients
  - [`brain/memory/personal/`](./brain/memory/personal/) — Expertise, services, positioning
  - [`brain/memory/values-beliefs/`](./brain/memory/values-beliefs/) — Core values, frameworks, principles
  - [`brain/memory/style-voice/`](./brain/memory/style-voice/) — Writing style, tone, vocabulary
  - [`brain/memory/team/`](./brain/memory/team/) — Team members, roles
  - [`brain/memory/decisions/`](./brain/memory/decisions/) — Key business decisions log
  - [`brain/memory/patterns/`](./brain/memory/patterns/) — Extracted wisdom (grows with /learn)
  - [`brain/memory/examples/`](./brain/memory/examples/) — Winning artifacts by type
  - [`brain/memory/knowledge-repo/`](./brain/memory/knowledge-repo/) — Ideas, concepts, research
  - [`brain/memory/projects/`](./brain/memory/projects/) — Active and completed project tracking
- **[`brain/experiences/`](./brain/experiences/INDEX.md)** — Episodic memory (past projects with plan → output → review → learnings)
- **[`brain/brain-health/`](./brain/brain-health/INDEX.md)** — Growth log, pattern confidence, quality metrics
- **[`brain/prompts/`](./brain/prompts/)** — Reusable prompt templates
- **[`brain/projects/`](./brain/projects/INDEX.md)** — Active work in progress

### `assets/` — Shared Media
- **[`assets/vehicles/`](./assets/vehicles/)** — Fleet photography (BMW 520i, Cadillac Escalade, GMC Yukon, Lexus, Mercedes Van, Tahoe, Sequoia)

### `docs/` — Strategy & Documentation
Strategy documents, playbooks, and operational guides. Examples:
- SEO strategy and execution roadmaps
- Google Ads campaign documentation
- Analytics and tracking plans
- Business operations playbooks

---

## Quick Start

### Working on the website
```bash
cd apps/website
git checkout -b feat/my-feature
# make changes
git commit && git push
gh pr create
```

### Working on business operations
```bash
# Brain, docs, assets — commit directly to this repo
git add brain/ docs/
git commit -m "brain: update customer pain points"
git push
```

### Using the AI Brain
```
/plan [task]  →  /work [plan]  →  /review [output]  →  /learn
```

---

## Key Files
- [`CLAUDE.md`](./CLAUDE.md) — Complete usage guide and AI instructions
- [`README.md`](./README.md) — Quick overview
- [`brain/AGENTS.md`](./brain/AGENTS.md) — Agent configurations

---

**Repo**: github.com/noorhatransport/noorha-business
