## Valid Parentheses
### problem:
```
Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Note that an empty string is also considered valid.
```
//++    先建立一个向量组，将所有同向的括号“（，{,["储存在里面，设置另一向量组，将尾部的元素储存在里面，一一判断是否匹配。
``` cpp
 class Solution {
public:
       bool isValid(string s) {
           vector<char>stack;
           for(int i=0;i<s.length();i++)
           {
               if(s[i]=='('||s[i]=='{'||s[i]=='[')
               {
                   stack.push_back(s[i]);
               }
               if(s[i]==')'||s[i]=='}'||s[i]==']')
               {
                   if(stack.empty())
                   {
                        return 0;
                   }
               char temp=stack.back();
               stack.pop_back();
               if(s[i]==')'&&temp!='(')
               {
                   return false;
               }
               if(s[i]=='}'&&temp！='{')
               {
                   return false;
               }
               if(s[i]==']'&&temp!='[')
               {
                   return false;
               }
            } 
         }
         return (stack.empty());
       };
       ```cpp