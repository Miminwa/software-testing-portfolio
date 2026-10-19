# Requirements Review: SauceDemo Online Shop

**Requirements analysis and static testing of an e-commerce checkout journey, with no written specification provided.**

## Key findings
- **8 requirements** identified from the live application, covering login, product browsing, cart, checkout and order confirmation
- **1 defect found before writing a single test case:** the shop allows checkout with an empty cart
- **3 gaps** in the requirements raised as questions for the product team
- **1 requirement** written as a full user story with testable acceptance criteria

## Scope
| | |
|---|---|
| **Application** | [saucedemo.com](https://www.saucedemo.com), a practice e-commerce site |
| **User** | standard_user |
| **Environment** | Chrome on macOS |
| **Date** | 19 October 2026 |
| **Approach** | Explored the full customer journey, wrote the rules the shop should follow, then checked each one |

## Requirements identified
| # | Requirement | Area | Result |
|---|---|---|---|
| R1 | The shop should not let anyone log in without a password | Login | Pass |
| R2 | Sorting should offer name A to Z, name Z to A, price low to high and price high to low, and order products correctly | Products | Pass |
| R3 | The About link should open a page explaining who runs the site | Menu | Pass |
| R4 | Adding a product should put it in the cart, and the cart icon should show the correct number of items | Cart | Pass |
| R5 | The shop should not allow checkout with an empty cart | Cart | **Fail: defect** |
| R6 | Checkout should not continue unless first name, last name and postal code are filled in, with an error for each empty field | Checkout | Pass |
| R7 | Item total should equal the sum of product prices, and Total should equal item total plus tax | Checkout | Pass |
| R8 | After Finish, the shop should confirm the order was placed | Confirmation | Pass |

## Defect found
**R5: Checkout is possible with an empty cart.**
Opening the cart with no products and clicking Checkout continues to the information form and on to the order overview. A shop should block this, because it creates empty orders.
**Severity:** Medium, because orders with no products reach the system, though no money is taken.

## User story: R7, order totals
> **As a** customer, **I want** my order total calculated correctly, **so that** I am never overcharged or undercharged.

**Acceptance criteria**
| # | Criterion | Result |
|---|---|---|
| 1 | Item total equals the prices of all products in the cart added together | Pass |
| 2 | Tax is shown as a separate line | Pass |
| 3 | Total equals item total plus tax | Pass |

**What if…**
- …I remove a product on the overview page? Does the total update?
- …I click Finish twice quickly? Is the order placed only once?
- …I refresh the overview page? Do the totals stay the same?

## Questions for the product team
Gaps where no rule exists, raised as questions rather than defects:
1. Can a customer buy **more than one of the same product**? There is no quantity option.
2. Is there a way to **recover a forgotten password**? There is no "Forgot password" link.
3. Should customers receive an **order receipt** by email after checkout?

## Skills shown
- **Requirements analysis:** working out the rules of a product with no written specification
- **Static testing:** finding a defect and gaps by reviewing behaviour against expected rules
- **Writing user stories and testable acceptance criteria**
- **Separating defects from missing requirements**
