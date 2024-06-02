-   Basically, the idea is to find length of LCS of a string and it's reverse

**Approach 1 : Recursion :sweat_smile:**

=== "Java"

    ```java
    class Solution {
        public static void main(String[] args) {
            String s1 = "";
            String s2 = new StringBuilder(s1).reverse().toString();

            int n = s1.length();
            int lps = solve(n-1, n-1, s1, s2);
            System.out.println("Length of LPS = " + lps);
        }

        public static int solve(int i, int j, String s1, String s2){
            // base case
            if(i < 0 || j < 0)
                return 0;
            // if the current characters of both strings match,
            // then lcs length = 1 + lcs length for remaining part of these strings
            if(s1.charAt(i) == s2.charAt(j))
                return 1 + solve(i-1, j-1, s1, s2);
            return Math.max(solve(i-1, j, s1, s2), solve(i, j-1, s1, s2));
        }
    }
    ```

-   [x] **Time Complexity :** O(2^n\*n^) where n is the length of the string

-   [x] **Space Complexity :** O(n) where n is the length of the string

<hr>

**Approach 2 : Memoization :smile:**

=== "Java"

    ```java
    ```

-   [x] **Time Complexity :** O(n^2^) where n is the length of the string

-   [x] **Space Complexity :** O(n^2^) where n is the length of the string

<hr>

**Approach 3 : Tabulation :smile:**

=== "Java"

    ```java
    class Solution {
        public static void main(String[] args) {
            String s1 = "";
            String s2 = new StringBuilder(s1).reverse().toString();

            int n = s1.length();
            int[][] dp = new int[n + 1][n + 1];

            for(int i = 1; i <= n; i++){
                for(int j = 1; j <= n; j++){
                    if(s1.charAt(i-1) == s2.charAt(j-1))
                        dp[i][j] = 1 + dp[i-1][j-1];
                else
                    dp[i][j] = Math.max(dp[i-1][j], dp[i][j-1]);
                }
            }
            System.out.println("Length of LPS = " + dp[n][n]);
        }
    }
    ```

-   [x] **Time Complexity :** O(n^2^) where n is the length of the string

-   [x] **Space Complexity :** O(n^2^) where n is the length of the string
