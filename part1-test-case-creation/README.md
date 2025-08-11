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

The product data and rules are loaded from YAML configuration files located in the `assets/` folder.

---

## Test Case Categories

The test cases are organized according to common ISTQB categories to ensure thorough coverage:

- **Basic Functional (Happy Path):** Validates correct application of rules when conditions are exactly met.  
- **Equivalent Partition:** Tests valid and invalid input classes regarding rule application.  
- **Boundary Cases:** Tests limits and edges of rule application.  
- **Negative Cases:** Verifies the system behavior when rules are not applicable or cart is empty.

---

## How to Use

- Review the `products.yml` and `rules.yml` files to understand the product catalog and the discount rules configured.  
- Follow the test cases described in `test/cashier_test_cases.md` to validate the correct behavior of the system.  
- Test cases cover various scenarios to ensure that the system applies pricing rules accurately and handles edge cases properly.

---

## Notes

- This part does not include implementation or automation scripts, only test case design and configuration files.  