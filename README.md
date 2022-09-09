class Solution {
public:
    bool static find_sorted(vector <int> &a, vector<int> &b)
        {
            if(a[0] == b[0])
            {
                return a[1] > b[1];
            }
                return a[0] < b[0];
        }
    int numberOfWeakCharacters(vector<vector<int>>& properties) {
        int maxi = INT_MIN;
        sort(properties.begin(), properties.end(), find_sorted);
        int x = properties.size();
        int count = 0;
        for(int i = x - 1; i >= 0; i--)
        {
            if(properties[i][1] > maxi)
            {
                maxi = properties[i][1];
            }
            if(properties[i][1] < maxi)
            {
                count++;
            }
        }
        return count;
        
    }
};
