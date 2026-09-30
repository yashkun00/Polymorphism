# 🐍 Python Polymorphism

A beginner-friendly Python lesson covering **Polymorphism**, an important concept in Object-Oriented Programming (OOP).

Polymorphism allows different classes to use the **same method name** while providing different behavior.

---

## 📌 Topic Covered

* Polymorphism
* Same Method Name
* Different Class Behavior
* Objects and Methods
* Duck Typing in Python

---

# 1. What is Polymorphism?

The word **polymorphism** means **"many forms."**

In Python, different objects can have a method with the same name, but each object can implement that method differently.

For example, both a `Dog` and a `Cat` can have a `speak()` method.

```python id="4f4z3u"
class Dog:
    def speak(self):
        print("Dog barks")


class Cat:
    def speak(self):
        print("Cat meows")


dog = Dog()
cat = Cat()

dog.speak()
cat.speak()
```

---

## 🧠 What Happens Here?

The `Dog` class has:

```python id="q4rjka"
def speak(self):
    print("Dog barks")
```

The `Cat` class also has a method with the same name:

```python id="5qk7xe"
def speak(self):
    print("Cat meows")
```

However, they perform different actions.

When we call:

```python id="wujj73"
dog.speak()
```

the output is:

```text id="b3a5cn"
Dog barks
```

When we call:

```python id="j5x8cf"
cat.speak()
```

the output is:

```text id="6y0wmb"
Cat meows
```

---

# 2. Same Method, Different Behavior

The important idea is:

```text id="x0v1fw"
        speak()
          │
     ┌────┴────┐
     ↓         ↓
   Dog        Cat
     │         │
     ↓         ↓
  "barks"   "meows"
```

Both objects respond to the same method:

```python id="9p4r1f"
speak()
```

but the behavior depends on which object is calling it.

---

# 3. Polymorphism with a Function

Polymorphism becomes even more useful when we write a function that works with different objects.

```python id="0c6m6v"
def make_sound(animal):
    animal.speak()


dog = Dog()
cat = Cat()

make_sound(dog)
make_sound(cat)
```

Output:

```text id="y0j9cp"
Dog barks
Cat meows
```

The function doesn't need to know whether it received a `Dog` or a `Cat`.

It simply expects the object to have a `speak()` method.

---

# 4. Duck Typing

Python often uses a concept called **Duck Typing**.

The idea is:

> If an object behaves like the required type, Python can use it.

For example:

```python id="x4tjxk"
def make_sound(animal):
    animal.speak()
```

This function doesn't check whether `animal` is specifically a `Dog` or `Cat`.

It only needs the object to provide:

```python id="m6x7c8"
speak()
```

So both objects work.

---

## 🆚 Method Overriding vs Polymorphism

### Method Overriding

A child class changes a method inherited from a parent class.

```python
class Dog(Animal):
    def speak(self):
        print("Dog barks")
```

### Polymorphism

Different objects can provide their own implementation of the same method.

```python
dog.speak()
cat.speak()
```

They don't have to inherit from the same parent for this basic Python example.

---

## 🎯 Learning Outcomes

After completing this lesson, you should understand:

* What polymorphism means.
* How different classes can use the same method name.
* How the same method can produce different behavior.
* How functions can work with different object types.
* The basic idea of Duck Typing in Python.
* The relationship between polymorphism and method overriding.

---


## 👨‍💻 Author

**Yash**

⭐ If you found this lesson useful, consider giving the repository a star.
