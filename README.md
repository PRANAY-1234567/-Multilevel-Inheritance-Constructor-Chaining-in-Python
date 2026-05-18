# 🧬 Multilevel Inheritance & Constructor Chaining in Python

## 📌 Description

This Python program demonstrates:

* **Multilevel Inheritance**
* **Constructor Chaining**
* Use of the `super()` function

When an object of the last derived class (`Derived1`) is created, constructors are executed from parent to child in sequence.

---

## 🚀 Features

* Demonstrates multilevel inheritance
* Uses `super()` for constructor chaining
* Shows constructor execution order clearly

---

## 🛠️ How It Works


### Inheritance Hierarchy

```text id="g9m2pl"
Base
  ↓
Derived
  ↓
Derived1
```

---

### 1️⃣ Base Class

```python id="v7x4qa"
class Base
```

Contains constructor:

```python id="r3m8zx"
__init__()
```

Prints:

```text id="k2q9mv"
Inside class Base default constructor
```

---

### 2️⃣ Derived Class

```python id="n5m1pt"
class Derived(Base)
```

👉 Inherits from `Base`

Uses:

```python id="x8q3pl"
super().__init__()
```

to call `Base` constructor.

---

### 3️⃣ Derived1 Class

```python id="b4m7qa"
class Derived1(Derived)
```

👉 Inherits from `Derived`

Uses:

```python id="p9x2zx"
super().__init__()
```

to call `Derived` constructor.

---

## 💻 Code

```python id="c6m8pl"
class Base:
    def __init__(self):
        print("Inside class Base default constructor")


class Derived(Base):
    def __init__(self):
        super().__init__()
        print("Inside class Derived default constructor")


class Derived1(Derived):
    def __init__(self):
        super().__init__()
        print("Inside class Derived1 default constructor")


if __name__ == "__main__":
    obj = Derived1()
```

---

## ▶️ Output

```id="y3m9qa"
Inside class Base default constructor
Inside class Derived default constructor
Inside class Derived1 default constructor
```
---

## 🧠 Key Concepts

### ✔ Multilevel Inheritance

A class inherits from another derived class.

```text id="h8q2mv"
Base → Derived → Derived1
```

---

### ✔ Constructor Chaining

Constructors execute in order:

```text id="t4m7zx"
Base() → Derived() → Derived1()
```

---

### ✔ `super()` Keyword

```python id="q1m8pl"
super().__init__()
```

👉 Calls constructor of immediate parent class.

---

## 📚 Concepts Used

* Multilevel Inheritance
* Constructor Chaining
* `super()` method
* Parent-child relationships

---

## ⚠️ Important Note

If `super().__init__()` is removed from any class:

* constructor chain breaks
* parent constructor will not execute

Example:

```python id="m6q3qa"
class Derived(Base):
    def __init__(self):
        print("Derived constructor")
```

👉 `Base` constructor will be skipped.

---

## 🎯 Advantages

* Code reuse
* Better organization
* Cleaner inheritance hierarchy

---

## 🔧 Future Improvements

* Add methods in all classes
* Demonstrate method overriding
* Add parameterized constructors
* Show multiple inheritance

---

## 📄 License

This project is open-source and free to use.

<img width="677" height="726" alt="image" src="https://github.com/user-attachments/assets/9320bad4-bca6-4f96-9882-174092fe65d0" />
