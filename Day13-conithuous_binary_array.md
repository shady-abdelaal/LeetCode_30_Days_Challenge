# Problem
Given a binary array, find the maximum length of a contiguous subarray with equal number of 0 and 1.

Example 1:
```Input: [0,1]
Output: 2
Explanation: [0, 1] is the longest contiguous subarray with equal number of 0 and 1.
```
Example 2:
```Input: [0,1,0]
Output: 2
Explanation: [0, 1] (or [1, 0]) is a longest contiguous subarray with equal number of 0 and 1.
```
Note: The length of the given binary array will not exceed 50,000.


# Code
```python
class Solution(object):
    def findMaxLength(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        accum = 0
        my_dict = {}
        my_dict[0] = -1
        max_length = 0
        for i in xrange(len(nums)):
            if nums[i] == 0:
                accum -= 1
            else:
                accum +=1
            if accum in my_dict:
            
                max_length = max(max_length, (i - my_dict[accum]) )
            else:
                my_dict[accum] = i
        return max_length    
```
