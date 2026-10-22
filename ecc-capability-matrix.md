# ECC Capability Matrix

**Generated:** 2026-10-22
**ECC Version:** 2.2.3
**Target:** OpenCode (Beta adapter)

---

## Overview

ECC provides 71 agents, 311 skills, and 97 legacy command shims. This matrix documents what ECC actually provides in the OpenCode integration and how it compares to existing tooling.

**OpenCode Support Status:** Beta (capability-limited adapter per ECC documentation)

---

## Capability-by-Capability Mapping

### 1. Planning & Implementation

| ECC Capability | Implementation | OpenCode Compat | Test Performed | Result | Existing Overlap | Migration Decision | Limitations |
|---------------|----------------|-----------------|----------------|--------|------------------|-------------------|-------------|
| `/plan` command | `commands/plan.md` + planner agent | ✅ Native | Not yet run | Pending | Superpowers: `make-plan`, `writing-plans` | **CONSOLIDATE** — Use ECC for planning, Superpowers for brainstorming | OpenCode beta: some prompt templates may not render correctly |
| `/tdd` command | `commands/tdd.md` + tdd-guide agent | ✅ Native | Not yet run | Pending | Superpowers: `test-driven-development` | **REPLACE WITH ECC** — ECC has more comprehensive TDD enforcement (80%+ coverage) | Same as above |
| `/code-review` command | `commands/code-review.md` + code-reviewer agent | ✅ Native | Not yet run | Pending | Superpowers: `requesting-code-review`, `receiving-code-review` | **REPLACE WITH ECC** — ECC agent-based review is more thorough | Same as above |
| `/build-fix` command | `commands/build-fix.md` + build-error-resolver agent | ✅ Native | Not yet run | Pending | None | **INSTALL NOW** — Unique ECC capability for build error resolution | TypeScript/JS focused |
| `/security` command | `commands/security.md` + security-reviewer agent | ✅ Native | Not yet run | Pending | Superpowers: `claude-security` skill + CS scan agents | **KEEP BOTH** — ECC security is general-purpose; CS is repository scanning | Same as above |
| `/refactor-clean` command | `commands/refactor-clean.md` + refactor-cleaner agent | ✅ Native | Not yet run | Pending | Superpowers: `oh-my-issues` (different scope) | **INSTALL NOW** — Unique ECC capability | Same as above |

### 2. Agents / Delegation

| ECC Agent | Purpose | OpenCode Compat | Test Performed | Result | Existing Overlap | Migration Decision | Limitations |
|-----------|---------|-----------------|----------------|--------|------------------|-------------------|-------------|
| `build` | Primary coding agent | ✅ Native | Not yet run | Pending | None | **INSTALL NOW** — ECC's default agent | Replaces some manual workflow |
| `planner` | Implementation planning | ✅ Native | Not yet run | Pending | Superpowers `make-plan` | **CONSOLIDATE** — Use ECC planner for structured plans | Same as plan command |
| `architect` | System design | ✅ Native | Not yet run | Pending | None | **KEEP** — Unique architecture agent | - |
| `code-reviewer` | Code quality/security review | ✅ Native | Not yet run | Pending | Superpowers `requesting-code-review` | **REPLACE** — ECC agent is more comprehensive | - |
| `security-reviewer` | Security vulnerability detection | ✅ Native | Not yet run | Pending | Superpowers `claude-security` | **KEEP BOTH** — Different depth/focus | - |
| `tdd-guide` | Test-driven development | ✅ Native | Not yet run | Pending | Superpowers `test-driven-development` | **REPLACE** — ECC enforces 80%+ coverage | - |
| `build-error-resolver` | Build/TypeScript error fixes | ✅ Native | Not yet run | Pending | None | **INSTALL NOW** — Unique capability | - |
| `e2e-runner` | End-to-end Playwright testing | ✅ Native | Not yet run | Pending | None | **INSTALL NOW** — Unique Playwright integration | - |
| `doc-updater` | Documentation/codemaps | ✅ Native | Not yet run | Pending | None | **INSTALL NOW** — Unique documentation agent | - |
| `refactor-cleaner` | Dead code cleanup | ✅ Native | Not yet run | Pending | None | **INSTALL NOW** — Unique capability | - |
| `loop-operator` | Autonomous loop execution | ✅ Native | Not yet run | Pending | None | **KEEP** — Unique autonomous loop capability | May require hooks (declined) |
| `harness-optimizer` | Harness config tuning | ✅ Native | Not yet run | Pending | None | **KEEP** — Unique optimization agent | - |
| `docs-lookup` | Context7 documentation lookup | ✅ Native | Not yet run | Pending | None | **KEEP** — Unique documentation agent | Requires Context7 MCP |

### 3. Specialized Language Agents

| ECC Agent | Language | OpenCode Compat | Migration Decision | Notes |
|-----------|----------|-----------------|-------------------|-------|
| `go-reviewer` / `go-build-resolver` | Go | ✅ Native | **INSTALL** | Unique Go-specific review |
| `java-reviewer` / `java-build-resolver` | Java | ✅ Native | **INSTALL** | Unique Java-specific review |
| `kotlin-reviewer` / `kotlin-build-resolver` | Kotlin | ✅ Native | **INSTALL** | Unique Kotlin-specific review |
| `python-reviewer` | Python | ✅ Native | **INSTALL** | Unique Python-specific review |
| `rust-reviewer` / `rust-build-resolver` | Rust | ✅ Native | **INSTALL** | Unique Rust-specific review |
| `cpp-reviewer` / `cpp-build-resolver` | C++ | ✅ Native | **INSTALL** | Unique C++-specific review |
| `ruby-reviewer` | Ruby | ✅ Native | **INSTALL** | Unique Ruby-specific review |
| `php-reviewer` | PHP | ✅ Native | **INSTALL** | Unique PHP-specific review |

### 4. Skills Inventory

#### ECC-New Skills (not in existing ecosystem)
| Skill | Purpose | Value | Priority |
|-------|---------|-------|----------|
| `tdd-workflow` | TDD methodology enforcement | High | P0 |
| `security-review` | Security vulnerability scanning | High | P0 |
| `coding-standards` | Code quality standards | Medium | P1 |
| `frontend-patterns` | React/Next.js patterns | Medium | P1 |
| `backend-patterns` | Server-side patterns | Medium | P1 |
| `e2e-testing` | Playwright E2E testing | High | P1 |
| `api-design` | REST/GraphQL API design | Medium | P2 |
| `verification-loop` | Automated verification | High | P1 |
| `unified-memory` | ECC memory system | Medium | P2 (overlap with claude-mem) |
| `continuous-learning` | Session learning | Low | P3 (overlap with claude-mem) |
| `hookify` | Hook configuration | Low | P3 |
| `terminal-opener` | Terminal management | Low | P3 |
| `mcp-server-patterns` | MCP development | Medium | P2 |
| `gan-style-harness` | GAN-based style analysis | Low | P4 |
| `cost-tracking` | Token/cost monitoring | Medium | P2 |
| `token-card` | Token budget management | Medium | P2 |
| `token-budget-advisor` | Token optimization | Medium | P2 |
| `prompt-optimizer` | Prompt refinement | Medium | P2 |
| `search-first` | Research methodology | Medium | P2 |
| `deep-research` | Deep web research | Medium | P2 |

#### ECC-Overlapping Skills (exist in both ECC and existing)
| Skill | ECC Source | Existing Source | Verdict |
|-------|-----------|-----------------|---------|
| `make-plan` | ✅ | Superpowers | Keep both — ECC version may be enhanced |
| `brainstorming` | ✅ | Superpowers cache | Keep both |
| `systematic-debugging` | ✅ | Superpowers cache | Keep both |
| `verification-before-completion` | ✅ | Superpowers cache | Keep both |
| `writing-plans` | ✅ | Superpowers cache | Keep both |
| `executing-plans` | ✅ | Superpowers cache | Keep both |
| `requesting-code-review` | ✅ | Superpowers | Keep both |
| `receiving-code-review` | ✅ | Superpowers | Keep both |
| `using-superpowers` | ✅ | Superpowers cache | Keep both |
| `subagent-driven-development` | ✅ | Superpowers | Keep both |
| `do` | ✅ | Superpowers | Keep both |
| `ponytail` | ✅ | Ponytail plugin | Keep both — different implementations |
| `ponytail-audit` | ✅ | Ponytail plugin | Keep both |
| `ponytail-debt` | ✅ | Ponytail plugin | Keep both |
| `ponytail-gain` | ✅ | Ponytail plugin | Keep both |
| `ponytail-help` | ✅ | Ponytail plugin | Keep both |
| `ponytail-review` | ✅ | Ponytail plugin | Keep both |
| `web-design` | ✅ | Atelier | Keep both — different implementations |
| `video-production` | ✅ | Atelier | Keep both |
| `seo` | ✅ | Atelier | Keep both |
| `backend` | ✅ | Atelier | Keep both |
| `payments` | ✅ | Superpowers | Keep both |
| `ship-it` | ✅ | Superpowers | Keep both |
| `vibe-code` | ✅ | Superpowers | Keep both |
| `security` | ✅ | Superpowers | Keep both |
| `animate` | ✅ | Emil Kowalski | Keep both |
| `review-animations` | ✅ | Emil Kowalski | Keep both |
| `improve-animations` | ✅ | Emil Kowalski | Keep both |
| `hyperframes` | ✅ | HeyGen | Keep both |
| `hyperframes-*` | ✅ | HeyGen | Keep both |

---

## OpenCode-Specific Limitations

Per ECC documentation, the following capabilities are **not available** or **limited** in OpenCode:

| Capability | Claude Code | OpenCode | Notes |
|-----------|-------------|----------|-------|
| Native hooks | Full support | Plugin events only | `tool.execute.before/after`, `session.created/deleted` |
| Skill discovery | Automatic | Manual (via paths config) | Needs `skills.paths` in opencode.json |
| Agent definitions | Native `agent/` dir | Native `agent/` dir ✅ | Works as expected |
| Command templates | Native | Native ✅ | Works as expected |
| Instruction injection | Native | Via `instructions` array | Works as expected |
| Memory/Learning | Built-in | Plugin-based | Different implementation |
| AgentShield scanning | Full | Partial | Limited to installed skills |
| Full catalog | 311 skills | Subset (~310 installed) | Most skills installed, some excluded |

### Known Issues
1. **#2617** — "connect a provider and select a model in OpenCode" — model selection must be verified
2. **UTF-8 BOM** — installer fails on BOM-encoded config files (fixed in this audit)
3. **Hook runtime** — declined during install; no automatic source modification
4. **Continuous learning v2** — observer daemon has open Windows defects (#2489, #2626)

---

## Verification Status

| Test | Status | Evidence |
|------|--------|----------|
| ECC repo cloned | ✅ | `/tmp/ecc-src/` exists with 4627 files |
| npm install succeeds | ✅ | 220 packages installed |
| build:opencode succeeds | ✅ | `.opencode/dist/` generated |
| Install applies without error | ✅ | `ecc-install-state.json` written |
| Skills directory expanded | ✅ | 176 → 486 (+310) |
| Commands available | ✅ | 104 commands in `commands/` |
| Agents present | ✅ | 8 CS + 26 ECC agents |
| Plugin files written | ✅ | `ecc-hooks.ts` in `plugins/` |
| opencode.json not overwritten | ✅ | Preserved existing config |
| Backup preserved | ✅ | `rollback/opencode.json.bak-*` exists |
| Hooks runtime declined | ✅ | `hookConsent: "declined"` in state |
| Model provider connectivity | ⏳ Pending | Requires live opencode session |
| Skill invocation test | ⏳ Pending | Requires live opencode session |
| Agent delegation test | ⏳ Pending | Requires live opencode session |
| Command execution test | ⏳ Pending | Requires live opencode session |

---

## Recommendations

### Immediate (P0)
1. **Verify model provider** — Ensure `freellmapi/auto` works with ECC commands
2. **Test `/plan` command** — Run in a test project to verify planning workflow
3. **Test `/tdd` command** — Verify TDD enforcement
4. **Test `/code-review` command** — Verify review quality

### Short-term (P1)
5. **Enable ECC instructions** — Add `instructions/INSTRUCTIONS.md` to opencode.json if desired
6. **Test agent delegation** — Verify `build`, `planner`, `architect` agents work
7. **Evaluate hook runtime** — Consider enabling if automated workflows are needed

### Long-term (P2)
8. **Consider removing duplicate skills** — After verification, remove 1-2 overlapping skills per category
9. **Configure ECC memory** — Decide between ECC unified-memory vs claude-mem
10. **Evaluate cost-tracking** — Monitor token usage with ECC commands

---

## Rollback Reference

If ECC causes issues:
```powershell
# Restore opencode.json
Copy-Item "D:\OpenCode-Ecosystem-Audit\rollback\opencode.json.bak-*" `
          "C:\Users\Admin\.config\opencode\opencode.json" -Force

# Remove ECC-added skills (keep Superpowers/Atelier/Ponytail/Bitwize/HyperFrames)
# See README.md for full rollback script
```
