Tags: [[Java]] [[Programming]]

---

# Java Study Session: While Loops & Logic Review

## 🟢 Day 2: Java Study Log

> "Okay let’s go with the next step of our study session as I have learned how to use Scanner and I now know how to use if conditions so what’s next?"

---
## 🔁 What is a `while` loop?

- Used when you want to **keep running something over and over** as long as a condition is true.
- You MUST update the condition inside the loop or else it loops forever 😬

```java
int i = 1;
while (i <= 5) {
    System.out.println("Counter: " + i);
    i++;
}
```

---

## 🔣 Operators I Practiced

- `%` → remainder, used for checking even/odd
- `++` → shortcut for `+= 1`
- `+=` → add to current value

```java
if (i % 2 == 0) {
    System.out.println("Even");
} else {
    System.out.println("Odd");
}
```

---

## 🧪 Practice #1: Count Down & Classify Even/Odd

```java
int i = 10;
while (i >= 1) {
    if (i % 2 == 0) {
        System.out.println("Even: " + i);
    } else {
        System.out.println("Odd: " + i);
    }
    i--;
}
```

### 🧠 Learned:

- Counting down uses `i--`
- Can use `% 2` to separate even and odd numbers

---

## 🧪 Practice #2: Sum of Odd Numbers 1–20

```java
int i = 1;
int total_odd = 0;
while (i <= 20) {
    if (i % 2 != 0) {
        System.out.println("Odd: " + i);
        total_odd += i;
    }
    i++;
}
System.out.println("Total: " + total_odd);
```

### 🧠 Learned:

- Looping while summing values
- Only adding values if condition is true

---

## 🧪 Practice #3: User Input + Range + Sum

```java
Scanner input = new Scanner(System.in);
System.out.print("Enter Num: ");
int start = input.nextInt();
System.out.print("Enter EndNum: ");
int end = input.nextInt();

if (start > end) {
    int temp = start;
    start = end;
    end = temp;
}

int total_odd = 0;
while (start <= end) {
    if (start % 2 != 0) {
        System.out.println("Odd: " + start);
        total_odd += start;
    }
    start++;
}
System.out.println("Total Odd Sum: " + total_odd);
```

### 🧠 Learned:

- Taking user input with `Scanner`
- Looping from any direction (start to end, or end to start)
- Swapping values if needed

---

## 💡 Notes to Self

- `==` is only for **primitive types** (like `int`, `double`)
- `.equals()` is for comparing **objects** like `String`
- Never put `;` after `if`, `else if`, or `else` block headers
- Always update the loop variable (`i++`, `i--`, etc.) or it will go infinite

---

## ✅ Goals for Tomorrow

- Try `for` loops in Java
- Practice more `Scanner` input logic
- Try combining conditionals with menu systems or simple text games