##  question:
```
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.
```
##  solve:
```cpp
 class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode*rs;  //建立空数组，储存了l1+l2;
        ListNode*p;
        int temp=(l1->val+l2->val);
        rs=new ListNode(temp%10);//rs 的头指针先确定，否则不对。
       
        int num=temp/10;
        l1=l1->next;
        l2=l2->next;
         p=rs;
        while(l1!=NULL||l2!=NULL)
        {
          p->next=new ListNode(num);
            p=p->next;
        if(l1!=NULL)
        {
            p->val+=l1->val;
            l1=l1->next;
        }
            
        if(l2!=NULL)
        {
            p->val+=l2->val;
            l2=l2->next;
        }
       num=p->val/10;
            p->val=p->val%10;
        }
        if(num>0)
        {
            p->next=new ListNode(num);
        }
        return rs;
    }
};
```

// 分析：指针的用法和链表的用法。