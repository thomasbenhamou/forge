<p align="center">
  <strong>Agent skills for structured, GitHub-centric development.</strong><br>
  One workflow. Six skills. From issue to shipped code.
</p>

<p align="center">
  <a href="docs/architecture.md">Architecture</a> &middot;
  <a href="docs/development.md">Development</a> &middot;
  <a href="docs/coding-guidelines.md">Guidelines</a> &middot;
  <a href="docs/testing.md">Testing</a> &middot;
  <a href="docs/pr-workflow.md">PR Workflow</a>
</p>

---

A forge is where raw material meets intention. You bring the codebase — these skills shape the workflow from issue to implementation to review.

---

## Skills

Forge skills follow the [Agent Skills](https://agentskills.io) open standard and work with any compatible agent.

| Skill | Command | Purpose |
|-------|---------|---------|
| Setup Project | `/forge-setup-project` | Create CLAUDE.md, docs/, README, and other meta-structure |
| Create Issue | `/forge-create-issue` | Collaboratively plan and create GitHub issues |
| Implement Issue | `/forge-implement-issue <number>` | Implement a feature or fix from a GitHub issue |
| Reflect on PR | `/forge-reflect-pr` | Self-review before requesting peer review |
| Address PR Feedback | `/forge-address-pr-feedback` | Address unresolved PR review comments |
| Update Changelog | `/forge-update-changelog` | Update CHANGELOG.md with user-facing changes |

## Workflow

The skills form a pipeline — each step feeds into the next:

```
forge-setup-project → forge-create-issue → forge-implement-issue → forge-reflect-pr → forge-address-pr-feedback → forge-update-changelog
```

## Install

Copy or symlink the skill directories into your agent's skills folder.

### Claude Code

```bash
# All skills (symlink for easy updates)
ln -s /path/to/forge/skills/forge-* ~/.claude/skills/

# Or a single skill
ln -s /path/to/forge/skills/forge-setup-project ~/.claude/skills/forge-setup-project
```

Skills land in `~/.claude/skills/` (personal) or `.claude/skills/` (project-scoped). See [Claude Code docs](https://code.claude.com/docs/en/skills).

### Codex

```bash
ln -s /path/to/forge/skills/forge-* ~/.agents/skills/
```

Skills land in `~/.agents/skills/` (personal) or `.agents/skills/` (project-scoped). See [Codex docs](https://developers.openai.com/codex/skills/).

### Amp

```bash
ln -s /path/to/forge/skills/forge-* ~/.config/agents/skills/
```

Amp also reads from `.agents/skills/` and `.claude/skills/`. See [Amp docs](https://ampcode.com/news/agent-skills).

### pi

```bash
ln -s /path/to/forge/skills/forge-* ~/.pi/agent/skills/
```

Or install as a pi package. See [pi docs](https://github.com/badlogic/pi-mono/tree/main/packages/coding-agent#skills).

### Other agents

Any agent that supports the [Agent Skills](https://agentskills.io) standard can use these skills. Copy the `skills/forge-*` directories into your agent's skills folder.

## Documentation

| Document | Purpose |
|----------|---------|
| [Architecture](docs/architecture.md) | Skill pipeline, file format, design decisions |
| [Development](docs/development.md) | How to create and modify skills |
| [Coding Guidelines](docs/coding-guidelines.md) | Skill authoring conventions and style rules |
| [Testing](docs/testing.md) | How to validate skills manually |
| [PR Workflow](docs/pr-workflow.md) | Commits, PRs, branch naming, review process |

## Contributing

1. Read [CLAUDE.md](CLAUDE.md) for project principles and conventions
2. Follow [docs/coding-guidelines.md](docs/coding-guidelines.md) for skill authoring rules
3. Test your changes by invoking the skill on a real project
4. Use conventional commits: `feat(skills): add new skill`
