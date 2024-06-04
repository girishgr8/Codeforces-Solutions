---
tags:
  - math
  - '*800'
---
# [A. Little Nikita](https://codeforces.com/contest/1977/problem/A)

=== "C++"

    ```c++
    #include <bits/stdc++.h>
    using namespace std;
    #define ll long long int
    #define ulli unsigned long long int
    #define li long int
    
    void solve(int n, int m)
    {
        if (n < m || (n - m) % 2 == 1)
            cout << "No" << endl;
        else
            cout << "Yes" << endl;
    }
    
    int main()
    {
        int t;
        cin >> t;
    
        while (t-- > 0)
        {
            int n, m;
            cin >> n >> m;
            solve(n, m);
        }
        return 0;
    }
    ```

=== "Java"

    ```java
    import java.util.*;
    import java.io.*;

    public class Main {
        public static void solve(int n, int m) {
            if (n < m || (n - m) % 2 == 1)
                System.out.println("No");
            else 
                System.out.println("Yes");
        }

        public static void main(String[] args) {
            FastReader sc = new FastReader();
            int t = sc.nextInt();
            while (t-- > 0) {
                int n = sc.nextInt();
                int m = sc.nextInt();
                solve(n, m);
            }
        }
    }
    ```

- [X] **Time Complexity :** O(t) where `t` is number of testcases
- [X] **Space Complexity :** O(1)
