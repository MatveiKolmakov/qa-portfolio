# Bug Report

**Bug ID:** BUG-002

**Title:** Product sorting does not work for `problem_user`

**Reported by:** Matvei Kolmakov

**Date:** [Date]

**Environment:** Chrome (latest), Windows 11

account: `problem_user`

**Severity:** High

**Priority:** High

**Status:** Open

---

## Summary

When logged in as `problem_user`, changing the sort option in the product dropdown (e.g. "Name (A to Z)" → "Name (Z to A)") does not change the order of products on the inventory page. The dropdown selection visually updates, but the underlying product list stays the same.

## Steps to Reproduce

1. Go to https://www.saucedemo.com
2. Log in with username `problem_user` and password `secret_sauce`
3. On the inventory page, note the current product order (default: "Name (A to Z)")
4. Open the sort dropdown and select "Name (Z to A)"
5. Observe the product list

## Expected Result

Selecting "Name (Z to A)" should reverse the product order alphabetically (and similarly, "Price (low to high)" / "Price (high to low)" should sort by price accordingly).

## Actual Result

The product order does not change regardless of which sort option is selected. The dropdown itself shows the selected option correctly, but the list underneath stays in the same order.

## Screenshots

![bug](sorting-not-working.gif)

## Additional Notes

- Confirmed consistent — tested all four sort options (Name A-Z, Name Z-A, Price low-high, Price high-low), none of them change the list order.
- Does **not** occur with `standard_user` — sorting works correctly there for all four options (used as a baseline comparison).
- No visible JS console errors observed during reproduction.
