# Time: O(N)
# Space: O(N)

```cpp
int minLength(string s) {
        stack<char> st;
        for (int i = 0; i < s.size(); i++) {
            if (!st.empty()) {
                char c = st.top();
                if (c == 'A' && s[i] == 'B') {
                    st.pop();
                } else if (c == 'C' && s[i] == 'D') {
                    st.pop();
                } else {
                    st.push(s[i]);
                }
            } else {
                st.push(s[i]);
            }
        }
        return st.size();
    }
```