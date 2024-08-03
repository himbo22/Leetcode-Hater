```cpp
class Solution {
public:

    string replaceWords(vector<string>& dictionary, string sentence) {
        string s;
        stringstream ss(sentence);
        string res = "";
        while(getline(ss, s, ' ')){
            bool flag = false;
            string replaceWord = s;
            for(int i=0;i<dictionary.size();i++){
                string word = dictionary[i];
                for(int j=0;j<word.size();j++){
                    if(s[j] != word[j]) {
                        flag = true;
                        break;
                    }
                }
                if(flag == true) flag = false;
                else {
                    if(replaceWord > word) replaceWord = word;
                }
            }
            res += replaceWord;
            res += " ";
        }
        res.pop_back();
        return res;
    }
};
```