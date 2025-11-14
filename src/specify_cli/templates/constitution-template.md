# MVP Project Constitution

**Purpose of this document:** To ensure maximum development speed and user value delivery while avoiding technical debt that could slow or stop the project in its early stages. This document is our main guide for technical decision-making.

---

## 1. Fundamental Principles (The "Why")

We are guided by three pillars of fast and quality development:

* **KISS (Keep It Simple, Stupid):** Simplicity is our primary goal. A simple solution is easier to implement, test, maintain, and modify. We always choose the simplest path that solves the current task.
* **DRY (Don't Repeat Yourself):** We avoid duplication of business logic. A single source of truth for key operations reduces the number of errors and simplifies making changes.
* **YAGNI (You Ain't Gonna Need It):** We don't write code "just in case." Any functionality that is not required to solve *today's* task is not implemented.

---

## 2. Practical Rules (The "How-To")

These rules are a direct consequence of our principles.

### Code and Architecture
1. **No premature abstractions.** Don't create complex patterns (services, repositories, layers) for a single simple case. Start with the most straightforward code. Refactoring to a pattern is only possible when a *second* real use case appears.
2. **Prefer standard tools.** Instead of adding a new library, first check if the task can be solved using the language's standard library or main framework.
3. **Configuration in code.** Don't create complex configuration systems and admin panels for parameters that change once a year. In an MVP, hardcoded values are normal.
4. **One function - one task.** Functions and methods should be short and do one thing. This simplifies their understanding and testing.

### Dependency Management
5. **Minimal third-party libraries.** Every new dependency is a potential security, performance, and compatibility problem in the future. Add a library only if it saves *days*, not *hours* of development.
6. **Choose proven solutions.** If a dependency is necessary, choose popular and well-maintained libraries, not the newest and most experimental ones.

### Data and State
7. **Simple data schema.** Start with the simplest and flattest possible database structure. Avoid complex relationships and denormalization until it becomes absolutely necessary for performance.
8. **Migrations only forward.** Avoid complex data migrations. It's easier to write a simple one-time conversion script than to maintain a complex schema versioning system at the start.

### Pragmatic Testing
9. **Test the main thing.** 100% test coverage is not a goal for MVP. Focus on integration tests that check key user scenarios (happy path) from start to finish.
10. **Use mocks with caution.** Prefer tests with real (or test) versions of dependencies (e.g., with a test database) rather than with lots of mocks. This better reveals real integration problems.

---

## 3. Litmus Test: Pre-commit Checklist

Before making a commit, ask yourself these questions:

- [ ] Can I make this solution even simpler? (KISS)
- [ ] Have I written this same logic somewhere else? (DRY)
- [ ] Do I *really* need this function right now for the current task? (YAGNI)
- [ ] Is the complexity I'm adding justified?
- [ ] Is the new dependency I'm adding justified?