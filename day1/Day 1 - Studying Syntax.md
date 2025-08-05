Tags: [[Java]] [[Programming]]

---
# Java Study Session: Syntax and User input

### ✅ Java Syntax Basics
- Java code runs inside a `public class`.
- The `main` method is the entry point:  `public static void main(String[] args)`
- Statements end with `;`
- Code blocks use `{}` (curly braces)
- Java is **case-sensitive**

---

## 🧪 Practice #1: Login Program

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
	    
	    // Declaring Input function
        Scanner input = new Scanner(System.in);
    
        // Declaring Variables and its values
        String username = "Vincent";
        String password = "pass1234";

		// Getting User input
        System.out.print("Username: ");
        String user_name = input.nextLine();

        System.out.print("Password: ");
        String user_pass = input.nextLine();
	
        // If condition to see if it equals to the variables
        if (user_name.equals(username) && user_pass.equals(password)) {
            System.out.println(String.format("Welcome back, %s!", user_name));
         
        } else {
            System.out.println("LogIn failed");
        }
    }
}
```

### 🧠 Learned:

- `.equals()` is used to compare strings — not `==`
- Logical AND is `&&`
- Use `Scanner` to get user input:

    ```java
Scanner input = new Scanner(System.in);
    ```

---

## 🧪 Practice #2: Age Checker

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Hi! What's your name? ");
        String name = input.nextLine();

        System.out.print("Your Age? ");
        int age = input.nextInt();

        if (age >= 18) {
            System.out.println("You are of legal Age!");
        } else {
            System.out.println("You are not of legal age! " + name);
        }
    }
}
```

### 🧠 Learned:

- No `;` after `if`, `else if`, or `else`
- Use `else` alone for "everything else" — no condition needed
- Format:

    ```java
    if (condition) {
        // code
    } else {
        // code
    }
    ```
---
## 💡 Notes to Self

- `==` is only for **primitive types** (like `int`, `double`, `char`)
- Use `.equals()` for **objects** (like `String`)
- Don't put `;` right after `if` or `else` — it ends the block early

---
## ✅ Goals for Tomorrow

- Practice nested `if` statements
- Learn how `switch` works in Java
- Try writing a basic menu system
