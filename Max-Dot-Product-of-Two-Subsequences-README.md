# leet-day85

## Problem Description

You are given two arrays, `nums1` and `nums2`. You need to find the maximum dot product between non-empty subsequences of these two arrays with the same length.

A subsequence of an array is a new array formed by deleting some (can be none) of the elements without disturbing the relative positions of the remaining elements. The dot product between two arrays of the same length is calculated as follows:

```
DotProduct(nums1, nums2) = nums1[0] * nums2[0] + nums1[1] * nums2[1] + ... + nums1[n-1] * nums2[n-1]
```

You need to find the maximum possible dot product that can be obtained by choosing subsequences from `nums1` and `nums2` while maintaining the relative order of elements in both subsequences.

## Approach

To solve this problem efficiently, we can use dynamic programming. The idea is to create a 2D DP array, `dp`, where `dp[i][j]` represents the maximum dot product of two subsequences starting at the `i`th position of `nums1` and the `j`th position of `nums2`. We will iterate through both arrays, filling in this DP array while maintaining the maximum dot product.

Here are the main steps of the approach:

1. Initialize an `n x m` DP array, where `n` is the length of `nums1`, and `m` is the length of `nums2`.

2. Initialize the first element of the DP array, `dp[0][0]`, as the product of the first elements of `nums1` and `nums2`.

3. Initialize a variable, `maxProduct`, to keep track of the maximum dot product encountered. Initialize it with `dp[0][0]`.

4. Fill in the first row of the DP array by considering subsequences starting at the first element of `nums1` and each element of `nums2`. Update `maxProduct` as needed.

5. Fill in the first column of the DP array by considering subsequences starting at the first element of `nums2` and each element of `nums1`. Update `maxProduct` as needed.

6. Fill in the rest of the DP array. For each cell `dp[i][j]`, calculate the maximum dot product that can be obtained by considering subsequences starting at the `i`th position of `nums1` and the `j`th position of `nums2`. Update `dp[i][j]` and `maxProduct` as needed.

7. The final result is stored in `maxProduct`. Return it as the answer.

## Complexity

The time complexity of this solution is O(n * m), where `n` and `m` are the lengths of `nums1` and `nums2`, respectively.
The space complexity is O(n * m) as well due to the DP array. This solution works efficiently for the given constraints.
