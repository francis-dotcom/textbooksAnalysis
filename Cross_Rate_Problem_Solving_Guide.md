# Cross-Rate Problem Solving Guide

## 🎯 Core Concepts You MUST Understand

### 1. **What is a Cross-Rate?**
A cross-rate is an exchange rate between two currencies where **neither currency is the US dollar**.

Examples: EUR/GBP, JPY/CHF, CAD/MXN

---

## 📊 Understanding Quote Formats

### American Terms (Direct Quote)
- **Format**: USD per foreign currency
- **Example**: $1.3153/£ means 1 pound costs $1.3153

### European Terms (Indirect Quote)  
- **Format**: Foreign currency per USD
- **Example**: €0.8903/$ means 1 dollar costs €0.8903

### Key Relationship:
```
American Terms = 1 / European Terms
```

---

## 🔑 The Golden Rules for Cross-Rates

### Rule 1: Identify What You're Computing
**Always write out the notation clearly:**
- S(€/£) = "Euros per Pound" = How many euros for 1 pound
- S(£/€) = "Pounds per Euro" = How many pounds for 1 euro

### Rule 2: The Currency Algebra Method
**The currency you want in the NUMERATOR must appear in the NUMERATOR of one of your rates.**

Example: To get S(€/£):
```
You need € in numerator and £ in denominator

Option 1: ($/£) × (€/$) = €/£  ✓
Option 2: (€/$) × ($/£) = €/£  ✓
```

### Rule 3: Cross-Multiply to Cancel USD
**The dollar signs must cancel out!**

---

## 💡 Step-by-Step Problem-Solving Framework

### **SCENARIO 1: Computing Cross-Rate from American Terms**

**Example from slides:**
- £ Bid: $1.3153, Ask: $1.3158
- € Bid: $1.1228, Ask: $1.1233
- **Compute: S(€/£)**

#### Step 1: Write what you need
```
S(€/£) = "How many euros per pound?"
```

#### Step 2: Set up the formula
```
S(€/£) = ($/£) ÷ ($/€)
       = ($/£) × (€/$)
```

#### Step 3: Apply Bid-Ask Logic
**CRITICAL CONCEPT:**
- **Bid rate** = Bank BUYS from you (you get LESS)
- **Ask rate** = Bank SELLS to you (you pay MORE)

**For Cross-Rate BID (bank buys € from you, gives you £):**
- Use £ BID (bank gives you fewer £)
- Use € ASK (you give more €)
```
Cross Bid = £ Bid ÷ € Ask
         = $1.3153 ÷ $1.1233
         = 1.1709 €/£
```

**For Cross-Rate ASK (bank sells € to you, takes your £):**
- Use £ ASK (you give more £)
- Use € BID (bank gives you fewer €)
```
Cross Ask = £ Ask ÷ € Bid
         = $1.3158 ÷ $1.1228
         = 1.1719 €/£
```

---

### **SCENARIO 2: Computing Cross-Rate from Mixed Terms**

**Example from Slide 2:**
- £ (American): Bid $1.3153, Ask $1.3158
- € (European): Bid €0.8903/$, Ask €0.8906/$
- **Compute: S(€/£)**

#### Step 1: Identify what you have
```
$/£ rates (American terms)
€/$ rates (European terms)
```

#### Step 2: Multiply to get €/£
```
S(€/£) = ($/£) × (€/$)
```

#### Step 3: Apply Bid-Ask Logic
**Cross Bid:**
```
= £ Bid × € Bid
= $1.3153 × €0.8903
= 1.1710 €/£
```

**Cross Ask:**
```
= £ Ask × € Ask
= $1.3158 × €0.8906
= 1.1719 €/£
```

---

### **SCENARIO 3: Computing Inverted Cross-Rate (£/€)**

**Example from Slide 4:**
- £ (European): Bid ₤0.7600/$, Ask ₤0.7603/$
- € (American): Bid $1.1228, Ask $1.1233
- **Compute: S(£/€)**

#### Step 1: Set up formula
```
S(£/€) = ($/€) × (£/$)
```

#### Step 2: Apply Bid-Ask Logic
**Cross Bid:**
```
= € Bid × £ Bid
= $1.1228 × ₤0.7600
= 0.8533 £/€
```

**Cross Ask:**
```
= € Ask × £ Ask
= $1.1233 × ₤0.7603
= 0.8540 £/€
```

---

### **SCENARIO 4: Both Currencies in European Terms**

**Example from Slide 5:**
- £ (European): Bid ₤0.7600/$, Ask ₤0.7603/$
- € (European): Bid €0.8903/$, Ask €0.8906/$
- **Compute: S(£/€)**

#### Step 1: Set up formula
```
S(£/€) = (£/$) ÷ (€/$)
```

#### Step 2: Apply Bid-Ask Logic
**Cross Bid:**
```
= £ Bid ÷ € Ask
= ₤0.7600 ÷ €0.8906
= 0.8533 £/€
```

**Cross Ask:**
```
= £ Ask ÷ € Bid
= ₤0.7603 ÷ €0.8903
= 0.8540 £/€
```

---

## 🎓 The Universal Bid-Ask Rule for Cross-Rates

### **When Computing Cross-Rate Bid:**
The bank wants to give you LESS of what you're buying.
- **Divide**: Use numerator BID ÷ denominator ASK
- **Multiply**: Use both BIDs

### **When Computing Cross-Rate Ask:**
The bank wants to take MORE of what you're selling.
- **Divide**: Use numerator ASK ÷ denominator BID
- **Multiply**: Use both ASKs

---

## 📝 Quick Reference Table

| Your Calculation | Formula Type | Cross BID | Cross ASK |
|------------------|--------------|-----------|-----------|
| A/B from $/A and $/B | Division | A_bid ÷ B_ask | A_ask ÷ B_bid |
| A/B from $/A and B/$ | Multiplication | Both bids | Both asks |
| A/B from A/$ and B/$ | Division | A_bid ÷ B_ask | A_ask ÷ B_bid |

---

## ✅ Checklist Before Solving ANY Cross-Rate Problem

1. ☐ **Identify the target**: What cross-rate am I computing? (e.g., €/£)
2. ☐ **Check quote formats**: American or European terms?
3. ☐ **Determine operation**: Multiply or divide?
4. ☐ **Apply bid-ask logic**: Which rates create the worst deal for me?
5. ☐ **Verify units cancel**: Does the math leave me with correct units?
6. ☐ **Sanity check**: Does the bid < ask? (Always true!)

---

## 🚨 Common Mistakes to Avoid

1. **Mixing up bid and ask** - Remember: bid is always lower than ask
2. **Wrong currency order** - S(€/£) ≠ S(£/€)
3. **Forgetting to invert** - When you have European terms but need American (or vice versa)
4. **Not checking units** - Always verify currencies cancel correctly
5. **Using same rates for bid and ask** - Cross bid and ask use DIFFERENT combinations

---

## 🎯 Practice Problem Template

**Given:**
- Currency A: Bid = ___, Ask = ___
- Currency B: Bid = ___, Ask = ___

**Find: S(A/B)**

**Step 1:** Write formula
```
S(A/B) = ?
```

**Step 2:** Determine operation (multiply or divide)

**Step 3:** Calculate Bid
```
Cross Bid = 
```

**Step 4:** Calculate Ask
```
Cross Ask = 
```

**Step 5:** Verify Bid < Ask ✓

---

## 💪 Pro Tips for Exam Success

1. **Always write out the currency notation** - S(€/£) tells you exactly what you need
2. **Draw arrows** - Visualize how currencies cancel
3. **Double-check bid < ask** - If your bid > ask, you made an error
4. **Practice with real data** - Use current exchange rates from xe.com
5. **Memorize the bid-ask rules** - They're the same for every problem

---

## 🔢 Summary Formula Sheet

### Cross-Rate from American Terms ($/A and $/B):
```
S(A/B)_bid = ($/B)_bid ÷ ($/A)_ask
S(A/B)_ask = ($/B)_ask ÷ ($/A)_bid
```

### Cross-Rate from Mixed Terms ($/A and B/$):
```
S(A/B)_bid = ($/A)_bid × (B/$)_bid  
S(A/B)_ask = ($/A)_ask × (B/$)_ask
```

### Cross-Rate from European Terms (A/$ and B/$):
```
S(A/B)_bid = (A/$)_bid ÷ (B/$)_ask
S(A/B)_ask = (A/$)_ask ÷ (B/$)_bid
```
