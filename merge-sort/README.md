# Merge Sort

## 🔁 Rule: Divide - Sort - Merge

Merge Sort is a classic **Divide and Conquer** algorithm.
It works by recursively breaking down the array into the smallest possible subarrays (of size 1), and then merging them back together in a sorted manner.

---

## 📌 Steps

1. **Divide**: Split the array into halves until each subarray has only one element.
2. **Sort**: The subarrays of size 1 are inherently sorted.
3. **Merge**: Combine the sorted subarrays into larger sorted arrays until the whole array is sorted.

---

## 📈 Time Complexity

| Case        | Time Complexity |
|-------------|-----------------|
| Best Case   | O(n log n)      |
| Average Case| O(n log n)      |
| Worst Case  | O(n log n)      |

### Explanation:
- Divide the array into halves every time (log n levels deep).
- At each level, you merge all elements back together (n work).

Total Work = (log n levels) * (n work per level)
           = O(n log n)


**Quick Memory Trick to Remember:** "n for merge, log n for levels", So n × log n

---

## 💾 Space Complexity

- **O(n)** - bacause it requires temporary arrays during the merge process.

---

## ✅ Example

Given an array: `[38, 27, 43, 3, 9, 82, 10]`

Steps:

- Divide: (log n levels)
    - Level 0: **array size = n (original array)**
        - `[38, 27, 43, 3, 9, 82, 10]`
    - Level 1: split into: **array size = n/2, n/2**
        - `[38, 27, 43]` and `[3, 9, 82, 10]`
    - Level 2: split further: **array size = n/4, n/4, n/4, n/4** 
        - `[38]`, `[27, 43]` and `[3, 9]`, `[82, 10]`
    - Level 3: final split: **array size = n/8, n/8, ... (8 pieces)**
        - `[38]`, `[27]`, `[43]` and `[3]`, `[9]`, `[82]`, `[10]`
    
    **Each subarray is of size one, recursion base case reached.**

-  Now, the Merge and Sort Phase:
    - Step 1: Compare and Merge adjacent pairs
        - `[27]` and `[43]`    →    `[27, 43]`
        - `[3]` and `[9]`      →    `[3, 9]`
        - `[82]` and `[10]`    →    `[10, 82]`

        Now we have: `[38] [27, 43]` and `[3, 9] [10, 82]`

    - Step 2: Merge again
        - `[38]` and `[27, 43]` -> `[27, 38, 43]`
        - `[3, 9]` and `[10, 82]`   -> `[3, 9, 10, 82]`

        Now we have:  `[27, 38, 43]` and `[3, 9, 10, 82]`

    - Step 3: Final Merge
        - `[27, 38, 43]` and `[3, 9, 10, 82]`   -> `[3, 9, 10, 27, 38, 43, 82]`
    
    **Final sorted array = `[3, 9, 10, 27, 38, 43, 82]`**

## Pseudo-code

```
function mergeSort(arr):
    # Base case: if the array has 1 or 0 elements, it's already sorted
    if arr size <= 1:
        return arr
    
    # Find the middle index to split the array
    mid = middle index

    # Recursively split and sort both halves
    left = mergeSort(left half)
    right = mergeSort(right half)

    # Merge the sorted halves and return
    return merge(left, right)

function merge(left, right):
    # Initialize an empty list to store the sorted result
    result = empty list

    # Loop until either left or right is exhausted
    while left and right both have elements:
        # Append the smaller element to result and remove it
        if left[0] < right[0]:
            append left[0] to result
            remove left[0]
        else:
            append right[0] to result
            remove right[0]
    
    # Add any remaining elements (if any) from left or right to result
    append all remaining elements of left to result
    append all remaining elements of right to result

    # Return the merged, sorted array
    return result
```