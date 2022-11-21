---
layout: editorial
---

# LeetCode

## 1. Sliding Window

```
```





### 643  Maximum Average Subarray I



错误写法，不知道为什么这么写一直超时

{% code title="643  Maximum Average Subarray I" %}
```python
def findMaxAverage(self, nums: List[int], k: int) -> float:
    maxAvg = float('-inf')
    
    if len(nums) == 1 or k == 1:
        return max(sum(nums)/k, maxAvg)
    
    left = 0
    for right in range(left + 3, len(nums)):
        if right - left + 1 > k:
            left += 1
        # while right - left + 1 == k:
        #     maxAvg = max(sum(nums[left:right + 1])/4, maxAvg)
        #为什么这么写会tle
        # if right - left + 1 == k:
        maxAvg = max(sum(nums[left:right + 1])/k, maxAvg)
            
    return maxAvg
        
    # [1, 12, -5, -6, 50, 3]
    # left = 0, right = 3, maxAvg = 0.5
    # right = 4, left = 1, maxavg = 12.75
    # right = 5, left = 2, maxAvg = (12.75, 10.5)python
```
{% endcode %}

