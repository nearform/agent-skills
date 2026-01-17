# AGENTS.md

This file provides guidance to AI coding agents (Claude Code, Cursor, Copilot, etc.) when working with code in this repository.

## Repository Overview

A collection of Node.js best practices skills for AI coding agents from Nearform. Skills are packaged instructions and comprehensive guides that help agents write better Node.js and Fastify code.

## Skills in This Repository

### nodejs-best-practices

A comprehensive skill containing 48 rules across 8 categories for Node.js and Fastify development:

- **Performance & Security** (Critical): Event loop, security headers, input validation, streaming, memory leaks, compression
- **API Design & Database** (Critical): RESTful design, pagination, connection pooling, query optimization, N+1 prevention, transactions
- **Error Handling & Logging** (High): Centralized errors, structured logging, async errors, sensitive data protection
- **Fastify Optimization** (Medium-High): Schema validation, hooks, plugins, decorators, serialization
- **Async Patterns** (Medium): Parallelization, error handling, backpressure, rate limiting, queues, timeouts
- **Caching & State** (Medium): LRU cache, Redis, HTTP headers, cache invalidation
- **Code Organization** (Low-Medium): Module structure, dependency injection, configuration, testing, TypeScript
- **Monitoring & Diagnostics** (Low): Health checks, metrics, APM, memory/CPU profiling, distributed tracing

## Working with Skills

### Building the Skill

```bash
cd packages/nodejs-best-practices-build
pnpm install
pnpm build
```

This compiles all individual rule files from `skills/nodejs-best-practices/rules/` into a single `AGENTS.md` comprehensive guide.

### Adding New Rules

1. Copy the template: `skills/nodejs-best-practices/rules/_template.md`
2. Name with appropriate prefix:
   - `perf-` for Performance & Security
   - `api-` for API Design & Database
   - `error-` for Error Handling & Logging
   - `fastify-` for Fastify Optimization
   - `async-` for Async Patterns
   - `cache-` for Caching & State
   - `code-` for Code Organization
   - `monitor-` for Monitoring & Diagnostics
3. Fill in the frontmatter (title, impact, tags)
4. Add incorrect and correct code examples
5. Run `pnpm build` to regenerate AGENTS.md

### Validating Rules

```bash
cd packages/nodejs-best-practices-build
pnpm validate
```

This checks that all rule files have correct frontmatter, examples, and formatting.

## Repository Structure

```
skills/
  nodejs-best-practices/
    SKILL.md              # Skill definition for agents
    AGENTS.md             # Compiled comprehensive guide (generated)
    metadata.json         # Skill metadata
    README.md             # Developer documentation
    rules/
      _sections.md        # Section definitions
      _template.md        # Rule template
      perf-*.md           # Performance & Security rules
      api-*.md            # API Design & Database rules
      error-*.md          # Error Handling & Logging rules
      fastify-*.md        # Fastify Optimization rules
      async-*.md          # Async Patterns rules
      cache-*.md          # Caching & State rules
      code-*.md           # Code Organization rules
      monitor-*.md        # Monitoring & Diagnostics rules

packages/
  nodejs-best-practices-build/
    src/
      build.ts            # Builds AGENTS.md from rules
      validate.ts         # Validates rule files
      parser.ts           # Parses rule frontmatter and content
      extract-tests.ts    # Extracts test cases
```

## Guidelines for AI Agents

When working with this repository:

1. **Follow the existing structure**: Rules are organized by category prefix
2. **Maintain consistent formatting**: Use the template for new rules
3. **Provide real-world examples**: Show both incorrect and correct code
4. **Focus on Node.js/Fastify**: Examples should use Node.js, Fastify, or framework-agnostic patterns
5. **Include impact metrics**: Quantify improvements where possible (e.g., "10-100× faster")
6. **Reference authoritative sources**: Link to official Node.js, Fastify, or library documentation
7. **Use TypeScript**: Code examples should use TypeScript for type safety
8. **Test your changes**: Run `pnpm validate && pnpm build` before committing

## Contributing

This repository is maintained by Nearform. When adding or modifying rules:

1. Ensure the rule follows Nearform's Node.js expertise and best practices
2. Focus on production-grade patterns used in real-world applications
3. Consider performance, security, and reliability equally
4. Prioritize rules that prevent common mistakes or critical issues
5. Build and validate before creating a pull request
