# 💹 122. Best Time to Buy and Sell Stock II

📘 [Leetcode Link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/)

---

### 🧩 Real-Life Analogy: Street Vendor Profit Strategy

Imagine you're a street vendor buying and selling lemons.  
You can buy and sell as many times as you want — but you **must sell before buying again**.  
To make maximum profit, you buy when prices are low and sell whenever there's a rise.

---

### 🎯 Goal

Given an array of prices, determine the **maximum profit** you can achieve  
by making **as many transactions as you like** — but **never hold more than one stock at a time**.

---

### ✅ Solution Overview

1. Loop through the prices
2. If today's price is **greater than yesterday's**, sell and take profit
3. Accumulate profit every time there's an upward slope
4. No need to find valleys/peaks — just grab all positive differences

---

### 💡 Key Concepts

- Greedy Algorithm
- Peak-Valley Approach Simplified
- Maximize Gain on Every Increment

---

### 🧠 Code Solutions

#### 🐍 Python

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        profit = 0
        for i in range(1, len(prices)):
            if prices[i] > prices[i - 1]:
                profit += prices[i] - prices[i - 1]
        return profit
```

#### ☕ Java

```java
class Solution {
    public int maxProfit(int[] prices) {
        int profit = 0;
        for (int i = 1; i < prices.length; i++) {
            if (prices[i] > prices[i - 1]) {
                profit += prices[i] - prices[i - 1];
            }
        }
        return profit;
    }
}
```

#### 🧠 C++

```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int profit = 0;
        for (int i = 1; i < prices.size(); ++i) {
            if (prices[i] > prices[i - 1])
                profit += prices[i] - prices[i - 1];
        }
        return profit;
    }
};
```

#### 🌐 JavaScript

```javascript
var maxProfit = function(prices) {
    let profit = 0;
    for (let i = 1; i < prices.length; i++) {
        if (prices[i] > prices[i - 1]) {
            profit += prices[i] - prices[i - 1];
        }
    }
    return profit;
};
```

---

### 🧩 Step-by-Step Breakdown

Let’s walk through this input:  
📥 prices = [7, 1, 5, 3, 6, 4]

- Day 1 → 1 → Day 2 → 5 → ✅ Buy @1, Sell @5 → Profit: 4  
- Day 3 → 3 → Day 4 → 6 → ✅ Buy @3, Sell @6 → Profit: 3  
- Total Profit = 4 + 3 = 7

We skip any days where price goes down.

---

### 🏁 Output

✅ 7 — maximum profit from multiple transactions

---