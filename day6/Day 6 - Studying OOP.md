Tags: [[Java]] [[OOP]] [[Classes]] [[Array List]] [[CRUD]]

---

# 🍎 Java Study Session: Day 6 — Object-Oriented CRUD System

## 🟩 Summary

Today was the BIG shift: we moved from parallel `ArrayList`s to using **custom classes** and full **object-oriented programming (OOP)** in Java.

We created a `Fruits` class with a constructor and learned how to manage a list of fruit objects using `ArrayList<Fruits>`.

Even though I was tired today, I still pushed through and got a complete working CRUD system using objects. 💪

---

## ✅ What I Learned

### 📦 What is a Class?

- A **class** is like a **blueprint** for making objects.
- I created a class named `Fruits` that stores two fields:
    
    - `String name_item`
    - `int item_quan`

```java
public class Fruits {
    String name_item;
    int item_quan;

    public Fruits(String name, int quantity) {
        name_item = name;
        item_quan = quantity;
    }
}
```

### 🧱 Creating Objects

- I created a fruit object like this:

```java
Fruits apple = new Fruits("Apple", 4);
System.out.println(apple.name_item);  // Apple
System.out.println(apple.item_quan);  // 4
```

### 🧰 Using `ArrayList<Fruits>`

- Instead of two separate lists, I now use:

```java
ArrayList<Fruits> get = new ArrayList<>();
```

- This stores complete fruit objects, so I can manage both name and quantity together.

### 🧾 Listing Fruit Objects

- I added a `.toString()` method to the `Fruits` class:

```java
@Override
public String toString() {
    return name_item + " - " + item_quan + " pcs";
}
```

- This allows me to print a fruit object directly:

```java
System.out.println(apple);  // Apple - 4 pcs
```

---

## 🛠 CRUD Features Implemented

### ➕ Add Fruit

- Get user input
- Use `new Fruits(name, quantity)` to create object
- Add to the list with `.add()`

```java
String fruit_name = input.nextLine();
int quantity = input.nextInt();
Fruits fruit = new Fruits(fruit_name, quantity);
get.add(fruit);
```

### 📋 List Fruits

```java
for (int i = 0; i < get.size(); i++) {
    System.out.println(i + ": " + get.get(i));
}
```

### ✏️ Edit Fruit

- Ask for index
- Ask for new name and quantity
- Use `.set(index, new Fruits(...))` to replace object

```java
Fruits updated = new Fruits(new_name, new_quantity);
get.set(index, updated);
```

### 🗑️ Delete Fruit

- Ask for index
- Use `.remove(index)`
- Optionally store removed item in a variable for feedback

```java
Fruits removed = get.remove(index);
System.out.println("Deleted: " + removed);
```

---

## ❓ What is `input.close();`

- `input.close();` is used to **cleanly shut down the Scanner**.
- This helps release system resources (especially in larger apps).
- It’s optional for small scripts but good practice in real programs.

```java
Scanner input = new Scanner(System.in);
// ...
input.close();  // Optional, but safe and clean
```

---

## 🧠 Final Reflection

- Switching to object-based design made the code much cleaner.
- I no longer have to sync two lists — everything is inside a `Fruits` object.
- I’m now comfortable building custom types, using constructors, and storing objects in `ArrayList`.

---

## 🎯 Goals for Day 7

- Learn how to sort the list by name or quantity
- Add a search feature (by name or quantity)
- Try creating multiple classes (maybe for categories or prices)
- Maybe try file saving/loading
