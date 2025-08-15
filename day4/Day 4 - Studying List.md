Tags: [[Java]] [[Programming]] [[CRUD]]

---

# 🧾 Java Study Session: Day 4 — Array List & CRUD

## 🟢 Day 4: Java Study Log

> "Let's go Day 4! I want to try to learn how to manipulate lists, input into lists, and combine string and int values — no dictionaries yet."

This session focused on mastering:

- Using `ArrayList<String>` for dynamic data
- Adding, reading, updating, and deleting elements
- Combining `String` + `int` into a single string entry
- Building a text-based CRUD menu with user input

---

## 🧠 Concepts I Learned

### ✅ What is an Array List?

An `ArrayList` is a resizable list in Java — unlike arrays (`String[]`), its size can grow or shrink during runtime. You can add, remove, update, or access items using built-in methods like `.add()`, `.remove()`, `.set()`, and `.get()`.

```java
ArrayList<String> fruits = new ArrayList<>();
fruits.add("Apple");
fruits.set(0, "Mango");
fruits.remove(0);
```

Array Lists require `import java.util.ArrayList;` to be used.

---

### ✅ Scanner Input with Array Lists

To combine user input with list actions, `Scanner` was used:

```java
Scanner input = new Scanner(System.in);
```

We learned how to use `nextInt()` and `nextLine()` together properly:

- `nextInt()` reads a number
- `nextLine()` reads full string input
- An extra `nextLine()` after `nextInt()` clears the newline

---

## 🧪 Practice: Add & Combine Fruit Name + Quantity

Goal: Let the user type in fruit names and quantities, then store them like:

```
"APPLE - 4 pcs"
```

```java
System.out.print("Enter fruit: ");
String get_fruit = input.nextLine().toUpperCase();

System.out.print("Enter quantity: ");
int quan = input.nextInt();
input.nextLine();

String combined = get_fruit + " - " + quan + " pcs";
fruits.add(combined);
```

This allowed us to build formatted entries inside an `ArrayList<String>`.

---

## 🧪 Project: Interactive CRUD Menu (Add, List, Edit, Delete)

Built a full-featured console app with a looping menu:

- `1`: Add a fruit
- `2`: List all fruits
- `3`: Edit a fruit by index using `.set(index, value)`
- `4`: Delete a fruit by index using `.remove(index)`
- `5`: Exit program

Code sample for deleting:

```java
System.out.print("Enter index to delete: ");
int index = input.nextInt();
String deleted = fruits.get(index);

fruits.remove(index);
System.out.println(deleted + " has been deleted");
```

List was displayed using a loop with manual indexing:

```java
for (int i = 0; i < fruits.size(); i++) {
    System.out.println(i + ": Fruit: " + fruits.get(i));
}
```

---

## 💡 Notes to Self

- Use `.get(index)` to access items in ArrayLists — not `[]`
- Always clean up with `nextLine()` after using `nextInt()`
- Array List is like a dynamic Python list, not a dictionary
- Methods learned: `.add()`, `.set()`, `.remove()`, `.get()`, `.size()`
- Combined `String` and `int` values using `+` to build entries like receipts
- You can update items **only** if the index exists (no auto-expand like Python)

---

## ✅ Goals for Day 5

- Add input validation for bad indexes (optional challenge)
- Learn how to use `ArrayList<Integer>` for storing numbers
- Try storing both fruit names and quantities in two linked lists (or classes)
- Learn how to sort lists alphabetically or by quantity

---
# Sources Code 

```java
// imports
import java.util.ArrayList;  
import java.util.Scanner;  

// Declaring a class
public class Main {  
    public static void main(String[] args) {  

		// Declaring a input and list
        Scanner input = new Scanner(System.in);  
        ArrayList<String> fruits = new ArrayList<>();  

		// Printing the menu
        System.out.println();  
        System.out.println("             MENU    ");  
        System.out.println("==============================");  

		// Declaring a variable called is_on
        boolean is_on = false;  

		// Making a while loop
        while (!is_on) {  

			// Printing out the menu
            System.out.println("1. Add a fruit");  
            System.out.println("2. List all fruits");  
            System.out.println("3. Edit A fruit");  
            System.out.println("4. Delete a Fruit");  
            System.out.println("5. Exit");  
  
            System.out.print("\nEnter Choice: ");  
            int get_user_input = input.nextInt();  
            input.nextLine();  
  
            if (get_user_input == 1) {  
  
                System.out.println("==============================");  
  
                System.out.print("Enter Fruit: ");  
                String fruit = input.nextLine();  
                fruits.add(fruit);  
                System.out.println(fruit + " Has been added to the list");  
  
                System.out.println("==============================");  
  
            } else if (get_user_input == 2) {  
  
                System.out.println("==============================");  
  
                for (int i = 0; i < fruits.size(); i++) {  
                    System.out.println(i + ": Fruit: " + fruits.get(i));  
                }  
  
                System.out.println("==============================");  
  
            } else if (get_user_input == 3) {  
  
                System.out.println("==============================");  
  
                System.out.print("Enter What number: ");  
                int edit_num = input.nextInt();   
                input.nextLine();  
  
                System.out.print("Whats the new item: ");  
                String get_new_fruit = input.nextLine();  
                fruits.set(edit_num, get_new_fruit);  
  
                System.out.println("The item has been updated!");  
                System.out.println("==============================");  
  
            } else if (get_user_input == 4){  
  
                System.out.println("==============================");  
                System.out.print("Enter Index for Fruits to delete: ");  
                int fruit_delete = input.nextInt();  
                String deleted = fruits.get(fruit_delete);  
  
                fruits.remove(fruit_delete);  
  
                System.out.println(deleted + " Has been deleted");  
  
            } else {  
                is_on = true;  
            }  
  
        }  
  
    }  
}

```


# Source Code [In laptop]

```java
import java.util.Scanner;  
import java.util.ArrayList;  
  
public class Main{  
    public static void main(String[] args){  
  
        // Setting up for list and input function  
        Scanner input = new Scanner(System.in);  
        ArrayList<String> lst = new ArrayList<>();  
  
        // Printing out the menu  
        System.out.println("=====================");  
        System.out.println("        MENU     ");  
        System.out.println("=====================");  
  
        // declaring if the loop is on or not  
        boolean is_on = false;  
  
        // A While loop  
        while (!is_on) {  
  
            // Print choices  
            System.out.println("\n1. Add Item");  
            System.out.println("2. Read List");  
            System.out.println("3. Edit Item");  
            System.out.println("4. Delete Item");  
            System.out.println("5. Exit");  
  
            // get user input of choices  
            System.out.print("\nChoice: ");  
            int get_user_input = input.nextInt();  
            input.nextLine(); // this is for clean up  
  
            // this is the logic block of code            if (get_user_input == 1) {  
  
                boolean lop = true;  
                System.out.println("=====================");  
  
                while (lop) {  
  
                    // This is where the user input goes  
                    System.out.print("Item(N for stop): ");  
                    String item_get = input.nextLine();  
  
                    if (!item_get.equals("N")) {  
  
                        lst.add(item_get);  
  
                        // Printing a seperating line  
                        System.out.println("---------------------");  
  
                        // Prints out the result of it  
                        System.out.println(item_get + " has been added!");  
                        System.out.println("=====================");  
  
                    } else {  
  
                        lop = false;  
                    }  
                }  
  
            } else if (get_user_input == 2) {  
  
                if (lst.size() > 0) {  
  
                    System.out.println("=====================");  
  
                    for (int i = 0; i < lst.size(); i++) {  
                        System.out.println(i + ": Items: " + lst.get(i));  
                    }  
  
                    System.out.println("=====================");  
  
                } else {  
                    System.out.println("=====================");  
                    System.out.println("There are no items in list :<");  
                    System.out.println("=====================");  
                }  
  
            } else if (get_user_input == 3) {  
  
                if (lst.size() > 0) {  
  
                    System.out.println("=====================");  
  
                    System.out.print("Enter Index: ");  
                    int get_new_index = input.nextInt();  
                    input.nextLine();  
  
                    System.out.print("Enter New Varible: ");  
                    String get_new_variable = input.nextLine();  
                    String get_old_variable = lst.get(get_new_index);  
  
                    System.out.println(get_old_variable + " has been replaced with " + get_new_variable);  
                    lst.set(get_new_index, get_new_variable);  
  
                    System.out.println("=====================");  
  
                } else {  
                    System.out.println("=====================");  
                    System.out.println("There are now items in the list to edit :<");  
                    System.out.println("=====================");  
                }  
  
            } else if (get_user_input == 4) {  
                System.out.println("=====================");  
                System.out.print("Enter Index To delete: ");  
                int item_to_delete = input.nextInt();  
                input.nextLine();  
  
                String get_item = lst.get(item_to_delete);  
                lst.remove(item_to_delete);  
  
                System.out.println("Item " + get_item + " Has been deleted!");  
                System.out.println("=====================");  
  
            } else {  
                is_on = true;  
            }  
        }  
    }  
}

```