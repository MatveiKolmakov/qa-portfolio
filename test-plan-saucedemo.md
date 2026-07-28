# Test Plan: SauceDemo E-commerce Testing (Personal Pet Project)

**Project:** SauceDemo (saucedemo.com)
**Author:** Matvei Kolmakov
**Date:** [07/27/2026]
**Version:** 1.0

---

## 1. Objective

Practice manual QA skills — test design, exploratory testing, and bug reporting — on a realistic e-commerce web application (login, product catalog, cart, and checkout flow).

## 2. Scope

### In Scope
- Login (standard, locked-out, problem, performance-glitch users)
- Product listing page (sorting, filtering, display)
- Product detail page
- Cart functionality (add/remove items, item count)
- Checkout flow (customer info form, order overview, order completion)
- UX/UI and layout across screen sizes
- Basic accessibility checks

### Out of Scope
- Backend/API testing (SauceDemo is frontend-only demo)
- Load/performance testing
- Payment processing (checkout is simulated)

## 3. Test Environment

| Item | Details |
|---|---|
| URL | https://www.saucedemo.com |
| Test accounts | standard_user, locked_out_user, problem_user, performance_glitch_user, error_user, visual_user (password: `secret_sauce` for all) |
| Browsers | Chrome, Firefox, Opera GX (latest) |
| Devices | Desktop, one mobile viewport (via DevTools + real device) |

## 4. Entry Criteria

- SauceDemo site is accessible
- Test accounts (provided publicly by SauceDemo) are available

## 5. Exit Criteria

- All planned test cases and exploratory sessions executed
- All found bugs documented with repro steps and severity
- Test summary report completed

## 6. Test Approach

| Type | Description |
|---|---|
| Functional testing | Login, cart, checkout flows work as expected for standard_user |
| Negative/edge testing | Locked-out user, empty checkout form fields, invalid input |
| Comparative testing | Compare behavior across different test users (problem_user, performance_glitch_user, etc.) — SauceDemo intentionally injects bugs per account |
| UI testing | Layout consistency, sorting behavior, responsiveness |
| Exploratory testing | Timeboxed sessions (~30 min) around cart and checkout to find edge cases |

## 7. Key Test Scenarios

1. Login with standard_user — successful access to inventory page
2. Login with locked_out_user — verify correct error message
3. Login with problem_user — check for UI/behavior bugs (known to have intentional glitches)
4. Login with performance_glitch_user — measure and note load delays
5. Sort products by name (A-Z, Z-A) and price (low-high, high-low) — verify correct order
6. Add single/multiple items to cart — verify cart badge count updates correctly
7. Remove item from cart — verify it's removed from both cart page and inventory page
8. Proceed to checkout with empty required fields — verify validation messages
9. Complete full checkout flow — verify order confirmation page and "Back Home" button
10. Cart persistence — check if cart retains items after navigating between pages
11. Logout — verify redirect to login page and session ends properly
12. Visual check with visual_user — compare UI against standard_user for visual bugs

## 8. Risks & Assumptions

| Risk | Mitigation |
|---|---|
| SauceDemo may change behavior/bugs over time| Note the test date; re-verify scenarios if revisiting later |
| Some bugs are intentional (by design, for practice) | Clearly label findings as "intentional demo bug" in bug reports where relevant |

## 9. Deliverables

- Test cases (spreadsheet or TestRail)
- Bug reports (in portfolio repo)
- Test summary report with overall findings and screenshots