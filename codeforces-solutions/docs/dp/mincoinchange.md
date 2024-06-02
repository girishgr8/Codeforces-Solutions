**Approach 1 : Recursion :sweat_smile:**

=== "Java"

    ```java
    class Solution{
        public static void main(String[] args) {
            int[] coins = {1, 5, 7};
            int n = 18;
            int minCoins = solve(n, coins);
            System.out.println("To make a change of " + n +", minimum coins needed are " + minCoins);
        }

        public static int solve(int n, int[] coins){
            if(n == 0)
                return 0;
        int minimum = Integer.MAX_VALUE;
        for(int i = 0; i < coins.length; i++){
            if(n-coins[i] >= 0){
                int subMin = solve(n-coins[i], coins);
                if(subMin != Integer.MAX_VALUE && subMin + 1 < minimum)
                    minimum = 1 + subMin;
            }
        }
        return minimum;
        }
    }
    ```

-   [x] **Time Complexity :** O(2^(n\*V)) where n is number of different coins, and V is the change to make

-   [x] **Space Complexity :** O(max(n,V)) where n is number of different coins, and V is the change to make

<hr>

**Approach 3 : Tabulation :smile:**

=== "Java"

    ```java
    class Solution {
        public static void main(String[] args) {
            int[] coins = {1, 5, 7};
            int n = 14;
            int totalCoins = coins.length;
            int[] dp = new int[n + 1];
            Arrays.fill(dp, Integer.MAX_VALUE);
            dp[0] = 0;
            for(int i = 1; i < dp.length; i++){
                for(int j = 0; j < totalCoins; j++){
                    if(coins[j] <= i){
                        int min = dp[i-coins[j]];
                        if(min != Integer.MAX_VALUE && min + 1 < dp[i])
                            dp[i] = min + 1;
                    }
                }
            }
            int minCoins = dp[n];
            if(minCoins != Integer.MAX_VALUE)
                System.out.println("To make a change of " + n +", minimum coins needed are " + minCoins);
            else
                System.out.println("We cannot make a change of " + n +" using given coins");
        }
    }
    ```

-   [x] **Time Complexity :** O(n\*V) where n is number of different coins, and V is the change to make

-   [x] **Space Complexity :** O(n\*V) where n is number of different coins, and V is the change to make
