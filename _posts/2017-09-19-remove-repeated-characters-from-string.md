---
layout: post
title:  "Remove repeated characters from a string"
date:   2017-09-19 08:00:00
categories: strings
---

Question : Let's suppose that you are given an input string that might contain characters that are repeated. Can you design an algorithm that scans the input and removes any repeated characters and returns the trimmed string. In this case, you don't have to worry whether the characters are repeated consecutively or not. Here is an example :-
```
inpString = "my name is unique to me"
outString = "my naeisuqto" // this preserves the order
outString = "a eimonqsuty" // this does not preserve the order
```

Solution: This can be solved in O(n) using a set to hold the unique characters. If we want to preserve the order, then we can simultaneously insert the unique characters into a list and present that as the output. Here are both versions. 

```python
# ----------------------
# preserve the order
# ----------------------
inpString = "my name is unique to me"

outputList = list()
tempSet    = set()
counter    = 0

for ch in inpString:
    
    if ch not in tempSet:
        tempSet.add(ch)
        outputList.insert(counter, ch)
        counter += 1
    else:
        continue

print("Input string  : " + inpString)
print("Output string : " + "".join(outputList))
```



```python
# ----------------------
# don't preserve the order
# ----------------------

inpString = "my name is unique to me"

tempSet = set()
counter = 0

for ch in inpString:
    
    if ch not in tempSet:
        tempSet.add(ch)
        counter += 1
    else:
        continue

print("Input string  : " + inpString)
print("Output string : " + "".join(tempSet))
```


And here is a quick way to do this if we don't have to preserve the order. The idea is to create two sets populated with the input string and then find the intersection of these two sets. This will give us only the unique elements -- right?

```
inpString = "my name is unique to me"
print("".join(set(inpString) & set(inpString)))
```

Do let me know if you have a simpler solution! 
