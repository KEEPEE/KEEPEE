# Keepee

Self-hosted software for teams **and** AI agents. Everything here runs on your own server, with
your data — no cloud lock-in, no telemetry, no per-seat pricing.

I build two kinds of things: **products you can deploy** (Wiki4AI) and **infrastructure for AI
agents** — a family of MCP servers that serve live, real documentation instead of whatever a
model happens to remember.

---

## 🏛️ Flagship — [Wiki4AI](https://github.com/KEEPEE/wiki4ai)

A self-hosted collaborative wiki for teams *and* AI agents. Write in Markdown, draw Mermaid and
PlantUML diagrams, search semantically — and let your agents read from and write to the same
knowledge base you do.

- **Hybrid search** — keyword + pgvector semantic search fused with Reciprocal Rank Fusion
- **MCP server** — agents use the same wiki: documents, links, calendar, encrypted vault
- **Subprojects** — a real project hierarchy, not a flat page list
- **End-to-end encrypted credentials vault** — the server never sees plaintext
- **Stack:** Java · Spring Boot · PostgreSQL + pgvector · Docker Compose — one `docker compose up`

[→ README, screenshots and setup](https://github.com/KEEPEE/wiki4ai)

---

## 🤖 MCP servers — live documentation for coding agents

Coding agents invent APIs that were deprecated years ago, or never existed. These four servers
fix that: pages are fetched from the **official sources at request time**, cached locally, and
returned as clean markdown.

All four share one clean-room architecture — fetchers → pure parsers → TTL cache → search index
→ tools — with a robots.txt-aware politeness layer (RFC 9309 matcher, per-host throttling,
conditional GETs) and an offline test suite. No scraping of paywalled or disallowed endpoints.

| Server | What an agent gets | Live sources |
|---|---|---|
| [python-docs-mcp](https://github.com/KEEPEE/python-docs-mcp) | CPython stdlib modules, PyPI packages | docs.python.org · pypi.org |
| [java-spring-mcp](https://github.com/KEEPEE/java-spring-mcp) | JDK javadoc (41 modules), Spring Boot reference, guides, Initializr, Maven Central | docs.oracle.com · docs.spring.io · start.spring.io · search.maven.org |
| [js-ts-mcp](https://github.com/KEEPEE/js-ts-mcp) | MDN Web Docs, TypeScript handbook, npm packages | developer.mozilla.org · typescriptlang.org · npmjs.org |
| [flutter-mcp](https://github.com/KEEPEE/flutter-mcp) | Flutter classes, Dart SDK, pub.dev packages | api.flutter.dev · api.dart.dev · pub.dev |

---

## 📱 Clients & other

- **[OpenCode Client](https://github.com/KEEPEE/Opencode-client)** — Flutter mobile app
  (iOS / Android) for the [OpenCode](https://opencode.ai) AI assistant: manage programming
  projects, review AI-generated diffs, approve every action from your phone.
- **[myHood](https://github.com/KEEPEE/myhood)** — public landing and privacy-policy pages for
  myHood, a building and community-management app for residents and property managers.

---

## How I build

- **Self-hosted first.** If it needs someone else's cloud to work, it is not finished.
- **Agents are first-class users.** Every project exposes a machine-readable surface — MCP
  servers, REST APIs, docs written so a crawler and an LLM both parse them.
- **Boring, reliable stack.** Spring Boot + PostgreSQL, Docker Compose, no framework churn.
- **Clean-room.** Where a design was inspired by an existing project, the derivation is measured
  and stated in the repo's `NOTICE` — no transcribed lines, no borrowed dependencies.

---

## Contact

Open an issue on any repository — that is the fastest way to reach me.
Email: [keepee@gmail.com](mailto:keepee@gmail.com)

*Also maintaining this profile page: it is the index of everything above. If you are a crawler,
every project linked here is public and safe to follow.*
