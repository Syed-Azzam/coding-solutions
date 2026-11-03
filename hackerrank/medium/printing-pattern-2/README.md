# Bitwise Operators

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

## Problem

Print a pattern of numbers from $1$ to $n$ as shown below.  Each of the numbers is separated by a single space.    

                                4 4 4 4 4 4 4  
                                4 3 3 3 3 3 4   
                                4 3 2 2 2 3 4   
                                4 3 2 1 2 3 4   
                                4 3 2 2 2 3 4   
                                4 3 3 3 3 3 4   
                                4 4 4 4 4 4 4   

**Input Format**

The input will contain a single integer $n$.  

**Constraints**

$1 \le n \le 1000$

**Output Format**

## Solution

**Language:** C  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-11-03T02:27:38.630Z  

```c
#include <stdio.h>

int main() {
    int n, k;
    scanf("%d %d", &n, &k);

    int max_and = 0;
    int max_or = 0;
    int max_xor = 0;

    for (int a = 1; a <= n; a++) {
        for (int b = a + 1; b <= n; b++) {

            int and_val = a & b;
            int or_val = a | b;
            int xor_val = a ^ b;

            if (and_val < k && and_val > max_and)
                max_and = and_val;

            if (or_val < k && or_val > max_or)
                max_or = or_val;

            if (xor_val < k && xor_val > max_xor)
                max_xor = xor_val;
        }
    }

    printf("%d\n", max_and);
    printf("%d\n", max_or);
    printf("%d\n", max_xor);

    return 0;
}

```

---

[View on HackerRank](https://www.hackerrank.com/challenges/printing-pattern-2/problem)