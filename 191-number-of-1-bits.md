/**
 * @param {number} n - a positive integer
 * @return {number}
 * 十进制转二进制
 */
var hammingWeight = function(n) {
    let count = 0;
    while (n) {
        count += n % 2; 
        n = n >> 1;
        // n = Math.floor(n / 2);
    }
    return count;
};




/**
 * @param {number} n - a positive integer
 * @return {number}
 * 位运算
 */
var hammingWeight = function(n) {
    let counts = 0;
    let mask = 1;
    for (let i = 0; i < 32; i++) {
        if ((n & mask) !== 0) {
            counts++;
        }
        mask <<= 1;
    }
    return counts;
};



/**
 * @param {number} n - a positive integer
 * @return {number}
 * 位运算更简洁的做法
 */
var hammingWeight = function(n) {
    let counts = 0;
    while(n) {
        counts++;
        n &= n - 1
    }
    return counts;
};