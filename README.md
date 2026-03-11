תקציר OOP בפייתון – גרסת שינון מהירה

OOP – Object Oriented Programming

OOP היא גישת תכנות שבה בונים את הקוד סביב אובייקטים.
כל אובייקט כולל נתונים (attributes) והתנהגות (methods).

המטרה של OOP:

ארגון קוד

שימוש חוזר בקוד

תחזוקה קלה יותר

מודל של העולם האמיתי

Class

Class היא תבנית (Blueprint) שמגדירה איך אובייקטים יראו.

דוגמה

class Dog:
pass

Object

Object הוא מופע שנוצר מהמחלקה.

דוגמה

dog = Dog()

Dog = class
dog = object

Constructor

Constructor הוא מנגנון שיוצר ומאתחל אובייקט.

בפייתון משתמשים ב:

init

init

מתודה שמאתחלת את האובייקט ומקבלת ערכים התחלתיים.

דוגמה

class Person:

def __init__(self, name, age):

    self.name = name
    self.age = age

self

self מייצג את האובייקט הנוכחי.

באמצעות self אפשר לגשת ל:

שדות של האובייקט

מתודות של האובייקט

דוגמה

self.name
self.age

Instance Attribute

משתנה ששייך לאובייקט מסוים.

דוגמה

class Dog:

def __init__(self, name):

    self.name = name

Class Attribute

משתנה ששייך למחלקה עצמה ומשותף לכל האובייקטים.

דוגמה

class Dog:

species = "Mammal"

Instance Variable vs Class Variable

Instance Variable
שייך לכל אובייקט בנפרד.

Class Variable
משותף לכל האובייקטים של המחלקה.

גישה ל-Class Variable

אפשר לגשת דרך האובייקט:

dog.species

או דרך המחלקה:

Dog.species

Instance Method

מתודה שעובדת על אובייקט מסוים ומקבלת self.

דוגמה

class Dog:

def bark(self):

    print("Woof")

Class Method

מתודה שעובדת על המחלקה.

מקבלת cls.

דקורטור:

@classmethod

דוגמה

class Dog:

count = 0

@classmethod
def show_count(cls):

    print(cls.count)

Static Method

מתודה שלא משתמשת ב-self ולא ב-cls.

דקורטור:

@staticmethod

דוגמה

class MathHelper:

@staticmethod
def add(a, b):

    return a + b

מתי משתמשים ב-staticmethod

כאשר הפונקציה קשורה למחלקה
אבל לא צריכה מידע מהאובייקט או מהמחלקה.

Encapsulation

Encapsulation = הסתרת נתונים בתוך מחלקה.

מטרות:

הגנה על נתונים

שליטה בגישה

בדיקות תקינות

Private Variable

משתנה שמתחיל ב-__.

דוגמה

self.__balance

זה לא private מוחלט אבל נותן הגנה מסוימת.

Getter

פונקציה שמחזירה ערך של משתנה.

Setter

פונקציה שמעדכנת ערך עם בדיקות.

דוגמה

class Person:

def __init__(self, age):

    self.__age = age

def get_age(self):

    return self.__age

def set_age(self, age):

    if age >= 0:

        self.__age = age

Name Mangling

כאשר משתנה מתחיל ב-__
פייתון משנה את השם הפנימי שלו.

לדוגמה

__age

נהיה

_Person__age

Inheritance

Inheritance = ירושה בין מחלקות.

מחלקה אחת יורשת שדות ומתודות ממחלקה אחרת.

Parent Class

מחלקת האב.

Child Class

מחלקת הבן שיורשת מהאב.

דוגמה

class Animal:
pass

class Dog(Animal):
pass

Method Overriding

כאשר מחלקת הבן מחליפה מתודה של האב.

דוגמה

class Animal:

def speak(self):

    print("sound")

class Dog(Animal):

def speak(self):

    print("woof")

super()

super() מאפשר לקרוא למתודות של מחלקת האב.

דוגמה

class Animal:

def __init__(self, name):

    self.name = name

class Dog(Animal):

def __init__(self, name, age):

    super().__init__(name)

    self.age = age

Abstract Method

מתודה שחייבים לממש במחלקת הבן.

אם לא מממשים – אי אפשר ליצור אובייקט.

Polymorphism

Polymorphism = אותה מתודה יכולה להתנהג אחרת במחלקות שונות.

דוגמה

class Dog:

def speak(self):

    print("woof")

class Cat:

def speak(self):

    print("meow")

Dunder Methods

מתודות מיוחדות עם __ לפני ואחרי השם.

דוגמאות

init
str
repr
len
eq

str

מחזירה תצוגה קריאה של האובייקט.

print(object)

repr

ייצוג טכני יותר של האובייקט למפתחים.

len

קובע מה יחזיר:

len(object)

eq

קובע איך עובד:

object1 == object2

דוגמת מחלקה מלאה

class Person:

def __init__(self, name, age):

    self.name = name
    self.age = age

def __str__(self):

    return f"Person(name={self.name}, age={self.age})"

דוגמת ירושה

class Animal:

def speak(self):

    print("sound")

class Dog(Animal):

def speak(self):

    print("woof")

class Cat(Animal):

def speak(self):

    print("meow")

דוגמת BankAccount

class BankAccount:

def __init__(self, owner, balance):

    self.owner = owner
    self.balance = balance

def deposit(self, amount):

    if amount > 0:

        self.balance += amount

def withdraw(self, amount):

    if amount <= self.balance:

        self.balance -= amount
