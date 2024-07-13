**LINK:** https://leetcode.com/problems/robot-collisions/description/?envType=daily-question&envId=2024-07-13
![image](https://github.com/user-attachments/assets/7786b964-fd4a-4a7e-8eaa-17d900d6fdd7)
```
#include <vector>
#include <stack>
#include <algorithm>
#include <iostream>

using namespace std;

class Solution {
public:
    vector<int> survivedRobotsHealths(vector<int>& positions, vector<int>& h, string d) {
        vector<pair<int, int>> v;
        int n = positions.size();

        // Create pairs of (position, index) and sort based on positions
        for (int i = 0; i < n; i++) {
            v.push_back({positions[i], i});
        }
        sort(v.begin(), v.end());

        stack<int> st;
        for (int i = 0; i < n; i++) {
            int ind = v[i].second;

           
           while (!st.empty()&& d[st.top()] == 'R' && d[ind] == 'L') {
                if (h[st.top()] > h[ind]) {
                    h[st.top()] -= 1;
                    h[ind] = 0; 
                    break;
                } else if (h[st.top()] < h[ind]) {
                    h[ind] -= 1;
                    h[st.top()] = 0; 
                    st.pop();
                } else {
                    h[st.top()] = 0; 
                    h[ind] = 0;
                    st.pop();
                    break;
                }
            }

           
            if (h[ind] > 0) {
                st.push(ind);
            }
        }

       
        vector<int> ans;
        while (!st.empty()) {
            ans.push_back(st.top());
            st.pop();
        }
       sort(ans.begin(),ans.end());
       for(int i=0;i<ans.size();i++){
        ans[i]=h[ans[i]];
       }

        return ans;
    }
};
```
# Time Complexity: 𝑂(n+nlogn)
# Space Complexity: 𝑂(3n)
