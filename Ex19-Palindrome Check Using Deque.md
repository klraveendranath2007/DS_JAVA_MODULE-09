# Ex19 Palindrome Check Using Deque
## DATE:16-10-2025
## AIM:
To design a program that checks whether a given message is a palindrome by removing all non-alphanumeric characters, converting all characters to lowercase, and using a deque data structure for comparison.

## Algorithm
1. Start the program.  
2. Read the input string from the user.  
3. Remove all non-alphanumeric characters and convert the string to lowercase.  
4. Use a deque to store characters of the string.  
5. Compare characters from both ends of the deque.  
6. If all pairs match, it’s a palindrome; otherwise, it’s not.  
7. Display the result.    

## Program:
```java
/*
Program to checks whether a given message is a palindrome by removing all non-alphanumeric characters.
Developed by: K L RAVEENDRANATH
RegisterNumber:  212224060212
*/

import java.util.*;

public class PalindromeChecker {
    
    public static boolean isPalindrome(String message) {
        // Convert to lowercase and remove non-alphanumeric characters
        message = message.toLowerCase().replaceAll("[^a-z0-9]", "");
        
        Deque<Character> deque = new ArrayDeque<>();
        
        // Add all characters to the deque
        for (char c : message.toCharArray()) {
            deque.addLast(c);
        }
        
        // Compare characters from both ends
        while (deque.size() > 1) {
            if (deque.pollFirst() != deque.pollLast()) {
                return false;  // Mismatch found
            }
        }
        
        return true;  // All characters matched
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        //System.out.println("Enter a message:");
        String input = scanner.nextLine();

        if (isPalindrome(input)) {
            System.out.println("Palindrome");
        } else {
            System.out.println("Not a palindrome");
        }

        scanner.close();
    }
}

```

## Output:
<img width="447" height="165" alt="image" src="https://github.com/user-attachments/assets/bbbfe3c8-16a3-447b-a7d5-cf5ad1aa1664" />




## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
