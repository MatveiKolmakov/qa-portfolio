# Bug Report

**Bug ID:** BUG-003

**Title:** Checkout form accepts any character input (no format validation)

**Reported by:** Matvei Kolmakov

**Date:** [Date]

**Environment:** Chrome (latest), Windows 11

account: `standard_user`

**Severity:** Low

**Priority:** Medium

**Status:** Open

---

## Summary

The "Checkout: Your Information" form does not validate the format or character set of its input fields. Entering Cyrillic characters into First Name, Last Name, and Zip/Postal Code is accepted without any error, allowing the user to proceed to the next step.

## Steps to Reproduce

1. Go to https://www.saucedemo.com
2. Log in with username `standard_user` and password `secret_sauce`
3. Add any product to the cart and go to the cart page
4. Click "Checkout"
5. On the "Checkout: Your Information" page, enter Cyrillic text into First Name, Last Name, and Zip/Postal Code (e.g. "Иван", "Иванов", "123456" in Cyrillic-style input)
6. Click "Continue"

## Expected Result

The form should either validate the expected format for each field (e.g. Zip/Postal Code should only accept valid postal code characters) or, at minimum, the accepted input format should be clearly documented/implied by field labels. Accepting arbitrary scripts in a Zip Code field without validation is unexpected.

## Actual Result

The form accepted Cyrillic input in all three fields (First Name, Last Name, Zip Code) with no validation error, and the user was allowed to proceed to the "Checkout: Overview" page.

## Screenshots

![bug](checkout-cyrillic-input.png)

## Additional Notes

- Only "field is not empty" appears to be validated — no format, character set, or locale validation was found on any of the three fields.
- Not tested whether this also applies to `problem_user` or other accounts — likely applies to all, since this is a shared form component.
- Low severity since it doesn't break functionality or cause errors downstream, but worth flagging as a data-quality/validation gap.
