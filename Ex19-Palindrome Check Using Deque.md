# Ex19 Palindrome Check Using Deque
## DATE:
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

public class PalindromeDeque {
    public static boolean isPalindrome(String str) {
        Deque<Character> deque = new LinkedList<>();
        for (char c : str.toCharArray()) {
            if (Character.isLetterOrDigit(c)) {
                deque.add(Character.toLowerCase(c));
            }
        }

        while (deque.size() > 1) {
            if (deque.removeFirst() != deque.removeLast())
                return false;
        }
        return true;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a message: ");
        String message = sc.nextLine();
        if (isPalindrome(message))
            System.out.println("Palindrome");
        else
            System.out.println("Not a Palindrome");
        sc.close();
    }
}

```

## Output:
<img width="597" height="149" alt="image" src="https://github.com/user-attachments/assets/014bfa6f-c4b7-495a-83bf-a5df5f58ec3f" />



## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
