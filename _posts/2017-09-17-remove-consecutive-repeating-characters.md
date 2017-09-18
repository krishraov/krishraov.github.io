---
layout: post
title:  "Remove consecutive repeating characters in a string"
date:   2017-09-17 12:58:27 -0400
categories: strings
---

{% highlight python %}
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
{% endhighlight %}
