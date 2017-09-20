---
layout: post
title:  "Check if a string is a rotation of another string"
date:   2017-09-17 12:58:27 -0400
category: strings
---

Question : If you are given two strings, write a program to check if one string is a rotation of the other. Here are a few examples to explain the problem. 

```python
inpString  = "hurricane"  # yes, it's a rotation
outString1 = "icanehurr"  # not a rotation
outString2 = "canehurr"   # not a rotation
outString3 = "canehuirr"  # not a rotation
```

Solution: The intuition is a little tricky - but it is good to keep this in mind. Repeating the first string ends up creating all possible rotations of the string. Try it out for yourself! After you do this, the rest is pretty simple.  

```python
def checkRotation(inpString, testString):
    
    # early exit if the strings are 
    # not of the same length
    if len(inpString) != len(testString):
        return False

    # concatenate the input to itself 
    repString = inpString * 2

    # check if the test string is a substring
    # of the input string
    return ( testString in repString )



# defining test cases
inpString  = "hurricane"
outString1 = "icanehurr"
outString2 = "canehurr"
outString3 = "canehuirr"

result = str(checkRotation(inpString, outString1))
print("First case  : " + result)

result = str(checkRotation(inpString, outString2))
print("Second case : " + result)

result = str(checkRotation(inpString, outString3))
print("Third case  : " + result)
```

Do let me know if you have a simpler solution! 
