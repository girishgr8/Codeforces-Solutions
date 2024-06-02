---
tags:
  - brute force
  - dp
  - math
  - "*900"
---
# [B. New Year&#39;s Number](https://codeforces.com/problemset/problem/1475/B)

### Approach 1: Bottom-Up Dynamic Programming

=== "C++"

    ```c++
    #include <bits/stdc++.h>
    using namespace std;
    #define ll long long int
    #define ulli unsigned long long int
    #define li long int
    #define N 1000000

    void solve(vector`<bool>` &dp)
    {
        dp[0] = true;
        for (int i = 2020; i <= N; i++)
        {
            if (dp[i - 2020] == true || dp[i - 2021] == true)
                dp[i] = true;
        }
    }

    int main()
    {
        int t;
        cin >> t;
        vector`<bool>` dp(N + 1, false);
        solve(dp);

    while (t-- > 0)
        {
            int n;
            cin >> n;
            if (dp[n] == true)
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
        private static final int N = 1000000;

    public static void solve(boolean[] dp) {
            dp[0] = true;
            for (int i = 2020; i <= N; i++) {
                if (dp[i - 2020] == true || dp[i - 2021] == true)
                    dp[i] = true;
            }
        }

    public static void main(String[] args) {
            FastReader sc = new FastReader();
            int t = sc.nextInt();
            boolean[] dp = new boolean[N + 1];
            solve(dp);

    while (t-- > 0) {
                int n = sc.nextInt();
                if (dp[n] == true)
                    System.out.println("YES");
                else
                    System.out.println("NO");
            }
        }
    }
    ```

- [X] **Time Complexity :** O(N) where `N` = 10<sup>6</sup>
- [X] **Space Complexity :** O(N) where `N` = 10<sup>6</sup>

<hr>

### Approach 2: Mathematical

=== "C++"

    ```c++
    #include <bits/stdc++.h>
    using namespace std;
    #define ll long long int
    #define ulli unsigned long long int
    #define li long int

    int main()
    {
        int t;
        cin >> t;

    while (t-- > 0)
        {
            int n;
            cin >> n;
            int y = n % 2020;
            int x = (n - y) / 2020 - y;
            if (x >= 0 && (x * 2020 + y * 2021) == n)
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

    class Main {
        public static void main(String[] args) {
            FastReader sc = new FastReader();
            int t = sc.nextInt();

    while (t-- > 0) {
                int n = sc.nextInt();
                int y = n % 2020;
                int x = (n - y) / 2020 - y;
                if (x >= 0 && (x * 2020 + y * 2021) == n)
                    System.out.println("YES");
                else
                    System.out.println("NO");
            }
        }
    }
    ```

- [X] **Time Complexity :** O(t) where `t` is number of testcases
- [X] **Space Complexity :** O(1)
