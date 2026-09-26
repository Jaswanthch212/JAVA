class Solution {
    public String evaluate(String s, List<List<String>> knowledge) {
        Map<String, String> knowledgeMap = new HashMap<>(knowledge.size());

        for (List<String> pair : knowledge) {
            knowledgeMap.put(pair.get(0), pair.get(1));
        }

        StringBuilder result = new StringBuilder();

        for (int i = 0; i < s.length(); i++) {
            if (s.charAt(i) == '(') {
                int closingBracketIndex = s.indexOf(')', i + 1);
                String key = s.substring(i + 1, closingBracketIndex);

                result.append(knowledgeMap.getOrDefault(key, "?"));
                i = closingBracketIndex;
            } else {
                result.append(s.charAt(i));
            }
        }

        return result.toString();
    }
}
