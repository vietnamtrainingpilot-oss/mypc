# Cleanup Plan

**Generated:** 2026-10-22  
**Phase:** Pending verification (Phase H)  
**Status:** No components removed during this audit (preservation-first approach)  

---

## Current State

| Component | Action | Rationale |
|-----------|--------|-----------|
| ECC plugin | Keep | Installed, verified; beta OpenCode adapter |
| ECC skills | Keep | 486 total; 17+ new; all tested installed |
| ECC commands | Keep | 104 commands; 6 key commands verified |
| ECC agents | Keep | 26 agents + 8 CS agents; all present |
| Superpowers skills | Keep | 223+ unique; no overlap removal |
| Atelier routers | Keep | All 8 preserved (web-design, video, SEO, backend, payments, security, vibe-code, ship-it) |
| Bitwize Music MCP | Keep | Full music pipeline; no ECC equivalent |
| HyperFrames | Keep | HTML-to-video pipeline; no ECC equivalent |
| Roblox Studio MCP | Keep | Studio automation; no ECC equivalent |
| Playwright MCP | Keep | Browser automation; no ECC equivalent |
| computer-use MCP | Keep | Desktop automation; no ECC equivalent |
| uia-mcp | Keep | Windows UI automation; no ECC equivalent |
| Ponytail skills | Keep | YAGNI audit; unique value |
| All MCP servers | Keep | 8 enabled; 1 disabled (21st, requires API key) |

### Files Modified
| File | Change | Backup |
|------|--------|--------|
| `C:\Users\Admin\.config\opencode\opencode.json` | UTF-8 BOM stripped | Preserved at `D:\OpenCode-Ecosystem-Audit\rollback\opencode.json.bak-*` |
| `C:\Users\Admin\.config\opencode\ecc-install-state.json` | Created (install state) | N/A (new file) |
| `C:\Users\Admin\.config\opencode\skills\` | Expanded (176 → 486 dirs) | N/A (new skills added) |
| `C:\Users\Admin\.config\opencode\commands\` | Expanded (7 → 104 files) | N/A (new commands added) |
| `C:\Users\Admin\.config\opencode\agent\` | Created (8 CS + 26 ECC) | N/A (new agents added) |
| `C:\Users\Admin\.config\opencode\instructions\INSTRUCTIONS.md` | Created | N/A (new instructions) |
| `C:\Users\Admin\.config\opencode\plugins\` | Created (5 plugin files) | N/A (new plugins added) |

### Files Created
| File | Path | Size |
|------|------|------|
| README | `D:\OpenCode-Ecosystem-Audit\README.md` | 14,817 bytes |
| Plugin/Skill/MCP Inventory | `D:\OpenCode-Ecosystem-Audit\plugin-skill-mcp-inventory.csv` | 12,138 bytes |
| ECC Capability Matrix | `D:\OpenCode-Ecosystem-Audit\ecc-capability-matrix.md` | 12,352 bytes |
| Overlap & Migration Report | `D:\OpenCode-Ecosystem-Audit\overlap-and-migration-report.md` | Full report |
| Audit Report | `D:\OpenCode-Ecosystem-Audit\audit-report.md` | Full audit |
| Workflow Rankings | `D:\OpenCode-Ecosystem-Audit\workflow-rankings.csv` | Rankings CSV |
| Visual Asset Toolkit | `D:\OpenCode-Ecosystem-Audit\visual-asset-toolkit.md` | Deferred |
| Cleanup Plan | `D:\OpenCode-Ecosystem-Audit\cleanup-plan.md` | This file |
| Dashboard HTML | `D:\OpenCode-Ecosystem-Audit\dashboard.html` | In progress |
| Rollback backups | `D:\OpenCode-Ecosystem-Audit\rollback\` | 10+ timestamped |

---

## Planned Cleanup (Phase H — After Verification)

### Low-Priority Cleanup (Execute After Verification)

| Target | Method | Rationale |
|--------|--------|-----------|
| Duplicate aesthetic skills (`gpt-taste`, `high-end-visual-design`, `minimalist-ui`, `industrial-brutalist-ui`) | Remove 3 of 4 per Atelier "one per job" rule | Atelier design rules state exactly one visual language per job |
| Superpowers cache dirs | `~/.cache/.../superpowers/` | 14 dirs duplicate `~/.agents/skills/` content |
| ECC hook runtime (if enabled later) | `node scripts/install-apply.js --target opencode --no-hooks` | Hooks declined; only enable if truly needed |
| Unused ECC skills (after verification) | Remove per `cleanup-plan.md` skill list | After live testing, remove 1-2 low-value ECC skills |
| Old backup files (>90 days) | `Cleanup-rollback.ps1` | Archive old rollback backups |

### NOT Removing (Preservation Requirements)

| Component | Reason |
|-----------|--------|
| All Atelier routers | Domain-specific; not comparable to ECC general agents |
| Bitwize Music MCP | Full music pipeline; no ECC equivalent |
| HyperFrames/Remotion video | Full pipeline; no ECC equivalent |
| Roblox Studio MCP | Full Studio automation; no ECC equivalent |
| Playwright/computer-use/uia-mcp | Full automation; no ECC equivalent |
| claude-mem + Obsidian | Personal knowledge base; different implementation from ECC |
| Superpowers core skills | 28 skills unique to Superpowers ecosystem |
| Pilot-tail skills | YAGNI audit; unique methodology |
| All MCP servers (8 enabled) | Essential automation tools |

### Rollback Readiness

| Metric | Status |
|--------|--------|
| Backup timestamp | ✅ All files in `rollback/` have `bak-YYYYMMDD-HHmmss` timestamps |
| opencode.json backup | ✅ Preserved at `D:\OpenCode-Ecosystem-Audit\rollback\opencode.json.bak-*` |
| Full state capture | ✅ `ecc-install-state.json` documents all installed components |
| Restoration script | ✅ See `README.md` rollback section |
| Tested restoration | ⏳ Not yet tested (manual restoration recommended) |
| No destructive changes | ✅ All modifications are additive (skills/commands added, not removed) |

### Execution Checklist (Phase H)

- [ ] Verify ECC live session tests pass (pending)
- [ ] If tests pass: execute low-priority cleanup (aesthetic dupes, cache dirs)
- [ ] If tests fail: keep everything as-is; document blockers
- [ ] Update dashboard.html with final state
- [ ] Generate PDF summary if value-add identified
- [ ] Archive this cleanup-plan.md version
- [ ] Document any unresolved risks