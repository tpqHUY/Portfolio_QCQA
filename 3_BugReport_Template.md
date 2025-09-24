# Bug Report Template

**Title:** [<Platform>][<Module>] <Concise problem>  
**Environment:** <OS/Browser/Device>, App/Web version, Build ID, Staging URL  
**Severity/Priority:** Blocker/Major/Minor | High/Medium/Low  
**Pre-conditions:** <accounts, seed data, feature flags>

## Steps to Reproduce
1. <step>
2. <step>
3. <step>

**Actual Result:** <what happens>  
**Expected Result:** <what should happen>  
**Evidence:** <screenshot/video/logs links>  
**Notes/Attachments:** <network HAR, console logs, device logs>

---

## Example
**Title:** [Mobile][Login] "Sign in" button stays disabled after valid input  
**Environment:** Android 14 (Pixel 6), App v1.2.3 (build 45), Staging  
**Severity/Priority:** Major | High  
**Pre-conditions:** User exists and verified

### Steps
1. Launch app → Login screen.
2. Enter valid email + password.
3. Observe "Sign in" button remains disabled.

**Actual:** Button disabled, cannot proceed.  
**Expected:** Button enabled when inputs valid.  
**Evidence:** video + logcat snippet attached.  
**Notes:** Repro 4/5; likely form validation race condition.

