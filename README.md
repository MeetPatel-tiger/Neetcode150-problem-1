# Neetcode150-problem-1- Contains Duplicate



##  Problem Statement

The task is to determine whether an integer list contains any duplicate values. If any value appears at least twice, the function should return `True`; otherwise, it should return `False`.



##  Thought Process

When approaching this problem, I began by asking clarifying questions: what happens if the list is empty, or what if it contains only a single element? In both cases, duplicates would be impossible. This helped me set a clear foundation for edge cases.

My first approach was a brute force solution. I compared every element with every other element using nested loops. This method worked, but it was inefficient. The time complexity was O(n²) since each element was compared against all others, while the space complexity was O(1) because no additional data structures were used. One issue I initially faced was comparing elements starting at the same index, which always returned `True`. I fixed this by offsetting the inner loop index.

To improve performance, I turned to an optimized approach using a hash set. By looping through the list once, I could check whether each element had already been seen. If it had, the function would return `True`; otherwise, the element was added to the set. This reduced the time complexity to O(n), though it increased the space complexity to O(n) because of the additional data structure. This tradeoff was worthwhile because the solution became much faster and passed all test cases.

I also explored an alternative solution using sorting. By sorting the array first, duplicate elements would become neighbors. Then, by scanning through the list once, I could detect duplicates by comparing consecutive elements. This approach had a time complexity of O(n log n) due to the sorting step but only required O(1) extra space. It was more efficient than brute force but slower than the hash set approach.

---

## Final Code (Python)

```python
def containsDuplicate(nums):
    seen = set()
    for num in nums:
        if num in seen:
            return True
        seen.add(num)
    return False
```

---

## 🎯 Key Takeaways

I began with a brute force solution and then refined it to a more efficient approach using a hash set. Along the way, I practiced thinking like I would in an interview: starting with clarifying questions, implementing a baseline solution, and then moving toward optimization while considering tradeoffs. This problem reinforced the importance of analyzing both time and space complexity and gave me confidence in systematically solving coding interview challenges.
