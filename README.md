# median-of-two-sorted-array

#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

double findMedianSortedArrays(vector<int>& nums1,
                              vector<int>& nums2) {
    vector<int> merged;

    for (int x : nums1)
        merged.push_back(x);

    for (int x : nums2)
        merged.push_back(x);

    sort(merged.begin(), merged.end());

    int n = merged.size();

    if (n % 2 == 1)
        return merged[n / 2];

    return ((double)merged[n / 2 - 1] +
            merged[n / 2]) / 2.0;
}

int main() {
    int n, m;
    cin >> n >> m;

    vector<int> nums1(n), nums2(m);

    for (int i = 0; i < n; i++)
        cin >> nums1[i];

    for (int i = 0; i < m; i++)
        cin >> nums2[i];

    cout << findMedianSortedArrays(nums1, nums2);

    return 0;
}
