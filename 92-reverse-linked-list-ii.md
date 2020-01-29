/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} head
 * @param {number} m
 * @param {number} n
 * @return {ListNode}
 */

var reverseBetween = function(head, m, n) {
   let dummy = new ListNode(-1);
   let pre = dummy;
   dummy.next = head;

   for (let i = 0; i < m - 1; i++) {
       pre = pre.next;
   }

   let cur = pre.next;

   for (let i = m; i < n; i++) {
       let temp = cur.next;
       cur.next = temp.next;
       temp.next = pre.next;
       pre.next = temp;
   }

   return dummy.next;
};




/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} head
 * @param {number} m
 * @param {number} n
 * @return {ListNode}
 */

var reverseBetween = function(head, m, n) {
    let successor = null; 
    let reverseN = (head, n) => {
        if (n === 1) {
            successor = head.next;
            return head;
        }

        let cur = reverseN(head.next, n - 1);
        head.next.next = head;
        head.next = successor;
        return cur;
    }

    if (m === 1) {
        return reverseN(head, n);
    }

    head.next = reverseBetween(head.next, m - 1, n - 1);
    return head;
};