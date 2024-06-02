---
tags:
  - brute force
  - implementation
  - sortings
---
# [A. Bazoka and Mocha&#39;s Array](https://codeforces.com/contest/1975/problem/A)

=== "C++"

    ```c++
    #include <bits/stdc++.h>
    using namespace std;
    #define ll long long int
    #define ulli unsigned long long int
    #define li long int

    void solve(vector`<int>` &arr){
        int n = arr.size();
        int peakIndex = -1;
        for (int i = 0; i < n - 1; i++)
        {
            if (arr[i] > arr[i + 1])
            {
                peakIndex = i;
                break;
            }
        }
        if (peakIndex == -1)
        {
            cout << "Yes" << endl;
        }
        else
        {
            bool notPossible = false;
            for (int i = peakIndex + 1; i < n; i++)
            {
                int j = (i + 1) % n;
                if (arr[j] < arr[i])
                {
                    notPossible = true;
                    break;
                }
            }
            if (notPossible == false)
                cout << "Yes" << endl;
            else
                cout << "No" << endl;
        }
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
        public static void solve(int[] arr) {
            int n = arr.length;
            int peakIndex = -1;
            for (int i = 0; i < n - 1; i++) {
                if (arr[i] > arr[i + 1]) {
                    peakIndex = i;
                    break;
                }
            }
            if (peakIndex == -1)
                System.out.println("Yes");
            else {
                boolean notPossible = false;
                for (int i = peakIndex + 1; i < n; i++) {
                    int j = (i + 1) % n;
                    if (arr[j] < arr[i]) {
                        notPossible = true;
                        break;
                    }
                }
                if (notPossible == false)
                    System.out.println("Yes");
                else
                    System.out.println("No");
            }
        }

    public static void main(String[] args) {
            FastReader sc = new FastReader();
            int t = sc.nextInt();
            while (t-- > 0) {
                int n = sc.nextInt();
                int[] arr = new int[n];
                for (int i = 0; i < n; i++)
                    arr[i] = sc.nextInt();
                solve(arr);
            }
        }
    }
    ```

- [X] **Time Complexity :** O(t \* n) where `t` is number of testcases and `n` is the length of array
- [X] **Space Complexity :** O(1)
