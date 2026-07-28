# Test Summary Report: SauceDemo Manual Testing

**Project:** SauceDemo (saucedemo.com)

**Author:** Matvei Kolmakov

**Date:** [07/27/2026]

**Test Plan:** [test-plan-saucedemo.md](./test-plan-saucedemo.md)

**Test Cases:** [test-cases-saucedemo.xlsx](./test-cases-saucedemo.xlsx)

---

## 1. Summary

Manual functional, comparative, and exploratory testing was performed on SauceDemo, covering login, product sorting, cart, and checkout flows across multiple test accounts (`standard_user`, `problem_user`, `locked_out_user`, `performance_glitch_user`).

## 2. Test Execution Summary

| Metric | Value |
|---|---|
| Total test cases | 14 |
| Passed | 10 |
| Failed | 4 |
| Pass rate | 71.4% |
| Bugs logged | 3 |

## 3. Bugs Found

| ID | Title | Severity | Status |
|---|---|---|---|
| [BUG-001](./bug-reports/BUG-001-mismatched-images/) | Product images incorrect on inventory page (`problem_user`) | Medium | Open |
| [BUG-002](./bug-reports/BUG-002-sorting-not-working/) | Product sorting does not work for `problem_user` | High | Open |
| [BUG-003](./bug-reports/BUG-003-no-input-validation/) | Checkout form accepts any character input, no format validation | Low | Open |

**Severity breakdown:** 1 High · 1 Medium · 1 Low · 0 Critical

## 4. Failed Test Cases (mapped to bugs)

| Test Case | Linked Bug | Observation |
|---|---|---|
| TC-03 (problem_user login/UI check) | BUG-001, BUG-002 | Page behavior differs from `standard_user` |
| TC-04 (performance_glitch_user login) | — | Noticeable load delay (~5s+) vs baseline — flagged as a performance observation, not filed as a formal bug (expected/intentional demo behavior) |
| TC-05b (problem_user sorting) | BUG-002 | Product order never changes regardless of sort option |
| TC-10 (checkout invalid character input) | BUG-003 | Form accepts any character input with no format validation |

## 5. Areas Tested

- ✅ Login (valid, locked-out, problem, performance-glitch accounts)
- ✅ Product sorting (name and price, both directions)
- ✅ Cart (add/remove, badge count, persistence across navigation)
- ✅ Checkout (empty field validation, invalid character input, full flow completion)
- ✅ Logout

## 6. Areas Not Covered (Out of Scope)

- API/backend testing (frontend-only demo, no real backend)
- Load/performance testing
- Payment processing (checkout is simulated)
- Visual comparison testing (`visual_user`) — not included in this test cycle
- Cross-browser testing beyond Chrome (per test plan scope)

## 7. Overall Assessment

Core functional flows (login, cart, checkout) work correctly for `standard_user`. Testing on alternate accounts (`problem_user`, `performance_glitch_user`) surfaced several intentionally-injected demo bugs, which were documented as practice bug reports. No blocking issues were found in the primary user flow with `standard_user`.