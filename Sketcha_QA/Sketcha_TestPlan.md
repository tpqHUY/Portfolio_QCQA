# Test Plan / Scope — Sketcha (Collaborative Whiteboard)

**Project:** Sketcha Web App (Realtime collaborative whiteboard)  
**Version/Build:** v0.1-staging (build TBD)  
**Date:** 2025-09-24  
**Owner:** <Your Name>

## 1. Objectives
- Validate critical flows: Authentication, Board CRUD, Real-time collaboration, Drawing tools, Sharing/Permissions, Export/Import.
- Ensure stable real-time syncing (presence, cursors, shapes) under typical team usage (2–5 concurrent users).
- Provide sprint-level pass/fail status and high-signal defect reporting.

## 2. Scope
**In-Scope**
- Web (Desktop-first; responsive checks on mobile/tablet).
- Modules: Auth, Board CRUD, Canvas tools (pen/shapes/text), Layers, Undo/Redo, Zoom/Pan, Comments, Share/Permissions, Presence, Export/Import (PNG/SVG/JSON).
- Browsers/Devices: Chrome 120+, Edge 120+, Firefox 120+; iPadOS Safari (sanity).

**Out-of-Scope**
- Full-scale performance/load testing; SSO/Enterprise IdP; advanced a11y audits; native mobile apps.

## 3. Risks & Assumptions
- **Risks:** Unstable WebSocket server; race conditions on concurrent edits; browser compatibility gaps for pointer events.  
- **Assumptions:** Stable staging URL & WS endpoint; seed users & boards; feature freeze at code-freeze; design tokens final.

## 4. Test Strategy
- **Techniques:** BVA/EP (auth forms), State Transition (board lifecycle), Decision Table (permissions), Exploratory (canvas tools).  
- **Types:** Smoke (health), Functional, Regression (critical paths), Basic responsive checks.  
- **Realtime:** 2–3 concurrent sessions to verify presence, cursor movement, shape sync, comment sync, conflict rules.
- **Entry:** Build on staging, health-check OK, migrations done.  
- **Exit:** No Blocker/Major open; smoke 100% pass; regression ≥ 95% pass; collaboration sync stable in 3 runs.

## 5. Environment
- **Staging URL:** <https://staging.sketcha.example>  
- **WS Endpoint:** wss://staging-ws.sketcha.example  
- **Data:** Seed accounts (owner/editor/viewer), sample boards.  
- **Tools:** Jira, TestRail/Sheet, Confluence, ScreenToGif/Loom, HAR/DevTools.

## 6. Coverage Matrix (sample)
| Module             | Scenarios | Positive | Negative | Edge | Status      |
|-------------------|---------:|---------:|---------:|-----:|-------------|
| Auth              |       10 |        6 |        3 |    1 | In progress |
| Board CRUD        |       10 |        7 |        2 |    1 | Planned     |
| Collaboration     |        8 |        6 |        1 |    1 | Planned     |
| Canvas Tools      |       12 |        8 |        3 |    1 | Planned     |

## 7. Timeline
- D1–D2: Design test cases, set up data.  
- D3–D5: Execute + log defects; 3x realtime sync runs (2–3 users).  
- D6: Regression sweep + Sprint test report.

## 8. Reporting & Metrics
- Daily notes on Confluence; sprint report end-of-week.  
- Metrics: pass rate, defects by severity, reopened rate, flakiness (realtime).

## 9. Evidence Policy
- Attach screenshot/clip for UI defects; HAR/console for sync/API issues; timestamps & session IDs for multi-user runs.

