Tags: [[Java]] [[Programming]] [[Array List]] [[CRUD]]

---

# 🧾 Java Study Session: Day 5 — Linked Lists with Array List

## 🟢 Day 5: Java Study Log

> "I want to learn how to combine fruit names and their quantities into a single working system — using `ArrayList<Integer>` and `ArrayList<String>`."

Today, we successfully built a **CRUD system** using two linked `ArrayList`s — one for fruit names and another for quantities. This laid the groundwork for object-oriented design while reinforcing index-based logic.

---

## 🧠 Concepts I Learned

### ✅ Linked Parallel Lists

- Used two `ArrayList`s to represent a table-like structure:
    - `ArrayList<String> item` for fruit names
    - `ArrayList<Integer> item_quan` for quantities
- Maintained strict index alignment (i.e., index `i` in both lists refers to the same fruit record)

### ✅ Adding Records

- Asked the user for a fruit name and quantity
- Used `.add()` to insert both into their respective lists
- Ensured inputs were synced by index

**Sample Code:**

```java
System.out.print("Enter Fruit: ");
String fruit_name = input.nextLine();
item.add(fruit_name);

System.out.print("Enter Quantity: ");
int fruit_quantity = input.nextInt();
input.nextLine();
item_quan.add(fruit_quantity);
```

### ✅ Viewing/Listing Records

- Used a `for` loop to print both `item.get(i)` and `item_quan.get(i)` together

- Output formatted as:

    ```
    Apple - 3
    Banana - 5
    ```

- Checked for `.isEmpty()` before listing to avoid printing from an empty list

**Sample Code:**

```java
for (int i = 0; i < item.size(); i++) {
    System.out.println(item.get(i) + " - " + item_quan.get(i));
}
```

### ✅ Editing Records

- Validated user input index: `index >= 0 && index < item.size()`
- Used `.set(index, newValue)` on both lists:
	- Updated the fruit name

    - Updated the quantity
- Printed what was replaced using `get(index)` before editing
- Used a loop to retry editing if the index was invalid

**Sample Code:**

```java
System.out.print("Enter index to edit: ");
int index = input.nextInt();
input.nextLine();

if (index >= 0 && index < item.size()) {
    System.out.print("Enter new fruit name: ");
    String newName = input.nextLine();
    System.out.print("Enter new quantity: ");
    int newQuantity = input.nextInt();
    input.nextLine();

    item.set(index, newName);
    item_quan.set(index, newQuantity);
    System.out.println("Updated successfully!");
}
```

### ✅ Deleting Records

- **Important bug fix**: accessed `.get(index)` before calling `.remove(index)`
- Used `.remove(index)` on both lists to keep them synced
- Showed what was deleted to the user with formatted feedback
- Prevented crash by checking `.isEmpty()` and validating index before delete

**Sample Code:**

```java
System.out.print("Enter index to delete: ");
int index = input.nextInt();
input.nextLine();

if (index >= 0 && index < item.size()) {
    String deletedName = item.get(index);
    int deletedQuantity = item_quan.get(index);
    item.remove(index);
    item_quan.remove(index);

    System.out.println(deletedName + " - " + deletedQuantity + " has been deleted.");
}
```

---

## 🧩 Features I Implemented

- ✅ Add Fruit + Quantity
- ✅ List All Entries
- ✅ Edit Fruit & Quantity with index checking
- ✅ Delete Fruit & Quantity
- ✅ Exit option
- ✅ Input cleanup using `input.nextLine()` after `nextInt()`

---

## 🧠 Code Design Reflection

- The parallel list design helped reinforce how related data must be kept in sync
- Index-based operations need **extra care** to prevent out-of-bounds errors
- Input validation is now part of my habit, especially when working with lists
- The current structure is modular enough to be split into methods later
- This experience made me ready to combine both values into a **custom class** (like `Fruit` with fields `name` and `quantity`)

---

## ✅ Goals for Day 6

- Learn how to refactor this code to use a custom `Fruit` class (OOP)
- Replace two lists with one `ArrayList<Fruit>`
- Practice sorting by quantity or name
- (Optional) Save/load fruit records from a file (basic persistence)

---

# Source Code

``` java

import java.util.Scanner;  
import java.util.ArrayList;  
  
public class combinedArrays {  
    public static void main(String[] args){  
        Scanner input = new Scanner(System.in);  
        ArrayList<String> item = new ArrayList<>();  
        ArrayList<Integer> item_quan = new ArrayList<>();  
        boolean running = true;  
  
        while (running) {  
  
            System.out.println("\nFRUITS - QUANTITIES\n");  
  
            System.out.println("1. Add Fruit");  
            System.out.println("2. List All Fruit");  
            System.out.println("3. Edit Fruit");  
            System.out.println("4. Delete Fruit");  
            System.out.println("5. Exit");  
  
            System.out.print("\nEnter Choice: ");  
            int get_user_input = input.nextInt();  
            input.nextLine();  
  
            if (get_user_input == 1) {  
  
                System.out.print("Enter Fruit: ");  
                String fruit_name = input.nextLine();  
                item.add(fruit_name);  
  
                System.out.print("Enter Fruit Quantities: ");  
                int fruit_quantities = input.nextInt();  
                input.nextLine();  
                item_quan.add(fruit_quantities);  
  
            } else if (get_user_input == 2) {  
  
                if (!item.isEmpty()) {  
  
                    for (int i = 0; i < item.size(); i++) {  
                        System.out.println(item.get(i) + " - " + item_quan.get(i));  
                    }  
  
                } else {  
                    System.out.println("=====================");  
                    System.out.println("There is no item in the list!");  
                    System.out.println("=====================");  
  
                }  
  
            } else if (get_user_input == 3){  
  
                if (item.isEmpty()){  
                    System.out.println("=====================");  
                    System.out.println("There is no item in the list!");  
                    System.out.println("=====================");  
  
                } else {  
  
                    boolean x = true;  
                    while (x){  
  
                        System.out.print("Enter Index: ");  
                        int get_index = input.nextInt();  
                        input.nextLine();  
  
                        if (get_index >= 0 && get_index < item.size()){  
  
                            System.out.print("Enter new Fruit: ");  
                            String new_fruit = input.nextLine();  
                            String old_fruit = item.get(get_index);  
                            item.set(get_index, new_fruit);  
  
                            System.out.print("Enter The Quantity: ");  
                            int new_quan = input.nextInt();  
                            input.nextLine();  
                            int old_quan = item_quan.get(get_index);  
  
                            item_quan.set(get_index, new_quan);  
                            System.out.println(old_fruit + " - " + old_quan + " Has been replaced with " + new_fruit + " - " + new_quan);  
  
                            x = false;  
  
                        } else {  
                            System.out.println("Invalid Index, Try Again.");  
                        }  
                    }  
                }  
            } else if (get_user_input == 4){  
  
                if (item.isEmpty()){  
                    System.out.println("=====================");  
                    System.out.println("There is no item in the list!");  
                    System.out.println("=====================");  
  
                } else {  
  
                    boolean y = true;  
                    while (y){  
  
                        System.out.print("Enter Index to delete: ");  
                        int get_index = input.nextInt();  
                        input.nextLine();  
  
                        if (get_index >= 0 && get_index < item.size()){  
  
                            item.remove(get_index);  
                            item_quan.remove(get_index);  
  
                            String old_fruit = item.get(get_index);  
                            int old_quan = item_quan.get(get_index);  
  
                            System.out.println(old_fruit + " - " + old_quan + " Has Been deleted.");  
  
                            y = false;  
  
                        } else {  
                            System.out.println("Invalid Index, Try Again.");  
                        }  
                    }  
                }  
            } else {  
                running = false;  
  
            }  
        }    
    }  
}
```