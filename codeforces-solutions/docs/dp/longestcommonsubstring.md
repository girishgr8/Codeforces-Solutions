**Approach : Dynamic Programming - Tabulation :smile:**

=== "Java"

    ```java
    class Solution {
        public static void main(String[] args) {
            String s1 = "abcdaf", s2 = "zbcdf";

            int m = s1.length(), n = s2.length();
            int[][] dp = new int[m + 1][n + 1];
            int r = -1, c = -1, len = 0;
            
            for(int i = 1; i <= m; i++){
                for(int j = 1; j <= n; j++){
                    if(s1.charAt(i-1) == s2.charAt(j-1)){
                        dp[i][j] = 1 + dp[i-1][j-1];
                        if(len < dp[i][j]){
                            r = i;
                            c = j;
                            len = dp[i][j];
                        }
                    }
                }
            }
            System.out.println("Length of longest common substring : " + len);
            char[] str = new char[len];
            if(r == -1 && c == -1)
                System.out.println("Longest Common Substring does not exist");
            else{
                while(dp[r][c] > 0){
                    str[--len] = s1.charAt(r-1);
                    r--;
                    c--;
                }
                System.out.println("Longest Common Substring is : " + String.valueOf(str));
            }
        }
    }
    ```

-   [x] **Time Complexity :** O(m\*n) where m and n are the length of the two strings

-   [x] **Space Complexity :** O(m\*n) where m and n are the length of the two strings
