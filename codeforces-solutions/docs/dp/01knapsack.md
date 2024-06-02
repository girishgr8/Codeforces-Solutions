**Approach 1 : Recursion :sweat_smile:**

=== "Java"

    ```java
    ```

-   [x] **Time Complexity :** O(2^(n\*W)) where n is number of items, and W is the capacity of knapsack

-   [x] **Space Complexity :** O(max(n,W)) where n is number of items, and W is the capacity of knapsack

<hr>

**Approach 2 : Memoization :smile:**

=== "Java"

    ```java
    ```

-   [x] **Time Complexity :** O(n\*W) where n is number of items, and W is the capacity of knapsack

-   [x] **Space Complexity :** O(n\*W) where n is number of items, and W is the capacity of knapsack

<hr>

**Approach 3 : Tabulation :smile:**

=== "Java"

    ```java
    class Solution {
        public static void main(String[] args) {
            int W = 50;
            int n = 3;
            int[] p = {60, 100, 120};
            int[] wt = {10, 20, 30};

            int[][] dp = new int[n + 1][W + 1];

            for(int i = 0; i <= n; i++){
                for(int j = 0; j <= W; j++){
                    if(i == 0 || j == 0)
                        continue;
                    else if(wt[i-1] > j)
                        dp[i][j] = dp[i-1][j];
                    else
                        dp[i][j] = Math.max(dp[i-1][j], (dp[i-1][j-wt[i-1]]+p[i-1]));
                }
            }
            System.out.println("Maximum Profit = " + dp[n][W]);
        }
    }
    ```

-   [x] **Time Complexity :** O(n\*W) where n is number of items, and W is the capacity of knapsack

-   [x] **Space Complexity :** O(n\*W) where n is number of items, and W is the capacity of knapsack
