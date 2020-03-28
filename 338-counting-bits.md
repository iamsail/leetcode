/**
 * @param {number} num
 * @return {number[]}
 * 十进制转二进制
 */
var countBits = function(num) {
    let result = [0];
    for (let i = 1; i <= num; i++) {
        let count = 0;
        let n = i;
        while (n) {
            count += n % 2; 
            n = n >> 1;
        }
        result[i] = count;
    }
    return result;
};




/**
 * @param {number} num
 * @return {number[]}
 * 动态规划
 */
var countBits = function(num) {
    let result = [0];
    for (let i = 1; i <= num; i++) {
        if (i & 1) {
            result[i] = result[i - 1] + 1;
        } else {
            result[i] = result[i >> 1];
        }
    }
    return result;
};



/**
 * @param {number} num
 * @return {number[]}
 * 更简洁的动态规划
 */
var countBits = function(num) {
    let result = [0];
    for (let i = 1; i <= num; i++) {
        result.push(result[i >> 1] + (i & 1));
    }
    return result;
};