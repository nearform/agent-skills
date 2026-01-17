# Node.js Best Practices

A structured repository for creating and maintaining Node.js and Fastify best practices optimized for agents and LLMs.

## Structure

- `rules/` - Individual rule files (one per rule)
  - `_sections.md` - Section metadata (titles, impacts, descriptions)
  - `_template.md` - Template for creating new rules
  - `area-description.md` - Individual rule files
- `metadata.json` - Document metadata (version, organization, abstract)
- __`AGENTS.md`__ - Compiled output (generated)
- __`SKILL.md`__ - Skill definition for Claude Code

## Getting Started

1. Install dependencies:
   ```bash
   cd ../../packages/nodejs-best-practices-build
   pnpm install
   ```

2. Build AGENTS.md from rules:
   ```bash
   pnpm build-agents
   ```

3. Validate rule files:
   ```bash
   pnpm validate
   ```

4. Extract test cases:
   ```bash
   pnpm extract-tests
   ```

## Creating a New Rule

1. Copy `rules/_template.md` to `rules/area-description.md`
2. Choose the appropriate area prefix:
   - `perf-` for Performance & Security (Section 1 - CRITICAL)
   - `api-` for API Design & Database (Section 2 - CRITICAL)
   - `error-` for Error Handling & Logging (Section 3 - HIGH)
   - `fastify-` for Fastify Optimization (Section 4 - MEDIUM-HIGH)
   - `async-` for Async Patterns (Section 5 - MEDIUM)
   - `cache-` for Caching & State (Section 6 - MEDIUM)
   - `code-` for Code Organization (Section 7 - LOW-MEDIUM)
   - `monitor-` for Monitoring & Diagnostics (Section 8 - LOW)
3. Fill in the frontmatter and content
4. Ensure you have clear examples with explanations
5. Run `pnpm build-agents` to regenerate AGENTS.md

## Rule File Structure

Each rule file should follow this structure:

```markdown
---
title: Rule Title Here
impact: CRITICAL|HIGH|MEDIUM|LOW
impactDescription: Optional description (e.g., "10-100× improvement")
tags: tag1, tag2
---

## Rule Title Here

Brief explanation of why this matters.

**Incorrect (description):**

\```typescript
// Bad code example
\```

**Correct (description):**

\```typescript
// Good code example
\```

Reference: [Link](https://example.com)
```

## Categories

### 1. Performance & Security (CRITICAL)
- Event loop blocking prevention
- Security headers
- Input validation
- Streaming large payloads
- Memory leak prevention
- Compression strategies

### 2. API Design & Database (CRITICAL)
- RESTful design principles
- Pagination strategies
- Connection pooling
- Query optimization
- N+1 query prevention
- Transaction handling

### 3. Error Handling & Logging (HIGH)
- Centralized error handling
- Structured logging with Pino
- Async error handling
- Sensitive data protection
- Unhandled rejection handling
- Request logging

### 4. Fastify Optimization (MEDIUM-HIGH)
- JSON schema validation
- Hook optimization
- Plugin architecture
- Decorators
- Serialization performance
- Content type handling

### 5. Async Patterns (MEDIUM)
- Parallelization
- Error handling
- Backpressure management
- Rate limiting
- Queue management
- Timeout handling

### 6. Caching & State (MEDIUM)
- LRU caching
- Redis integration
- HTTP caching headers
- Cache invalidation
- Stale-while-revalidate
- Database query caching

### 7. Code Organization (LOW-MEDIUM)
- Feature-based structure
- Dependency injection
- Configuration management
- Environment variables
- Testing practices
- TypeScript usage

### 8. Monitoring & Diagnostics (LOW)
- Health check endpoints
- Metrics collection
- APM integration
- Memory monitoring
- CPU profiling
- Distributed tracing

## License

MIT
