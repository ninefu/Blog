title: Compare Version Numbers
date: 2016-01-10 12:03:00
categories:
- Leetcode
tags:
- Leetcode
- String
comments: true
---

Compare two version numbers version1 and version2.
If version1 > version2 return 1, if version1 < version2 return -1, otherwise return 0.

You may assume that the version strings are non-empty and contain only digits and the . character.
The . character does not represent a decimal point and is used to separate number sequences.
For instance, 2.5 is not "two and a half" or "half way to version three", it is the fifth second-level revision of the second first-level revision.

Here is an example of version numbers ordering:

0.1 < 1.1 < 1.2 < 13.37

<!--more-->

```java
public class Solution {
    public int compareVersion(String version1, String version2) {
        String[] v1 = version1.split("\\.");
        String[] v2 = version2.split("\\.");
        int length = Math.max(v1.length, v2.length), l1 = v1.length, l2 = v2.length;
        
        for (int i = 0; i < length; i++){
            Integer i1 = (i >= l1) ? 0 : Integer.parseInt(v1[i]);
            Integer i2 = (i >= l2) ? 0 : Integer.parseInt(v2[i]);
            int compare = i1.compareTo(i2);
            if (compare != 0){
                return compare;
            }
        }
        return 0;
    }
}
```