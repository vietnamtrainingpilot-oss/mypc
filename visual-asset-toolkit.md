# Visual Asset Toolkit

**Generated:** 2026-10-22  
**Status:** Research deferred to follow-up engagement  

---

## Priority: DEFERRED

The dedicated SVG, vector, and website asset pipeline research is deferred to a follow-up phase. The main ECC integration and ecosystem audit are the current priority.

### Research Plan (to be executed)

| Category | Tools to Research | Decision Criteria |
|----------|------------------|-------------------|
| **SVG creation and editing** | Inkscape, SVG-edit, AI-assisted illustration libraries | Editable vector artwork, path editing, gradients, filters, batch asset creation, React integration, export formats |
| **Icon libraries** | Lucide, Tabler Icons, Heroicons, Iconify | Visual consistency, breadth/customization, license, framework compatibility, tree-shaking, bundle size, local availability |
| **SVG optimization and validation** | SVGO, SVGOMG, custom validation pipelines | XML/SVG structure validation, viewBox handling, path simplification, metadata optimization, security sanitization, accessibility, browser rendering |
| **Image-to-vector conversion** | Inkscape tracing, Potrace, VTracer, alternatives | Image preprocessing, vector fidelity, path complexity, file size, batch processing, editability |
| **Animated SVG and motion design** | CSS/SVG animation, Motion, GSAP | Path drawing, morphing, interactive vector elements, timeline-based animation, React integration, reduced-motion support, reusable animations |
| **Website UI and design systems** | shadcn/ui, Tailwind components, Figma integrations | Responsive design, accessibility, code ownership, customization, visual consistency, framework compatibility, dependency size, licensing |
| **Diagrams and data visualization** | Mermaid, D3.js, interactive charts, dashboards | Static website graphics vs interactive data visualizations; editable flowcharts, architecture diagrams |
| **3D, image editing, and video** | Three.js, WebGL, image compressors, background removers, HyperFrames | 3D asset optimization, raster-to-SVG conversion, image preparation, website-to-video workflows |

### Current Setup (Pre-ECC)

| Tool | Purpose | Status |
|------|---------|--------|
| Superpowers skills | General coding, animation, design | Present (untouched by ECC install) |
| Atelier routers | Domain-specific dispatch | Present (8 routers: web-design, video, SEO, backend, payments, security, vibe-code, ship-it) |
| Bitwize Music MCP | Music production pipeline | Present (untouched) |
| HyperFrames | HTML-to-video, motion graphics | Present (untouched) |
| Playwright | Browser automation | Present (untouched) |
| computer-use | Desktop GUI automation | Present (untouched) |
| uia-mcp | Windows UI automation | Present (untouched) |

### Next Steps (Post-ECC Verification)

1. **Research SVG pipeline tools** (Inkscape, SVGO, Lucide, etc.)
2. **Install selected tools** via npm/standalone
3. **Create representative SVG assets** (at least 1)
4. **Validate structure and safety** (security sanitization)
5. **Test browser rendering** (where environment permits)
6. **Document licensing and provenance**
7. **Integrate into isolated website/component**
8. **Test scaling, accessibility, visual quality**
9. **Record provenance and licensing**
10. **Update dashboard with toolkit status**

### Recommended Tool Categories (for future installation)

| Priority | Tool Category | Candidate Tools | License |
|----------|--------------|-----------------|---------|
| P0 | SVG optimization | SVGO, SVGOMG | MIT/Apache |
| P0 | Icon library | Lucide (MIT), Iconify (MIT) | MIT |
| P1 | SVG creation | Inkscape (GPL), SVG-edit (MIT) | GPL/MIT |
| P1 | Animated SVG | CSS keyframes, GSAP, Motion | Various |
| P2 | Diagram/drawing | Mermaid (MIT), D3.js (BSD) | BSD/MIT |
| P2 | 3D/WebGL | Three.js (MIT) | MIT |
| P3 | Image editing | ImageMagick (APL), background removal APIs | Various |

---

## ECC Integration Note

ECC does not currently provide SVG or vector graphics capabilities. The visual asset toolkit is **independent of ECC** and should be researched and installed separately after the main ECC consolidation is verified.

### SVG Pipeline (Planned)

When the SVG toolkit research is complete, the planned pipeline will be:

```
1. Create raw SVG (Inkscape / AI illustration)
2. Optimize (SVGO / SVGOMG — remove unused attrs, simplify paths)
3. Sanitize (security check — remove scripts, event handlers, external refs)
4. Validate (structure check — viewBox, child elements)
5. Convert (image-to-SVG if needed — Inkscape trace)
6. Animate (CSS/SVG animation or GSAP — path drawing, morphing)
7. Test (browser rendering, accessibility, reduced-motion)
8. Integrate (React component, inline SVG, or img tag)
9. Document (licensing, provenance, generation steps)
```

---

## Deferred Deliverable

This report will be expanded in a follow-up engagement after the main ECC ecosystem audit is verified and any planned consolidations are executed. The SVG and asset pipeline research is marked as DEFERRED with a clear roadmap for future execution.