# Time : O(N)
# Space : O(N)

```cpp
int minAddToMakeValid(string s) {
        stack<char> st;
        for(auto c:s){
            if(st.empty()){
                st.push(c);
            }else{
                if(st.top() == '(' && c == ')') st.pop();
                else st.push(c);
            }
        }
        return st.size();
    }
```