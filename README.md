# Leetcode-solutions-
class Solution {
public:
    int countPalindromicSubsequence(string s) {
        int n = s.size();
        int count = 0;

        for(char ch = 'a'; ch <= 'z'; ch++) {

            int first = s.find(ch);
            int last = s.rfind(ch);

            if(first == -1 || first == last)
                continue;

            unordered_set<char> middle;

            for(int i = first + 1; i < last; i++)
                middle.insert(s[i]);

            count += middle.size();
        }

        return count;  
    }
};
