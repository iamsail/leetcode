/**
 * @param {number} x
 * @return {number}
 */
var mySqrt = function(x) {
    if (x < 2) return x;
    const aim = x;
    let right = x >> 1;
    let left = 1;
    while (left <= right) {
        let mid = (left + right) >> 1;
        // console.log('left right mid ', left, right, mid);
        if (mid * mid > aim) {
            right = mid - 1;
        } else if (mid * mid < aim){
            left = mid + 1;
        } else {
            return mid;
        }
    }
    return right;
};



/**
 * @param {number} x
 * @return {number}
 */
var mySqrt = function(x) {
    if (x < 2) return x;
    let left = Math.floor(Math.E ** (0.5 * Math.log(x)));
    let right = left + 1;
    return right * right > x ? left : right;
};