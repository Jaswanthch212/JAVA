class Solution {
    public int minimumDeletions(int[] nums) {
        int n = nums.length;

        int minIndex = 0;
        int maxIndex = 0;

        for (int i = 1; i < n; i++) {
            if (nums[i] < nums[minIndex]) {
                minIndex = i;
            }

            if (nums[i] > nums[maxIndex]) {
                maxIndex = i;
            }
        }

        int removeFromFront = Math.max(minIndex, maxIndex) + 1;

        int removeFromBack = n - Math.min(minIndex, maxIndex);

        int removeFromBothSides = Math.min(
            minIndex + 1 + (n - maxIndex),
            maxIndex + 1 + (n - minIndex)
        );

        return Math.min(
            removeFromFront,
            Math.min(removeFromBack, removeFromBothSides)
        );
    }
}
