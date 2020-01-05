/**
 * @param {number[]} nums
 * @return {number}
 */
var removeDuplicates = function(nums) {
    let n = nums.length;
    if (n <= 2) return n;
    let slow = 1;
    for (let fast = 2; fast < n; fast++) {
        if (nums[slow - 1] != nums[fast]) {
            slow++;
            nums[slow] = nums[fast];
        }
    }
    return slow + 1;
};