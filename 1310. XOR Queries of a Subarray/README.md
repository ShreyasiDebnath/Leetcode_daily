**LINk** : https://leetcode.com/problems/xor-queries-of-a-subarray/description/
Sure! Here's a short explanation using an example:

Given the array `arr = [1, 3, 4, 8]` and queries `[[0, 1], [1, 2], [0, 3]]`, we want to quickly compute the XOR of subarrays.

### Step 1: Construct Prefix XOR Array

- We create a prefix XOR array (`vt`), where each `vt[i]` stores the XOR of all elements from `arr[0]` to `arr[i]`.
  
  `vt = [1, 1^3, 1^3^4, 1^3^4^8] = [1, 2, 6, 14]`

### Step 2: Answer Queries

- **Query `[0, 1]`:** XOR from `arr[0]` to `arr[1]` is `vt[1] = 2`.
- **Query `[1, 2]`:** XOR from `arr[1]` to `arr[2]` is `vt[2] ^ vt[0] = 6 ^ 1 = 7`.
- **Query `[0, 3]`:** XOR from `arr[0]` to `arr[3]` is `vt[3] = 14`.

### Output: `[2, 7, 14]`
