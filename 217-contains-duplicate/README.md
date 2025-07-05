### 🧾 217. Contains Duplicate

📘 [Leetcode Link](https://leetcode.com/problems/contains-duplicate/)

### 🧩 Real-Life Analogy: Class Roll Check

You're a school teacher checking the roll numbers of students as they enter.  
You have a list like: [101, 104, 103, 101]

### 🎯 Goal

Make sure no student enters more than once.

### ✅ Solution Overview

1. Create a set to store roll numbers seen so far
2. For each student, check if roll number already exists
3. If yes → return True (duplicate found)
4. If not → add to set
5. Return False after full pass if no duplicates

### 💡 Key Concepts

- Hashing (Set)
- Linear Search with Early Exit

### 🧠 Code Solutions

#### 🐍 Python

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        seen = set()
        for num in nums:
            if num in seen:
                return True
            seen.add(num)
        return False
```

#### ☕ Java

```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        Set<Integer> seen = new HashSet<>();
        for (int num : nums) {
            if (seen.contains(num)) return true;
            seen.add(num);
        }
        return false;
    }
}
```
