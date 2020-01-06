/**
 * @param {number} x
 * @return {number}
 */
var reverse = function(x) { 
    if (x === null) return;
    let PositiveNumber = true;
    if (x < 0) {
        x = 0 - x;
        PositiveNumber = false;
    };
    let num = String(x).split("").reverse().reduce((total, next) => {
        return total + next
    });

    if (num > Math.pow(2, 31) - 1) return 0;
    return PositiveNumber ? num : 0 - num;
};