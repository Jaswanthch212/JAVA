class Solution {
    public boolean uniformArray(int[] nums1) {
        int mn = Integer.MAX_VALUE;
        int count = 0;

        for (int x : nums1) {
            mn = Math.min(mn, x);
            if (x % 2 == 1) count++;
        }

        return mn % 2 == 1 || count == 0;
    }
}
