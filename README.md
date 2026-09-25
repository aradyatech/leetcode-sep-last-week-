# leetcode-sep-last-week-
class Solution {
public:
    int digitSum(int n) {
        int sum = 0;

        while (n > 0) {
            sum += n % 10;
            n /= 10;
        }

        return sum;
    }

    int smallestIndex(vector<int>& nums) {
        for (int i = 0; i < nums.size(); i++) {
            if (digitSum(nums[i]) == i) {
                return i;

                class Solution {
public:
    string s;
    int i;

    // Parses an expression until '}' or end
    set<string> parseExpression() {
        set<string> result;

        // First parse concatenated terms
        set<string> current = parseTerm();

        // Add current results
        result.insert(current.begin(), current.end());

        // Handle union: a,b,c
        while (i < s.size() && s[i] == ',') {
            i++;  // skip ','

            set<string> next = parseTerm();
            result.insert(next.begin(), next.end());
        }

        return result;
    }

    // Parses concatenation: ab{c,d}e
    set<string> parseTerm() {
        set<string> result;
        result.insert("");

        while (i < s.size() && s[i] != '}' && s[i] != ',') {

            set<string> part;

            // Single character
            if (s[i] >= 'a' && s[i] <= 'z') {
                part.insert(string(1, s[i]));
                i++;
            }

            // Braced expression
            else if (s[i] == '{') {
                i++;  // skip '{'

                part = parseExpression();

                i++;  // skip '}'
            }

            // Cartesian product for concatenation
            set<string> temp;

            for (string a : result) {
                for (string b : part) {
                    temp.insert(a + b);
                }
            }

            result = temp;
        }

        return result;
    }

    vector<string> braceExpansionII(string expression) {
        s = expression;
        i = 0;

        set<string> ans = parseExpression();

        return vector<string>(ans.begin(), ans.end());
    }
};
            }
        }

        return -1;
    }
};
