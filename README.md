# Agent Skills

A collection of skills for AI coding agents. Skills are packaged instructions and scripts that extend agent capabilities.

Skills follow the [Agent Skills](https://agentskills.io/) format.

## Available Skills

### nodejs-best-practices

Node.js and Fastify performance, security, and reliability guidelines from Nearform. Contains 48 rules across 8 categories, prioritized by impact.

**Use when:**
- Writing new Node.js APIs or Fastify routes
- Implementing database operations
- Reviewing code for performance or security issues
- Refactoring existing Node.js/Fastify code
- Optimizing API response times
- Setting up monitoring and observability

**Categories covered:**
- Performance & Security (Critical)
- API Design & Database (Critical)
- Error Handling & Logging (High)
- Fastify Optimization (Medium-High)
- Async Patterns (Medium)
- Caching & State (Medium)
- Code Organization (Low-Medium)
- Monitoring & Diagnostics (Low)

## Installation

```bash
npx add-skill nearform/agent-skills
```

## Usage

Skills are automatically available once installed. The agent will use them when relevant tasks are detected.

**Examples:**
```
Review this Fastify route for performance issues
```
```
Help me optimize this Node.js API
```
```
Check my database queries for N+1 problems
```

## Skill Structure

Each skill contains:
- `SKILL.md` - Instructions for the agent
- `AGENTS.md` - Compiled comprehensive guide
- `rules/` - Individual rule files
- `metadata.json` - Skill metadata

## Development

### Building the Skill

```bash
cd packages/nodejs-best-practices-build
pnpm install
pnpm build
```

### Validating Rules

```bash
pnpm validate
```

### Adding New Rules

1. Copy `skills/nodejs-best-practices/rules/_template.md`
2. Follow the naming convention: `prefix-description.md`
3. Add frontmatter and code examples
4. Run `pnpm build` to regenerate AGENTS.md

## License

MIT
