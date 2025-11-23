# Ex16 Check for Balanced Parentheses Using Stack
## DATE:06-10-2025
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

import java.util.Scanner;

class ArrayStack {
    private char[] stack;
    private int top;

    public ArrayStack(int size) {
        stack = new char[size];
        top = -1;
    }

    public void push(char ch) {
        stack[++top] = ch;
    }

    public char pop() {
        return stack[top--];
    }

    public boolean isEmpty() {
        return top == -1;
    }
}

public class ParenChecker {
    public static boolean isBalanced(String expr) {
        ArrayStack st = new ArrayStack(expr.length());
        for (char ch : expr.toCharArray()) {
            if (ch == '(' || ch == '{' || ch == '[') {
                st.push(ch);
            } else if (ch == ')' || ch == '}' || ch == ']') {
                if (st.isEmpty()) return false;
                char top = st.pop();
                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {
                    return false;
                }
            }
        }
        return st.isEmpty();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String expr = sc.nextLine();
        boolean ok = isBalanced(expr);
        System.out.println(ok);
        sc.close();
    }
}

```

## Output:
<img width="434" height="166" alt="image" src="https://github.com/user-attachments/assets/fc3cbd3a-2cbb-45d7-86e9-83757feb517d" />


## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
