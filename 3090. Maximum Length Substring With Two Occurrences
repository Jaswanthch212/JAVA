class Solution {
    public int maximumLengthSubstring(String s) {
        int n = s.length(), res = 0;
        int[] f = new int[26];

        for (int l = 0, r = 0; r < n; r++) {
            ++f[s.charAt(r) - 'a'];

            while (f[s.charAt(r) - 'a'] > 2) {
                --f[s.charAt(l++) - 'a'];
            }

            res = Math.max(res, r - l + 1);
        }

        return res;
    }
}
