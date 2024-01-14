# CSC-543-warm-up-Tanguy-Flachez


{
    public:
    vector<int> twoSum(vector<int>& nums, int target)
    {
        unordered_map<int, int> numMap;
        int n = nums.size();

        // Building the hash table with a for loop
        for (int i = 0; i < n; i++)
        {
            numMap[nums[i]] = i;
        }

        // Find the complement value of the target
        for (int i = 0; i < n; i++)
        {
            int complement = target - nums[i];
            if (numMap.count(complement) && numMap[complement] != i)
            {
                return { i, numMap[complement]};
            }
        }

        // else return empty if no solution is found
        return { };
    }
};
