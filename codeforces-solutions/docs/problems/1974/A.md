---
tags:
  - greedy
  - math
  - "*800"
---

# [A. Phone Desktop](https://codeforces.com/contest/1974/problem/A)

=== "C++"

    ```c++
    #include <bits/stdc++.h>
    using namespace std;
    #define ll long long int
    #define ulli unsigned long long int
    #define li long int

    void solve(int x, int y)
    {
        int two_must = y / 2;
        int two_extra = y % 2;
        int total = two_must + two_extra;
        int one_that_can_fit = 7 * two_must + 11 * two_extra;
        if (x > one_that_can_fit)
        {
            int one_extra = (x - one_that_can_fit);
            total += (one_extra / 15) + (one_extra % 15 > 0 ? 1 : 0);
        }
        cout << total << endl;
        return;
    }

    int main()
    {
        int t;
        cin >> t;

        while (t-- > 0)
        {
            int x, y;
            cin >> x >> y;
            solve(x, y);
        }
        return 0;
    }
    ```

=== "Java"

    ```java
    import java.util.*;
    import java.io.*;

    public class Main {
        public static void solve(int x, int y) {
            int two_must = y / 2;
            int two_extra = y % 2;
            int total = two_must + two_extra;
            int one_that_can_fit = 7 * two_must + 11 * two_extra;
            if (x > one_that_can_fit) {
                int one_extra = (x - one_that_can_fit);
                total += (one_extra / 15) + (one_extra % 15 > 0 ? 1 : 0);
            }
            System.out.println(total);
            return;
        }

        public static void main(String[] args) {
            FastReader sc = new FastReader();
            int t = sc.nextInt();
            while (t-- > 0) {
                int x = sc.nextInt(), y = sc.nextInt();
                solve(x, y);
            }
        }
    }
    ```

- [x] **Time Complexity :** O(t) where `t` is number of testcases
- [x] **Space Complexity :** O(1)
