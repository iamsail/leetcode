/**
 * @param {number[]} A
 * @param {number} K
 * @return {number}
 */
var longestOnes = function(A, K) {
    let max = 0;
    for (let left = 0, right = 0, count = 0; right < A.length; right++) {
        if (A[right]) count++;
        while(right - left + 1 - count > K) if (A[left++]) count--;
        max = Math.max(max, right - left + 1)
    }
    return max;
};



/**
 * @param {number[]} A
 * @param {number} K
 * @return {number}
 */
var longestOnes = function(A, K) {
    let max = 0;
    for (let left = 0, right = 0; right < A.length; right++) {
        if (A[right] === 0) {
            if (K === 0) {
                while(A[left]) {
                    left++;
                }
                left++;
            } else {
                K--;
            }
        }
        max = Math.max(right - left + 1, max);
    }
    return max;
};