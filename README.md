# QA Portfolio

Personal manual QA practice project - a full testing cycle performed on [SauceDemo](https://www.saucedemo.com), a demo e-commerce site used for QA training. The goal is to demonstrate the core workflow of a manual QA engineer: planning, test design, execution, bug reporting, and summarizing results.

## 📋 Test Plan

[test-plan-saucedemo.md](./test-plan-saucedemo.md) — scope, test environment, approach, key scenarios, and risks.

## ✅ Test Cases

[test-cases-saucedemo.xlsx](./test-cases-saucedemo.xlsx) — 14 test cases covering login, product sorting, cart, and checkout, with Pass/Fail status and a summary of results.

## 🐞 Bugs Found

| ID | Title | Severity | Status |
|---|---|---|---|
| [BUG-001](./Bug-Reports/BUG-001/) | Product images incorrect on inventory page (`problem_user`) | Medium | Open |
| [BUG-002](./Bug-Reports/BUG-002/) | Product sorting does not work for `problem_user` | High | Open |
| [BUG-003](./Bug-Reports/BUG-003/) | Checkout form accepts any character input, no format validation | Low | Open |

Each bug report includes reproduction steps, expected vs. actual results, and a screenshot or GIF.

## 📊 Test Summary Report

[test-summary-report.md](./test-summary-report_2.md) — execution results, bug breakdown by severity, and overall assessment.

## 🛠 Approach

- Manual functional and comparative testing across multiple test accounts (`standard_user`, `problem_user`, `locked_out_user`, `performance_glitch_user`)
- Test design techniques: equivalence partitioning, boundary value analysis
- Bug reports written in Jira-style format
- All testing performed on a public demo site
