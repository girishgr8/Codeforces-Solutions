---
tags:
  - math
  - number theory
  - "*900"
---
# [A. Odd Divisors](https://codeforces.com/problemset/problem/1475/A)

=== "C++"

    ```c++
    #include <bits/stdc++.h>
    using namespace std;
    #define ll              long long int
    #define ulli            unsigned long long int
    #define li              long int

    int main()
    {
        int t;
        cin >> t;
        while (t-- > 0)
        {
            long long int n;
            cin >> n;
            if ((n & (n - 1)) != 0)
                cout << "YES" << endl;
            else
                cout << "NO" << endl;
        }
        return 0;
    }
    ```

=== "Java"

    ```java
    import java.util.*;
    import java.io.*;

    public class Main {
        public static void main(String[] args) {
            FastReader sc = new FastReader();
            int t = sc.nextInt();
            while (t-- > 0) {
                long n = sc.nextLong();
                if ((n & (n - 1)) != 0)
                    System.out.println("YES");
                else
                    System.out.println("NO");
            }
        }
    }
    ```

- [X] **Time Complexity :** O(1)
- [X] **Space Complexity :** O(1)
