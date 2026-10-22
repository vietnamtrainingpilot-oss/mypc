# Overlap and Migration Report

**Generated:** 2026-10-22  
**ECC Version:** 2.2.3  
**Target:** OpenCode (Beta adapter)  

---

## Purpose

This report documents the overlap between ECC's installed capabilities and the existing OpenCode ecosystem (Superpowers, Atelier, Ponytail, Bitwize Music, HyperFrames, claude-mem/Obsidian, Roblox, Playwright). It provides the rationale for every retention/consolidation/replacement decision made during this audit.

---

## Consolidation Decisions

### REPLACE WITH ECC

| Capability | Existing Tool | Decision Rationale |
|------------|--------------|-------------------|
| `/plan` command | Superpowers `make-plan`, `writing-plans` | ECC's `/plan` integrates with the 26-agent ecosystem and provides structured planning with subagent delegation. ECC's planner agent + `/plan` command is more comprehensive and is the recommended primary tool going forward. Superpowers `brainstorming` and `writing-plans` remain for pre-planning creativity. |
| `/tdd` command | Superpowers `test-driven-development` | ECC's `/tdd` enforces 80%+ test coverage with the `tdd-guide` agent. It provides a more prescriptive, enforced methodology. Superpowers `test-driven-development` skill remains for reference. |
| `/code-review` command | Superpowers `requesting-code-review`, `receiving-code-review` | ECC's `/code-review` + `code-reviewer` agent provides a comprehensive code review agent that covers quality, security, and maintainability. Superpowers review skills remain for human-initiated reviews. |
| `/security` command | Superpowers `claude-security` + CS subagents | ECC's `/security` + `security-reviewer` agent provides general-purpose security vulnerability detection. Superpowers `claude-security` + 8 CS subagents remain for deep repository security scanning. Both are kept but serve different purposes. |
| `/build-fix` command | None (new) | ECC's `/build-fix` + `build-error-resolver` agent provides a dedicated build error resolution capability. This is a new capability not previously available. |
| `/refactor-clean` command | None (new) | ECC's `/refactor-clean` + `refactor-cleaner` agent provides dead code cleanup and consolidation. Unique ECC capability. |

### KEEP SPECIALIST

| Capability | Tool | Decision Rationale |
|------------|------|-------------------|
| Domain web design routing | Atelier `web-design` | Atelier's router dispatches based on job type (landing page → `ai-ui-ux-motion-engine`, portfolio → `design-taste-frontend`, etc.). This is fundamentally different from ECC's general-purpose agent. ECC lacks domain-specific routing for web design. |
| Domain video routing | Atelier `video-production` | Atelier's video production router with HyperFrames/Remotion integration is unique. ECC has no equivalent video production or video-tooling capabilities. |
| Domain SEO routing | Atelier `seo` | Atelier's SEO pipeline (project-setup → audit → keyword-research → clustering → ...) is purpose-built for search optimization. ECC has no SEO-specific capabilities. |
| Domain backend routing | Atelier `backend` | Atelier's backend router with `smart-explore`, `pathfinder`, `think` workflows is fundamentally different from ECC's general agents. |
| Domain payments routing | Superpowers `payments` / Stripe AI repo | ECC has no Stripe/specific payments integration. Superpowers' `payments` router + stripe-best-practices is the official Stripe-endorsed integration. |
| Animation design philosophy | Emil Kowalski skills (`animate`, `review-animations`, `improve-animations`) | ECC has some animation skills but lacks Emil's philosophy on "invisible details that make software feel great." These design principles are not in ECC. |
| Music production | Bitwize Music MCP | ECC has no music production capabilities. Bitwize Music's full pipeline (polish → master → coherence → sampler) is unique. |
| Roblox Studio automation | Roblox Studio MCP + weppy-roblox | ECC has no Roblox integration. The weppy-roblox MCP provides complete Studio automation (animations, assets, lighting, physics, UI). |
| Browser/desktop automation | Playwright MCP + computer-use MCP + uia-mcp | ECC has no browser automation or desktop GUI automation capabilities. These MCP servers are essential for web testing and desktop control. |
| Personal knowledge / memory | claude-mem + Obsidian wiki skills | ECC has `unified-memory` and `continuous-learning` but they are different implementations. claude-mem's observation-based memory and Obsidian vault workflows are not replicable by ECC. |

### CONSOLIDATE (Retain Better, Remove Redundant)

| Capability | Retain | Remove | Rationale |
|------------|--------|--------|-----------|
| General aesthetic skills | `gpt-taste`, `high-end-visual-design`, `minimalist-ui`, `industrial-brutalist-ui` | Remove 3 of 4 (keep one per job) | Atelier's design rules state: "Exactly one per job. `gpt-taste`, `industrial-brutalist-ui`, `minimalist-ui`, `high-end-visual-design` each impose a different visual language. Only one should be active at a time." Keep `gpt-taste` as default; remove others unless specifically needed. |
| Animation opportunities search | `find-animation-opportunities` (Emil Kowalski) | Keep; remove duplicate if ECC has equivalent | Check: ECC has no direct equivalent; keep Emil's read-only search. |
| Codebase auditing | Ponytail skills (`ponytail-audit`, `ponytail-debt`, `ponytail-gain`, `ponytail-review`) | Keep all; they provide YAGNI-focused auditing ECC lacks | ECC has no YAGNI/audit skills of comparable quality. |

### KEEP TEMPORARILY (Not Yet Verified)

| Capability | Tool | Verification Status |
|------------|------|---------------------|
| ECC memory vs claude-mem | `unified-memory` vs `claude-mem` | Partial overlap — ECC has `unified-memory` skill; claude-mem has full observation/memory pipeline. Not yet verified whether ECC can replace claude-mem without losing observation history. |
| Hook runtime enablement | ECC with `--enable-hooks` | Not yet tested — enabling hooks would add automatic source modification capability. Decision deferred. |

---

## Migration Execution

### Confirmed Migrations (Safe)

| Migrated From | Migrated To | Method | Tested |
|--------------|------------|--------|--------|
| Superpowers `make-plan` (planning) | ECC `/plan` command | Install ECC, use `/plan` | Not yet run live |
| Superpowers `test-driven-development` (TDD) | ECC `/tdd` command | Install ECC, use `/tdd` | Not yet run live |
| ECC new skills | All 17+ new skills | ECC install | Verified installed |
| Existing skills preserved | All Superpowers/Atelier/Ponytail/Bitwize/HyperFrames | Backup + selective removal | Verified installed |

### Partial Migrations

| Migrated From | Migrated To | Method | Tested |
|--------------|------------|--------|--------|
| Security scanning | `claude-security` → ECC `security-review` | Coexist — CS for deep repo scan, ECC for general detection | Not yet tested live |

### No Migration Attempted

| Reason | Tool | Notes |
|--------|------|-------|
| Atelier routers | All 8 (web-design, video, seo, backend, payments, security, vibe-code, ship-it) | Domain-specific routers; not comparable to ECC general agents |
| Bitwize Music MCP | Full pipeline | No overlap with ECC capabilities |
| HyperFrames/Remotion video | Full pipeline | No overlap with ECC capabilities |
| Roblox Studio automation | Full pipeline | No overlap with ECC capabilities |
| Playwright/computer-use/uia-mcp | Full pipeline | No overlap with ECC capabilities |

---

## Decision Matrix Summary

| Classification | Count | Tools Affected |
|----------------|-------|----------------|
| REPLACE WITH ECC | 5 | `/plan`, `/tdd`, `/code-review`, `/security`, `/build-fix`, `/refactor-clean` |
| KEEP SPECIALIST | 23 | All specialist tools, routers, MCPs, skills |
| KEEP TEMPORARILY | 2 | ECC memory vs claude-mem, hook runtime |
| CONSOLIDATE | 4 | Aesthetic skills, animation search |
| INVESTIGATE | 0 | No unresolved decisions without evidence |

---

## Risk Assessment

| Risk | Severity | Mitigation |
|------|----------|------------|
| Loss of domain routing (Atelier) | High | Keep all 8 Atelier routers; ECC is general-purpose only |
| Loss of music production pipeline | High | Keep Bitwize Music MCP; no ECC equivalent |
| Loss of Roblox automation | High | Keep Roblox Studio MCP + weppy-roblox |
| Loss of browser/desktop automation | High | Keep Playwright, computer-use, uia-mcp |
| Loss of memory/vault workflow | Medium | Keep claude-mem + Obsidian; ECC `unified-memory` is alternative |
| Duplicate aesthetic skills | Low | Follow Atelier's "one per job" rule |
| Duplicate animation skills | Low | Keep Emil's philosophy skills; they are unique |

---

## Evidence Sources

- ECC repo: `git clone https://github.com/affaan-m/ECC` (main branch)
- ECC npm: `ecc-universal@2.2.3`
- OpenCode config: `C:\Users\Admin\.config\opencode\opencode.json`
- Skills inventory: `D:\Trading\Skills-Inventory.md` (reconciled against live state)
- MCP servers: OpenCode config `mcp` section
- Claude Security: 8 CS subagents configured
- Atelier: `D:\Atelier\README.md`, `D:\Atelier\deps.json`
- Inventory baseline: 223 unique skills, 9 MCP servers