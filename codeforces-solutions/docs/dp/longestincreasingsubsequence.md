**Approach : Dynamic Programming - Tabulation :smile:**

=== "Java"

    ```java
    class Solution {
        public static void main(String[] args) {
            int[] nums = {10,9,2,5,3,7,101,18};
            int n = nums.length;
            int[] dp = new int[n];
            Arrays.fill(dp, 1);
            int len = 1;
            for(int i = 1; i < n; i++){
                for(int j = 0; j < i; j++){
                    if(nums[j] < nums[i] && dp[i] <= dp[j])
                        dp[i] = 1 + dp[j];
                }
                len = Math.max(len, dp[i]);
            }
            System.out.println("Length of LIS = " + len);
        }
    }
    ```

-   [x] **Time Complexity :** O(n^2^) where n is the length of the array

-   [x] **Space Complexity :** O(n) where n is the length of the array
