---
layout: post
title:  "Remove consecutive repeating characters in a string"
date:   2017-09-17 12:58:27 -0400
categories: strings
---

Question : Let's suppose that you are given an input string that might contain characters that are repeated. Can you design an algorithm that scans the input and removes any consecutively repeated characters and returns the trimmed string. It's easier to describe this with an example :-
```
inpString = "aabbcc"
outString = "abc"

inpString = "aabbccabc"
outString = "abcabc"
```

Solution: The solution is pretty easy. All you have to do is (1) scan the string character by character, (2) check if a character is the same as the next character, (3) decide what to do if it equal or not to the next character. You can do this in O(n) without allocating any new space.  

```python
inpstr = "aabbccfffff"
strlist = list(inpstr)

length   = len(strlist)
writeCtr = 0

for index in range(length-1):
    if index == 0 :
        strlist[writeCtr] = strlist[index]
        writeCtr = writeCtr + 1
    elif strlist[index] == strlist[index+1]:
        continue
    else:
        strlist[writeCtr] = strlist[index + 1]
        writeCtr = writeCtr + 1


outStr = strlist[0:writeCtr]


# printing the input and output
print("Input string  : " + inpstr)
print("Output string : " + "".join(outStr))
```

Do let me know if you have a simpler solution! 
