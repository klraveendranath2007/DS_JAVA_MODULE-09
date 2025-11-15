# Ex17 Reversing a String Using Stack Data Structure
## DATE:
## AIM:
To write a Java program that reverses an input string using a stack, without using built-in reverse functions.

## Algorithm
1. Start the program.  
2. Create an empty stack of characters.  
3. Traverse the string and push each character onto the stack.  
4. Pop each element from the stack and append it to a new string.  
5. Display the reversed string.  
6. Stop the program.   

## Program:
```java 
/*
Program to reverses an input string using a stack
Developed by: K L RAVEENDRANATH
RegisterNumber:  212224060212
*/

import java.util.*;

public class ReverseStringStack {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String str = sc.nextLine();
        Stack<Character> stack = new Stack<>();
        for (char ch : str.toCharArray())
            stack.push(ch);

        StringBuilder reversed = new StringBuilder();
        while (!stack.isEmpty())
            reversed.append(stack.pop());

        System.out.println("Reversed string: " + reversed.toString());
        sc.close();
    }
}
```

## Output:
<img width="569" height="160" alt="image" src="https://github.com/user-attachments/assets/0bf78166-6eb1-410e-9bf8-3fa72c10b529" />


## Result:
Thus, the program successfully reverses the given string using a stack without relying on built-in reverse functions.
