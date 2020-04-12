# Code
```python
class Solution(object):
    def lastStoneWeight(self, stones):
        """
        :type stones: List[int]
        :rtype: int
        """
        sorted_stones = sorted(stones, reverse = True)
        while len(sorted_stones) > 1:
            sorted_stones = sorted(sorted_stones, reverse = True)
            if (sorted_stones[0] == sorted_stones[1]):
                del(sorted_stones[1])
                del(sorted_stones[0])
            else:
                sorted_stones.append(sorted_stones[0] - sorted_stones[1])
                del(sorted_stones[1])
                del(sorted_stones[0])
                
                
        if len(sorted_stones) == 0:
            return 0
        else:
            return sorted_stones[0]
   ```
