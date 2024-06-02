---
tags:
  - brute force
  - greedy
  - math
  - sortings
---
# [B. 378QAQ and Mocha&#39;s Array](https://codeforces.com/contest/1975/problem/B)

=== "C++"

    ```c++
    #include <bits/stdc++.h>
    using namespace std;
    #define ll long long int
    #define ulli unsigned long long int
    #define li long int

    int gcd(int a, int b)
    {
        if (a == 0)
            return b;
        return gcd(b % a, a);
    }

    void solve(vector`<int>` &arr)
    {
        int n = arr.size(), i = 0, j = -1;
        if (arr[i] == 1)
        {
            cout << "Yes" << endl;
            return;
        }
        for (int k = 1; k < n; k++)
        {
            if (gcd(arr[i], arr[k]) != arr[i])
            {
                j = k;
                break;
            }
        }
        if (j == -1)
        {
            cout << "Yes" << endl;
            return;
        }
        for (int k = 0; k < n; k++)
        {
            if (!(arr[k] % arr[i] == 0 || arr[k] % arr[j] == 0))
            {
                System.out.println("No");
                return;
            }
        }
        cout << "Yes" << endl;
        return;
    }

    int main()
    {
        int t;
        cin >> t;

    while (t-- > 0)
        {
            int n;
            cin >> n;
            vector`<int>` arr;
            for (int i = 0; i < n; i++)
            {
                int num;
                cin >> num;
                arr.push_back(num);
            }
            sort(arr.begin(), arr.end());
            solve(arr);
        }
        return 0;
    }
    ```

=== "Java"

    ```java
    import java.util.*;
    import java.io.*;

    public class Main {
        public static int gcd(int a, int b) {
            if (a == 0)
                return b;
            return gcd(b % a, a);
        }

    public static void solve(int[] arr) {
            int n = arr.length, i = 0, j = -1;
            if (arr[i] == 1) {
                System.out.println("Yes");
                return;
            }
            for (int k = 1; k < n; k++) {
                if (gcd(arr[i], arr[k]) != arr[i]) {
                    j = k;
                    break;
                }
            }
            if (j == -1) {
                System.out.println("Yes");
                return;
            }
            for (int k = 0; k < n; k++) {
                if (!(arr[k] % arr[i] == 0 || arr[k] % arr[j] == 0)) {
                    System.out.println("No");
                    return;
                }
            }
            System.out.println("Yes");
            return;
        }
        public static void main(String[] args) {
            FastReader sc = new FastReader();
            int t = sc.nextInt();
            while (t-- > 0) {
                int n = sc.nextInt();
                int[] arr = new int[n];
                for (int i = 0; i < n; i++)
                    arr[i] = sc.nextInt();
                Arrays.sort(arr);
                solve(arr);
            }
        }
    }
    ```

- [X] **Time Complexity :** O(t \* n \* logN ) where `t` is number of testcases, `n` is the length of array and `N` = max(`a[i]`)
- [X] **Space Complexity :** O(1)
