# Test Plan: Sauce Demo Store

## 1. Objective
Verify that the main customer flows of the demo store work as expected
and document defects found during manual testing.

## 2. Scope
**In scope:**
- Customer login / account
- Product browsing and inventory
- Shopping cart
- Checkout

**Out of scope:**
- Performance and load testing
- Security testing
- Payment processing with real payment methods

## 3. Test Environment
- Application: https://sauce-demo.myshopify.com
- Browser: Google Chrome Versión 158.0.8127.88 (Build oficial) (64 bits)
- Operating system: Windows 10 64 bits
- Device: Desktop

## 4. Test Approach
- Type: manual functional testing
- Each test case has an ID (TC-XXX), steps, expected and actual results
- Failed cases are linked to a bug report (BUG-XXX)

## 5. Entry / Exit Criteria
- **Entry:** the application is accessible and test data is available
- **Exit:** all planned test cases were executed and all failures are documented

## 6. Deliverables
- Test cases (`test-cases.md`)
- Bug reports (see bug reports folder)
- Evidence (screenshots)