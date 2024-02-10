# 1. Pattern: Sliding Window

* **Fixed Window Size:**

![](../.gitbook/assets/image.png)

* **Variable Window Size**:
  * Window size can be increase or decrease

The Sliding Window Approach is a powerful technique used in algorithm design, particularly in solving problems involving arrays, strings, or other sequential data structures. It involves maintaining a window of elements within a larger sequence and dynamically adjusting the window as you iterate through the sequence. This approach is useful for optimizing the time complexity of problems by avoiding redundant computations.

**Concept of Sliding Window Approach**:

The Sliding Window Approach typically involves the following steps:

1. **Initialization**: Initialize two pointers, usually representing the start and end of the window, at the beginning of the sequence.
2. **Expansion**: Expand the window by moving the end pointer to the right, adding new elements to the window.
3. **Computation**: Perform computations or checks on the elements within the window.
4. **Shrinking**: If the window violates certain constraints or conditions, shrink the window by moving the start pointer to the right, removing elements from the window.
5. **Updating Result**: Update the result or keep track of the desired information based on the computations performed within the window.
6. **Repeat**: Repeat steps 2-5 until the end of the sequence is reached.

**Applications of Sliding Window Approach**:

The Sliding Window Approach is commonly used in problems involving:

- Subarray or substring problems: Finding a contiguous subarray or substring that satisfies certain conditions (e.g., maximum sum subarray, longest substring without repeating characters).
- Fixed-size window problems: Analyzing a fixed-size window of elements within a sequence (e.g., finding the maximum or minimum value within a window, calculating the average of values within a window).
- Two-pointer technique problems: Problems that can be solved efficiently using two pointers to define a window (e.g., finding pairs in sorted arrays, searching in a sorted array with a specific target sum).

**Types of Problems effectively solved by Sliding Window Approach**:

1. **Maximum Sum Subarray**: Finding the subarray with the maximum sum within a given array.
2. **Longest Substring without Repeating Characters**: Finding the longest substring without repeating characters in a given string.
3. **Minimum Window Substring**: Finding the minimum window in a string that contains all characters of another string.
4. **Longest Subarray with Ones after Replacement**: Finding the longest subarray with all ones after replacing at most 'k' zeroes.
5. **Longest Repeating Character Replacement**: Finding the longest substring with the same characters after replacing at most 'k' characters.

**Step-by-step Thought Process to Identify when to Apply Sliding Window Approach**:

1. **Identify the problem constraints**: Look for problems involving arrays, strings, or sequences where the optimal solution depends on a contiguous subarray or substring.
2. **Check for fixed-size window or substring requirements**: Determine if the problem requires analyzing a fixed-size window of elements within the sequence.
3. **Look for patterns or conditions to optimize**: Identify patterns or conditions within the problem that can be optimized using the Sliding Window Approach, such as finding maximum or minimum values, or satisfying certain conditions within a window.
4. **Consider whether two-pointer technique can be applied**: If the problem involves efficiently scanning through the sequence using two pointers, the Sliding Window Approach might be applicable.
5. **Verify whether the problem can be solved iteratively**: Ensure that the problem can be solved iteratively by dynamically adjusting the window as you iterate through the sequence.

**Example**:

Problem: Given an array of integers and an integer 'k', find the maximum sum of 'k' consecutive elements in the array.

Solution using Sliding Window Approach in Python:

```python
def max_sum_subarray(arr, k):
    max_sum = float('-inf')
    window_sum = 0
    start = 0

    for end in range(len(arr)):
        window_sum += arr[end]
        if end >= k - 1:
            max_sum = max(max_sum, window_sum)
            window_sum -= arr[start]
            start += 1

    return max_sum

# Example usage:
arr = [4, 2, 1, 7, 8, 1, 2, 8, 1, 0]
k = 3
print("Maximum sum of", k, "consecutive elements:", max_sum_subarray(arr, k))
```

In this example, we maintain a sliding window of size 'k' and calculate the sum of elements within the window. As we move the window forward, we keep track of the maximum sum encountered so far. The time complexity of this solution is O(n), where 'n' is the size of the input array.

Overall, the Sliding Window Approach is a versatile technique that can be applied to a wide range of problems, providing efficient solutions with optimal time complexity. It's essential to understand the underlying principles and applications of this approach to effectively tackle algorithmic problems in interviews and coding challenges.
