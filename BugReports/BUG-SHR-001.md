# [Bug] Viewer via share link can draw using keyboard shortcuts (permission bypass)

**Project:** SK (Sketcha)  
**Issue Type:** Bug  
**Component(s):** Share & Permissions, Collaboration  
**Severity:** **Major** (access control violation)  
**Priority:** **High**  
**Environment:** Staging – https://staging.sketcha.dev · Chrome 120 (Windows 11, 1920×1080)  
**Build/Version:** v0.1.12-stg (2025-10-08 14:10)

---

## Summary
A user opening a board via a **Viewer** share link can still **create shapes** using **keyboard shortcuts** (R/T/Del…), even though the UI toolbar is disabled.

## Preconditions
- Two accounts: **Owner** and **Viewer**  
- Owner created **Board A** and generated a **Viewer** share link

## Steps to Reproduce
1) Owner: Open **Board A** → **Share** → Generate link (role = **Viewer**)  
2) In an **Incognito** window, open the Viewer link  
3) Press **R** (rectangle) and click on the canvas (or **T** for text, **Del** to delete a shape)  
4) Open **DevTools → Network** (enable **Preserve log**) and observe requests when using shortcuts

## Actual Result
- The Viewer **creates a shape** on the board  
- Network shows `POST /api/shapes` returns **201 Created** with `role: "viewer"` (see HAR)  
- UI toolbar is read-only, but **shortcuts bypass** the restriction

## Expected Result
- Viewer must remain **read-only across all channels**: UI, **shortcuts**, **REST**, **WebSocket**  
- `POST /api/shapes` should return **403 Forbidden**; WS `create_shape` frames should be **rejected**

## Evidence (attachments)
> All tokens/cookies/PII are **redacted** in attached files.

- **Video:** `BUG-SHR-001_viewer_shortcut_creates_shape.mp4`  
- **HAR (redacted):** `BUG-SHR-001_redacted.har`
