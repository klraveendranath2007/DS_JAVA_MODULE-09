# Ex17 Reversing a String Using Stack Data Structure
## DATE:09-10-2025
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

import java.util.Scanner;
import java.util.Stack;

public class ReverseStringWithStack {

    public static String reverseString(String input) {
        Stack<Character> stack = new Stack<>();
        for (char ch : input.toCharArray()) {
            stack.push(ch);
        }
        StringBuilder reversed = new StringBuilder();
        while (!stack.isEmpty()) {
            reversed.append(stack.pop());
        }

        return reversed.toString();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        String reversed = reverseString(input);

        // Display result
        System.out.println(reversed);

        scanner.close();
    }
}
```

## Output:
<img width="418" height="161" alt="image" src="https://github.com/user-attachments/assets/47344336-9c2e-45be-8df8-c5ba3f0b985b" />



## Result:
Thus, the program successfully reverses the given string using a stack without relying on built-in reverse functions.
