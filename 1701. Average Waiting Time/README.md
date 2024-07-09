**LINK:** https://leetcode.com/problems/average-waiting-time/description/?envType=daily-question&envId=2024-07-09
```class Solution {
public:
    double averageWaitingTime(vector<vector<int>>& customer) {
       // sort(customer.begin(),customer.end());
        int time=0;
        double wait=0;

        for(int i=0;i<customer.size();i++){
                if(time<customer[i][0]){
                  time=customer[i][0]+customer[i][1];
                    wait+=customer[i][1];

                }
                else{
                    time+=customer[i][1];
                    wait+=(time-customer[i][0]);
                }
        }
        return wait/(double)customer.size();
    }
};
