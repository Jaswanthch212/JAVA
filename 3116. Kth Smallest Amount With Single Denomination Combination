class Solution {
    public long findKthSmallest(int[] coins, int k) {
        Arrays.sort(coins);

        List<Integer> newCoins = new ArrayList<>();

        for (int x : coins) {
            boolean keep = true;

            for (int y : newCoins) {
                if (x % y == 0) {
                    keep = false;
                    break;
                }
            }

            if (keep) {
                newCoins.add(x);
            }
        }

        int n = newCoins.size();
        int m = 1 << n;

        long[] lcm = new long[m];
        Arrays.fill(lcm, 1);

        long left = k;
        long right = (long)newCoins.get(0) * k + 1;

        for (int mask = 1; mask < m; mask++) {
            int prevMask = mask & (mask - 1);
            int bit = mask & -mask;
            int i = Integer.numberOfTrailingZeros(bit);

            long temp = lcm[prevMask] / gcd(lcm[prevMask], newCoins.get(i));

            if (temp <= right / newCoins.get(i)) {
                lcm[mask] = temp * newCoins.get(i);
            } else {
                lcm[mask] = right + 1;
            }
        }

        while (left < right) {
            long mid = left + (right - left) / 2;

            if (countLEQ(mid, lcm, m) >= k) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }

        return left;
    }

    private long countLEQ(long x, long[] lcm, int m) {
        long count = 0;

        for (int mask = 1; mask < m; mask++) {
            if (lcm[mask] > x) {
                continue;
            }

            if (Integer.bitCount(mask) % 2 == 1) {
                count += x / lcm[mask];
            } else {
                count -= x / lcm[mask];
            }
        }

        return count;
    }

    private long gcd(long a, long b) {
        while (b != 0) {
            long temp = a % b;
            a = b;
            b = temp;
        }

        return a;
    }
}
