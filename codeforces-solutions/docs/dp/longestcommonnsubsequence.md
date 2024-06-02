**Approach 1 : Recursion :sweat_smile:**

=== "Java"

    ```java
    class Solution {
        public static void main(String[] args) {
            String s1 = "AGGTAB", s2 = "GXTXAYB";

            int m = s1.length(), n = s2.length();
            int lcs = solve(m-1, n-1, s1, s2);
            System.out.println("Length of LCS = " + lcs);
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

-   [x] **Time Complexity :** O(2^m\*n^) where m and n are the length of the two strings

-   [x] **Space Complexity :** O(max(m,n)) where m and n are the length of the two strings

<hr>

**Approach 2 : Memoization :smile:**

=== "Java"

    ```java
    ```

-   [x] **Time Complexity :** O(m\*n) where m and n are the length of the two strings

-   [x] **Space Complexity :** O(m\*n) where m and n are the length of the two strings

<hr>

**Approach 3 : Tabulation :smile:**

=== "Java"

    ```java
    class Solution {
        public static void main(String[] args) {
            String s1 = "ABCDGH", s2 = "AEDFHR";

            int m = s1.length(), n = s2.length();
            int[][] dp = new int[m + 1][n + 1];

            for(int i = 0; i < m + 1; i++){
                for(int j = 0; j < n + 1; j++){
                    if(i == 0 || j == 0)
                        dp[i][j] = 0;
                    else if(s1.charAt(i-1) == s2.charAt(j-1))
                        dp[i][j] = 1 + dp[i-1][j-1];
                else
                    dp[i][j] = Math.max(dp[i-1][j], dp[i][j-1]);
                }
            }
            int lcs = dp[m][n];
            System.out.println("Length of LCS : " + dp[m][n]);

            char[] str = new char[lcs];
            int i = m, j = n;
            while(i > 0 && j > 0){
                if(dp[i-1][j] == dp[i][j])
                    i--;
                else if(dp[i][j-1] == dp[i][j])
                    j--;
                else{
                    str[--lcs] = s1.charAt(i-1);
                    i--;
                    j--;
                }
            }
            System.out.println("LCS is : " + String.valueOf(str));
        }
    }
    ```

-   [x] **Time Complexity :** O(m\*n) where m and n are the length of the two strings

-   [x] **Space Complexity :** O(m\*n) where m and n are the length of the two strings
