# LeetCode-19.-Remove-Nth-Node-From-End-of-List

class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        i, prev, cur = 0, -1, head
        while cur:
            if i == n:
                prev = head
            cur = cur.next
            if prev != -1 and cur:
                prev = prev.next
            i += 1
        if prev == -1:
            head = head.next
            return head
        prev.next = prev.next.next
        return head
