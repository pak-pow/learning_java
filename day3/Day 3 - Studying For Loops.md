Tags: [[Java]] [[Programming]]

---

# Java Study Session: For Loops & Arrays (Day 3)

## 🟢 Day 3: Java Study Log

> "I'm ready for Day 3, let's start with for loops and then list for Java."

This session focused on learning and mastering:

- `for` loops (standard and enhanced/for-each)
- Array (list) structure in Java
- Looping through arrays
- Filtering values and conditional logic with arrays

---

## 🧠 Concepts I Learned

### ✅ Java `for` Loop Syntax

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

- Compact and powerful for fixed iteration
- Starts from `i = 0`, checks condition (`i < 5`), and updates (`i++`)

The standard `for` loop is clean and efficient for when the number of repetitions is known. Each of the three parts inside the parentheses controls how the loop behaves.

---

## 📆 Arrays in Java

```java
String[] people = {"Neil", "Vincent", "Ace", "Prince"};
```

- Stores fixed-size values of a single type
- Accessed using `people[0]`
- `.length` returns size

Arrays are collections of elements like strings or numbers. They’re indexed starting from 0 and offer fast lookups, though their size is fixed.

---

## 🔁 Enhanced `for` Loop (for-each loop)

```java
for (String person : people) {
    System.out.println(person);
}
```

- No need for index variables
- Safer and more readable for full iteration

The enhanced `for` loop lets you iterate through an entire array without managing indices. You declare a variable (`person`) and Java automatically assigns it the next element each time.

---

## 🧪 Practice #1: Count Even Numbers from 1–20

```java
for (int i = 1; i <= 20; i++) {
    if (i % 2 == 0) {
        System.out.println(i);
    }
}
```

- Used modulo operator to check for even numbers
- Demonstrated filtering within a loop

This introduced using conditions to filter values inside a `for` loop, identifying which numbers meet a certain criteria (divisible by 2).

---

## 🧪 Practice #2: Favorite Foods that Start with 'P'

```java
String[] food = {"Pasta", "Pancakes", "Spaghetti", "Hot dog", "Ice Cream"};
int fav_food = 0;

for (String i : food) {
    if (i.toLowerCase().startsWith("p")) {
        fav_food++;
    }
}
System.out.println("You have " + fav_food + " favorite food(s) that start with 'p'.");
```

- Practiced string filtering with `.startsWith()`
- Used `.toLowerCase()` for case-insensitive comparison

This showed how to work with string arrays and check specific character conditions. We counted how many strings began with "P" or "p" using string methods.

---

## 🧪 Practice #3: Sum Odd and Even Numbers in Array

```java
int[] num = {3, 5, 8, 13, 21, 34};
int sum_of_odd = 0;
int sum_of_even = 0;

for (int i : num) {
    if (i % 2 == 0) {
        sum_of_even += i;
    } else {
        sum_of_odd += i;
    }
}
System.out.println("Sum of odd Numbers: " + sum_of_odd);
System.out.println("Sum of even Numbers: " + sum_of_even);
```

- Practiced accumulating totals with conditions
- Split values into even and odd categories

This task required using arithmetic and logic to separate values into categories. Each loop iteration tested whether a number was even or odd and added it to the corresponding total.

---

## 🧪 Final Challenge: Sum Numbers Divisible by 2 and 3

```java
int[] num = {4, 6, 9, 12, 14, 18, 25, 30};
int sum_all = 0;

for (int i : num) {
    if (i % 2 == 0 && i % 3 == 0) {
        sum_all += i;
    }
}
System.out.println("Sum of all numbers divisible by 2 and 3: " + sum_all);
```

- Used compound condition with `&&`
- Filtered numbers meeting multiple rules

This challenge deepened understanding of complex conditional logic. By combining two conditions, we found numbers divisible by both 2 and 3 and calculated their total.

---

## 💡 Notes to Self

- `for (type var : array)` = enhanced for loop
- `.startsWith("P")` + `.toLowerCase()` makes string comparisons easier
- Use `&&` for AND conditions, `||` for OR
- Arrays use `.length` instead of `len()` like Python
- You can’t change array size once declared

---

## ✅ Goals for Day 4

- Learn about `ArrayList` (resizable lists)
- Try writing a menu-driven Java console app
- Review basic Java methods and parameters