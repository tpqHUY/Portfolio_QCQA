# Test Plan / Scope (1–2 pages)

**Project:** <Product Name>  
**Version/Build:** v<1.0.0> (<build id>)  
**Date:** <YYYY-MM-DD>  
**Owner:** <Your Name>

## 1. Objectives
- Validate core flows: <Auth>, <CRUD>, <Checkout>, <i18n>, <Responsive>.
- Detect critical defects before UAT/release.
- Provide clear pass/fail status each sprint.

## 2. Scope
**In-Scope**
- <Web/Mobile/Game> features: <Module A, Module B, ...>
- Browsers/Devices: <Chrome 120, Edge 120, iPhone 14 iOS 17, ...>
- Test types: Smoke, Functional, Regression (critical paths), Exploratory.

**Out-of-Scope**
- <e.g., Performance Load Test>, <3rd party billing sandbox>, <Legacy module X>.

## 3. Risks & Assumptions
- Risks: <tight sprint timeline>, <unstable QA env>, <test data resets>.
- Assumptions: <stable staging URL>, <test accounts available>, <feature freeze at code-freeze date>.

## 4. Test Strategy
- **Design techniques:** BVA, EP, State Transition, Decision Table.
- **Entry/Exit criteria:**  
  - Entry: build deploys to staging; basic health-check passes.  
  - Exit: no **Blocker/Major** open; smoke 100% pass; regression ≥ 95% pass.
- **Evidence:** Screenshots/video; console/network logs for web; device logs for mobile.

## 5. Environment
- **Env:** Staging — <URL> — <commit hash/build id>  
- **Data:** seed users, test credit cards, locales.  
- **Tools:** Jira, TestRail, Confluence, Postman, Git, ScreenToGif/Loom.

## 6. Test Coverage Matrix (example)
| Module | Scenarios | Positive | Negative | Edge | Status |
|---|---:|---:|---:|---:|---|
| Auth | 12 | 7 | 4 | 1 | In progress |
| CRUD Items | 20 | 12 | 6 | 2 | Planned |

## 7. Timeline
- Design test cases: <D1–D3>  
- Execute + log defects: <D4–D6>  
- Regression + report: <D7>

## 8. Reporting
- Daily test notes on Confluence; Sprint report on last day.  
- Metrics: pass rate, defect count by severity, reopened rate.

