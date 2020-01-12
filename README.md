# Selenium with Java Quick Reference

According to Selenium offical pages `Selenium` automates browsers. That's it!.
Before go to learn selenium it better have basic programming knowledge.

1. [Java](#Java)  
2. [Selenium](#Selenium) 

# Java 

#### Skeleton of Java ####

```
// This is a simple  program. 
class HelloWorld  { 
	// Your program begins with a call to main(). 
	// Prints "Hello, World".
	public static void main(String args[]) { 
		System.out.println("Hello, World"); 
	} 
} 
```
#### Data Types ####

Primitive | Non Primitive | 
----------| -------------|
Int       | String       | 
Char      | Array        | 
Boolean   | class        | 
Float     |              |  
Double    |              |

#### Operators and Expressions ####

 ```cpp
Arthimetic       +, -, *, /, %
Relational       <, >, <=, >=, == 
Logical          &&, ||, !
Bitwise          &, !, ~, ^
Increment        ++
Decrement        --
Assignment       =

```
Operator | Precedence| 
----------| ---------|
( )       | 3        |
*, /, %   | 2        |
+, -      | 1        |

#### Control Statements ####

 1. If-else 
 2. Switch 
 3. For Loop 
 4. While Loop 
 5. Do While 
 6. Loop Break 
 7. Continue

#### OOPs ####

`OOPs (Object-Oriented Programming System)` Object-Oriented Programming is a methodology or paradigm to design a program using classes and objects. It simplifies software development and maintenance by providing some concepts:

1. Object
2. Class
3. Encapsulation
4. Abstraction
5. Inheritance
6. Polymorphism

`Object` - Any entity that has state and behavior is known as an object

`Class` - class is a  blueprint  or Collection of objects

`Encapsulation` - Binding (or wrapping) code and data together into a single unit

`Abstraction` - Hiding internal details and showing functionality

`Inheritance`- When one object acquires all the properties and behaviors of a parent object

`Polymorphism` - If one task is performed in different ways

##### Inheritance #####
There are three types of constructors in Java:
1. Single Inheritance
2. Multilevel Inheritance
3. Hierarchical Inheritance

#### Constructor ####
A constructor is a block of codes similar to the method. It is called when an instance of the class is created. At the time of calling constructor, memory for the object is allocated in the memory.

There are two types of constructors in Java:
1. Default constructor (no-arg constructor)
2. Parameterized constructor

#### This Keyword ####
`this` - this is a reference variable that refers to the current object

#### Method Overloading  ####
If a class has multiple methods having same name but different in parameters, it is known as Method Overloading.

#### Method Overriding  ####
If subclass (child class) has the same method as declared in the parent class, it is known as method overriding in Java.

#### Exception Handling ####
The Exception Handling in Java is one of the powerful mechanism to handle the runtime errors so that normal flow of the application can be maintained.

Types of Java Exceptions
There are mainly two types of exceptions:
1. Checked Exception
2. Unchecked Exception

###### Checked Exception  ######
The classes which directly inherit Throwable class except RuntimeException and Error are known as checked exceptions e.g. IOException, SQLException etc. Checked exceptions are checked at compile-time.

###### Unchecked Exception  ######
The classes which inherit RuntimeException are known as unchecked exceptions e.g. ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException etc. Unchecked exceptions are not checked at compile-time, but they are checked at runtime.

#### Exception Handling  Keywords ####

`try` keyword is used to specify a block where we should place exception code. The try block must be followed by either catch or finally. It means, we can't use try block alone.

`catch` block is used to handle the exception. It must be preceded by try block which means we can't use catch block alone. It can be followed by finally block later.

`finally` block is used to execute the important code of the program. It is executed whether an exception is handled or not.

`throw` keyword is used to throw an exception.

`throws` keyword is used to declare exceptions. It doesn't throw an exception. It specifies that there may occur an exception in the method. It is always used with method signature.

#### Modifiers ####
There are two types of modifiers in Java: 
1. Access Modifiers 
2. Non-Access Modifiers.

###### Access Modifiers  ###### 
The access modifiers in Java specifies the accessibility or scope of a field, method, constructor, or class. We can change the access level of fields, constructors, methods, and class by applying the access modifier on it.

Type                 | Private        | Protected      | Public     | Default    |
---------------------|----------------| ---------------|------------|------------|
Inside Class         | accessible     | accessible     | accessible | accessible |
Inside package       | not accessible | accessible     | accessible | accessible |
outside package by subclass only  | not accessible | accessible | accessible | not accessible |
outside package      | accessible     | not accessible | accessible | not accessible |

###### Non Access Modifiers  ###### 
1. static modifier   - The static keyword is used to create variables that will exist independently of any instances created for the class. Only one copy of the static variable exists regardless of the number of instances of the class.
2. final modifier    - A final variable can be explicitly initialized only once. A reference variable declared final can never be reassigned to refer to an different object.
3. abstract modifier -An abstract class can never be instantiated. If a class is declared as abstract then the sole purpose is for the class to be extended
4. synchronized      - which are used for threads.
5. volatile modifiers-which are used for threads.

# Selenium 

### Selenium with Java ###

#### Skeleton of Selenium with Java ####
```java
package test;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class TestNow {
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		String baseURL = "http://www.google.com";
		WebDriver driver;
		System.setProperty("webdriver.chrome.driver", "chromedriver.exe");
		driver = new ChromeDriver();
		driver.get(baseURL);
	}
}
```
#### FindElement ####

There many ways we can find object 
1. ID
2. Name
3. Class Name
4. Tag Name
5. Link Text
6. Partial Link Text
7. XPATH
8. Css selector

###### Example ######

```java
// By Id
driver.findElement(By.id("lst-ib")).sendKeys("Hello");

// By Xpath
driver.findElement(By.xpath("//*[@id='sblsbb']/button")).click();

// By Name		
driver.findElement(By.name("btnG")).click();

// By Link Text
driver.findElement(By.linkText("Login")).click();

// By Partial Link Text
driver.findElement(By.partialLinkText("Pract")).click();

// By Class Name
driver.findElement(By.className("title")).click();

```
#### Css selector ####

`Syntax: tag[attribute='value'] `
  
```java

// By Id input[id=displayed-­‐text]	
// Byclass input[class=displayed-­‐class]	
 driver.findElement(By.cssSelector("input[id=displayed-­‐text]"));
// we can Append .class1.class2.class -->  Until we find a unique element
```
`Using wildcards` :

1. “^”	->	Represents	the	starting	text
2. “$”	->	Represents the	ending	text
3. “*”	->	Represents	the	text	contained

` Syntax: tag[attribute<special	character>=’value’] `

```java
input[class='inputs']	->	Only 1 matching node
input[class^='inputs']	->	Two	matching nodes
input[class='displayed-class']	-> No matching nodes // here class = name-displayed-class
input[class$='class']	->	One	matching node
input[class*='displayed-class']	->	One	matching node
```
`Finding Children` :

```java
fieldset	->	10 matching nodes
Fieldset>table
fieldset>#product	
fieldset>button	
Fieldset>a
fieldset>input#name
```

#### Xpath ####

Difference between single ‘/’ or double ‘//’
1. Single slash ‘/’ anywhere in xpath signifies to look for the element immediately inside the parent element.
2. Double slash ‘//’ signifies to look for any child or nested-child element inside the parent element.

`Syntax: //tag[@attribute='value']`

```java
// By Xpath
driver.findElement(By.xpath("//*[@id='sblsbb']/button")).click();
// it's always better to tag name instead of using *, shown below
driver.findElement(By.xpath("//div[@id='sblsbb']/button")).click();
```

1. Absolute Xpath: It uses Complete path from the Root Element to the desire element. 
2. Relative Xpath: You can simply start by referencing the element you want and go from there. Always Relative Xpaths are preferred as they are not the complete paths from the Root element

Relative xpath using single ‘/’ 
```java
//div[@id='navbar']/div/div/div/ul/li[2]/a
```
Relative xpath using double ‘//’
```java
//div[@id='navbar']//ul/li[2]/a
```
Using Text of the element to build xpath
Finding Hello link:
```java
//div[@class='homepage-hero']//a[text()='Hello']
```
Using Contains to find the elements:

` Syntax: //tag[contains(attribute, ‘value’)] `

Finding Login link:
```java
//div[@id='navbar']//a[contains(text(),'Login')]
//div[@id='navbar']//a[contains(@class,'navbar-link') and contains(@href,'sign_in')]
```

Using Starts-With to find the elements:

`Syntax: //tag[starts-with(attribute, ‘value’)]`

Finding Login link:
```java
//div[@id='navbar']//a[starts-with(@class,'navbar-link')]

Parent
`Syntax: xpath-to-some-element//parent::<tag>`

Preceding Sibling
`Syntax: xpath-to-some-element//preceding-sibling::<tag>`

Following Sibling
`Syntax: xpath-to-some-element//following-sibling::<tag>`

Find the price of the course “Python Programming Language”
//table[@id='product']//td[text()='Python Programming Language']//following-sibling::td

Find Author of the book “The Green Mile”
//div[@id='gridbox']//a[text()='The Green Mile']//parent::td//following-sibling::td[1]
```
#### JUnit ####
JUnit is open sourde Automated test Framework
It has quite annotation,but let this five annotation
1. @BeforeClass - This will before first test method in current class
2. @AfterClass - This will After last test method in current class
3. @Before - This will before each test method 
4. @After - This will After each test method 
5. @Test - This aprt of test case