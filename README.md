# 🚀 Jump Game IX – LeetCode Contest Solution

This repository contains a Python solution to **Jump Game IX**, featured in [LeetCode Weekly Contest 464](https://leetcode.com/contest/weekly-contest-464/problems/jump-game-ix/).

---

## 🧠 Problem Summary

You are given an integer array `nums`. From any index `i`, you can jump to another index `j` under the following rules:

- You can jump to index `j > i` only if `nums[j] < nums[i]` (forward to smaller).
- You can jump to index `j < i` only if `nums[j] > nums[i]` (backward to larger).

Your task is to compute, for each index `i`, the **maximum value** in `nums` that can be reached by following any valid sequence of jumps starting at `i`.

Return an array `ans` where `ans[i]` is the maximum reachable value starting from index `i`.

---

## ✅ Approach

This solution uses a **segment tree + DFS traversal** to efficiently:

- Query the next valid jump index (forward or backward) in logarithmic time.
- Remove visited indices from the segment tree to avoid revisiting.
- Traverse reachable components and assign the maximum reachable value to all nodes in that component.

### Key Techniques

- Segment tree for range min/max queries.
- DFS traversal with pruning.
- Component labeling with max value propagation.

---
## Example Test Cases
Input: nums = [2, 1, 3]
Output: [2, 2, 3]

Input: nums = [2, 3, 1]
Output: [3, 3, 3]

## 📊 Complexity

```markdown
Time Complexity: O(n log n)
- Each segment tree query/update is O(log n)
- Each index is visited once

Space Complexity: O(n)
- Segment tree + visited array + result
