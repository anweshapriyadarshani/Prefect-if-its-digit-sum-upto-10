# Prefect-if-its-digit-sum-upto-10
A number is considered perfect if its digits sum up to exactly 10.  Given a positive integer n, return the n-th perfect number.  For example, given 1, you should return 19. Given 2, you should return 28.

#include <bits/stdc++.h>
using namespace std;
 
int findNth(int n)
{
    int count = 0;
 
    for (int curr = 1;; curr++) {
 
        // Find sum of digits in current no.
        int sum = 0;
        for (int x = curr; x > 0; x = x / 10)
            sum = sum + x % 10;
 
        // If sum is 10, we increment count
        if (sum == 10)
            count++;
 
        // If count becomes n, we return current
        // number.
        if (count == n)
            return curr;
    }
    return -1;
}
 
int main()
{
    printf("%d\n", findNth(5));
    return 0;
}
