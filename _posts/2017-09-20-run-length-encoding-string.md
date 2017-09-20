---
layout: post
title:  "Run-length encoding of a string"
date:   2017-09-17 12:58:27 -0400
category: strings
---

Question : Implement run-length encoding of a string. This is a commonly used technique in image and video compression (and possibly other compression systems). An example to describe run-length encoding :-

```python
Input = "wwwwaaadexxxxxx"
Run length encoded output = w4a3d1e1x6
```

Solution: It is a simple counting exercise - the only catch is to be aware of the last character which does not have anything after it for comparison. Take care of it in a separate if-clause.

```python
def runLengthEncode(inpString) :

    run    = ""
    length = 1
    encString = ""
    strLength = len(inpString)

    for idx in range(strLength):

        curr = inpString[idx]

        if idx == strLength - 1 :
            encString = encString + curr + str(length)
            length = 1
            return encString
        else:
            next = inpString[idx+1]

        if curr == next :
            length += 1
        else :
            encString = encString + curr + str(length)
            length = 1


# calling the function
inpString = "wwwwaaadexxxxxx"
outString = runLengthEncode(inpString)
print("Input : " + inpString)
print("RLE   : " + outString)
```

Do let me know if you have a simpler solution! 
