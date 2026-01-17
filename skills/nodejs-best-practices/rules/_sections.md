# Sections

This file defines all sections, their ordering, impact levels, and descriptions.
The section ID (in parentheses) is the filename prefix used to group rules.

---

## 1. Performance & Security (perf)

**Impact:** CRITICAL
**Description:** Performance and security are top priorities. Blocking the event loop, missing security headers, or memory leaks can severely impact application reliability and user trust.

## 2. API Design & Database (api)

**Impact:** CRITICAL
**Description:** Proper API design and database optimization prevent scalability issues and ensure fast response times. Connection pooling and query optimization are essential.

## 3. Error Handling & Logging (error)

**Impact:** HIGH
**Description:** Robust error handling and structured logging enable effective debugging and monitoring in production environments.

## 4. Fastify Optimization (fastify)

**Impact:** MEDIUM-HIGH
**Description:** Fastify-specific patterns leverage the framework's performance benefits through schema validation, hooks, and plugins.

## 5. Async Patterns (async)

**Impact:** MEDIUM
**Description:** Effective async/await usage prevents waterfalls, handles backpressure, and ensures resilient concurrent operations.

## 6. Caching & State (cache)

**Impact:** MEDIUM
**Description:** Caching strategies reduce database load and improve response times through in-memory and distributed caching.

## 7. Code Organization (code)

**Impact:** LOW-MEDIUM
**Description:** Well-organized code improves maintainability, testability, and team collaboration.

## 8. Monitoring & Diagnostics (monitor)

**Impact:** LOW
**Description:** Monitoring and diagnostics enable proactive issue detection and performance optimization in production.
