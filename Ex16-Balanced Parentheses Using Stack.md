# Ex16 Check for Balanced Parentheses Using Stack
## DATE:
## AIM:
To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket (, {, [ has a corresponding and correctly ordered closing bracket ), }, ].

## Algorithm
1. Start the program.    
2. Create an empty stack.    
3. Traverse each character in the string.    
4. Push opening brackets onto the stack.    
5. When a closing bracket is encountered, check if it matches the top of the stack.    
6. If any mismatch or leftover element exists, the parentheses are not balanced.    
7. If the stack is empty at the end, the parentheses are balanced.       

## Program:
```java
/*
Program to verify whether the parentheses (brackets) in an input string are balanced
Developed by: K L RAVEENDRANATH
RegisterNumber:  212224060212
*/

import java.util.*;

public class BalancedParentheses {
    public static boolean isBalanced(String str) {
        Stack<Character> stack = new Stack<>();
        for (char ch : str.toCharArray()) {
            if (ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
            } else if (ch == ')' || ch == '}' || ch == ']') {
                if (stack.isEmpty()) return false;
                char top = stack.pop();
                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '['))
                    return false;
            }
        }
        return stack.isEmpty();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter expression: ");
        String expr = sc.nextLine();
        if (isBalanced(expr))
            System.out.println("Balanced");
        else
            System.out.println("Not Balanced");
        sc.close();
    }
}
```

## Output:
<img width="567" height="160" alt="image" src="https://github.com/user-attachments/assets/523b2b30-f1bb-4edc-9645-65de1832b8c7" />

## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
