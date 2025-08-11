## Test Cases

### Test Case ID: TC001  
**Categories**: Equivalent Partition (valid/invalid); Boundary Case; Negative Case  
**Title:** Add 1 Product Without Discount  
**Description:** Verify that the system correctly calculates the price of a product that does not trigger any discount rules.  
**Preconditions:**
- Product `SR1` (Strawberries) registered with price £5.00
- No rules apply with only 1 unit  
**Steps:**  
    1. Start an empty cart.  
    2. Add 1 unit of product `SR1`.  
    3. Calculate the cart total  
**Expected Result:**
- Total: £5.00
- No discount applied

---

### Test Case ID: TC002  
**Categories** Basic Functional (Happy Path); Equivalent Partition (valid).  
**Title:** FreeRule - Buy 2 Green Teas, Get 1 Free.  
**Description:** Verify that when adding 2 units of `GR1`, only 1 is charged due to the “buy one get one free” rule.  
**Preconditions:**
- Product `GR1` (Green Tea) registered with price £3.11
- Active FreeRule: "Buy 1 get 1 free"  
**Steps:**.  
    1. Start empty cart.  
    2. Add 2 units of `GR1`.  
    3. Calculate the total.   
**Expected Result:**. 
- Total: £3.11. 
- 1 unit charged, 1 unit free. 

---

### Test Case ID: TC003  
**Categories**: Basic Functional (Happy Path); Equivalent Partition (valid); Boundary Case.  
**Title:** ReducedPriceRule - Buy 3 Strawberries at a reduced price.  
**Description:** Verify that when purchasing more than 2 units of Strawberries, a reduced price per unit is applied.   
**Preconditions:**
- Product `SR1` registered with standard price £5.00
- Active rule: more than 2 units → each unit costs £4.50   
**Steps:**.  
    1. Start empty cart.  
    2. Add 3 units of `SR1`.  
    3. Calculate total.   
**Expected Result:**
- Total: £13.50
- (3 × £4.50)

---

###  Test Case ID: TC004  
**Categories**: Basic Functional (Happy Path); Equivalent Partition (valid).  
**Title:** FractionPriceRule - Buy 3 Coffees and apply a % discount  
**Description:** Verify that when purchasing more than 2 Coffees, a percentage discount is applied to each unit.  
**Preconditions:**. 
- Product `CF1` (Coffee) registered with price £11.23
- Active rule: more than 2 units → each unit costs 50.00% of the original price
**Steps:**. 
    1. Start empty cart. 
    2. Add 3 units of `CF1`. 
    3. Calculate total.  
**Expected Result:**. 
- Total: £16.83
- (3 × £5.61 approximately)

---

### Test Case ID: TC005
**Categories:** Basic Functional (Happy Path).  
**Title:** Combining Products with and without Discounts.  
**Description:** Verify that the system handles multiple products and correctly applies rules only when appropriate.  
**Preconditions:**. 
- Products `GR1`, `SR1`, `CF1` registered and with their respective rules
**Steps:**  
    1. Add: `GR1`, `GR1`, `SR1`, `SR1`, `SR1`, `CF1`. 
    2. Calculate Total.  
**Expected Result:**. 
- Green Tea: £3.11
- Strawberries: 3 × £4.50 = £13.50
- Coffee: £11.23
- **Expected Total: £27.84**

---

### Test Case ID: TC006 
**Categories**: Equivalent Partition (valid/invalid); Boundary Case.  
**Title:** FreeRule with an odd number of products.  
**Description:** Verify that the system correctly applies "Buy 1 Get 1 Free" when adding an odd number of products.  
**Preconditions:**. 
- Product GR1 with price £3.11
- Active rule: Buy 1 Get 1 Free

**Steps:**.  
    1. Start an empty cart.  
    2. Add 3 units of product `GR1`.  
    3. Calculate the cart total.  
**Expected Result:**. 
- 2 charged (1 free)
- Total: £6.22

---

### Test Case ID: TC007
**Categories**: Boundary Case.  
**Title:** FractionPriceRule with more units than necessary.  
**Description:** Verify that the discount is applied to all units if the minimum is exceeded.
**Preconditions:**   
- Product CF1 with price £11.23
- Active rule: 3 or more units → 50.00% of the price  
**Steps:**.  
    1. Start an empty cart.  
    2. Add 4 units of product `CF1`.  
    3. Calculate the cart total.  
**Expected Result:**. 
- 4 × £5.61 = £22.44
- Total: £22.44

---

### Test Case ID: TC008
**Categories**: Equivalent Partition (invalid); Negative Case.  
**Title:** No rules apply (product not included in rules).  
**Description:** Verify that a product without any rules is charged at the regular price.   
**Preconditions:**. 
- Product XX1, price £2.00
- No rules exist for XX1  
**Steps:**.  
    1. Start an empty cart.  
    2. Add 2 units of product `XX1`.  
    3. Calculate the cart total.  
**Expected Result:**
- Total: £4.00

---

### Test Case ID: TC009
**Categories**: Boundary Case; Negative Case.  
**Title:** Empty Cart.  
**Description:** Verify that the system correctly handles an empty cart.   
**Steps:**.  
    1. Start an empty cart.  
    2. Do not add any products.  
    3. Calculate total.   
**Expected Result:**. 
- Total: £0.00
- No errors, valid but empty cart

---