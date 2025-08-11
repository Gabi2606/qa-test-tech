# Part 1: Test Case Creation - Cashier System

## Overview

This document contains the detailed test cases designed for the Cashier System.  
The goal is to provide the development team with precise and comprehensive test coverage to ensure correct application of product pricing and discount rules.

---

## Project Structure

- `assets/`  
  Contains configuration files:  
  - `products.yml`: List of products with their codes, names, and prices.  
  - `rules.yml`: List of discount rules applied to products (FreeRule, ReducedPriceRule, FractionPriceRule).

- `tests/`  
  Contains the test cases documentation:  
  - `cashier_test_cases.md`: Detailed test cases covering different scenarios, including happy path, boundary, equivalent partitions, and negative cases.

---

### Special Discount Rules

- **FreeRule**: Buy N products, get N free (Buy One Get One Free)
- **ReducedPriceRule**: Buy more than N products, pay a reduced price per unit
- **FractionPriceRule**: Buy more than N products, pay a percentage of the original price

---

## How to Use

- Review the `products.yml` and `rules.yml` files to understand the product catalog and the discount rules configured.  
- Follow the test cases described in `test/cashier_test_cases.md` to validate the correct behavior of the system.  
- Test cases cover various scenarios to ensure that the system applies pricing rules accurately and handles edge cases properly.

---

## Notes

- This part does not include implementation or automation scripts, only test case design and configuration files. 

---

## Test Case Categories

The test cases are organized according to common ISTQB categories to ensure thorough coverage:

- **Basic Functional (Happy Path):** Validates correct application of rules when conditions are exactly met.  
- **Equivalent Partition:** Tests valid and invalid input classes regarding rule application.  
- **Boundary Cases:** Tests limits and edges of rule application.  
- **Negative Cases:** Verifies the system behavior when rules are not applicable or cart is empty.

# Test Cases - Cashier System

## Organization by Test Case Type (Categories)

**Basic Functional (Happy Path):**

- TC002: Free Rule - Buy 2 Green Teas, Get 1 Free
- TC003: ReducedPriceRule - Buy 3 Strawberries
- TC004: FractionPriceRule - Buy 3 Coffees
- TC005: Combine products with and without rules

**Equivalent Partition (valid/invalid):**

- TC001: Add only 1 product without a discount (class without a rule)
- TC008: Product with no active rule
- TC002, TC003, TC004: represent valid classes with an applied rule
- TC006: Odd quantity in a BOGO rule (Buy One Get One)

**Boundary Cases (Boundary Value Analysis / Edge):**

- TC001: 1 unit (lower limit for SR1 rule)
- TC003: exactly 3 (application limit)
- TC006: odd quantity (for FreeRule)
- TC007: more units than required (validate that applies to all)
- TC009: empty cart

**Negative Cases / Rule Not Applicable:**

- TC001: 1 SR1 unit, discount rule does not apply
- TC008: product with no defined rule
- TC009: empty cart, no error
---

