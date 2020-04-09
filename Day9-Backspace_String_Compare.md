# Backspace String:

Given two strings S and T, return if they are equal when both are typed into empty text editors. # means a backspace character.

Example 1:

```Input: S = "ab#c", T = "ad#c"
Output: true
Explanation: Both S and T become "ac".
```

Example 2:

```Input: S = "ab##", T = "c#d#"
Output: true
Explanation: Both S and T become "".
```
Example 3:

```Input: S = "a##c", T = "#a#c"
Output: true
Explanation: Both S and T become "c".
```
Example 4:

```Input: S = "a#c", T = "b"
Output: false
Explanation: S becomes "c" while T becomes "b".
```
Note:

1 <= S.length <= 200
1 <= T.length <= 200
S and T only contain lowercase letters and '#' characters.
Follow up:

Can you solve it in O(N) time and O(1) space?



# Code

```python
class Solution(object):
    def backspaceCompare(self, S, T):
        """
        :type S: str
        :type T: str
        :rtype: bool
        """
        s_list = list(S)
        t_list = list(T)
        s_stack = []
        t_stack = []
        for counter, value in enumerate(s_list):
            if value == "#":
                if len(s_stack) != 0:
                    del(s_stack[-1])
            else:
                s_stack.append(value)
                
        
        for counter, value in enumerate(t_list):
            if value == "#":
                if len(t_stack) != 0:
                    del(t_stack[-1])
            else:
                t_stack.append(value)
                
        
        return s_stack == t_stack
```

How about some code clean up? Maybe there are some useful methods that we can use?
