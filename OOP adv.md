# OOP

## 1- Inheritance

> Class Main

```java
package inheritance;

public class Main {
    public static void main(String[] args) {

       C c = new C();

       c.printA();
       c.printB();
       c.printC();

    }
}
```

> Class A

```java
package inheritance;

/*
Class A is Direct SuperClass for Class B
Class A is Indirect SuperClass for Class C
 */
public class A {

    public void printA(){
        System.out.println("Class A");
    }
}
```

> Class B

```java
package inheritance;

/*
Class B is Direct SuperClass for Class C
Class B is Direct SubClass for Class A
 */
public class B extends A {

    public void printB(){
        System.out.println("Class B");
    }
}
```

> Class C

```java
package inheritance;

/*
Class C is Direct SubClass for Class B
Class C is Indirect SubClass for Class A
 */
public class C extends B {

    public void printC() {
        System.out.println("Class C");
    }
}
```

----

## Super or This

![Super or This](super-this.png)

> Class Main

```java
package inheritance;

public class Main {
    public static void main(String[] args) {

       C c = new C();

       c.printC();

    }
}
```

> Class A

```java
package inheritance;

public class A {

    public void printA(){
        System.out.println("Class A");
    }
}
```

> Class B

```java
package inheritance;

public class B extends A{

    public void printB(){
        System.out.println("Class B");
    }
}
```

> Class C

```java
package inheritance;

public class C extends B {

    public void printC() {
        System.out.println("Class C");
        super.printB();
        this.printA();
    }
}
```

----

## multiple constructor

> Class Main

```java
package inheritance;

public class Main {

    public static void main(String[] args){

        A a1 = new A();
        A a2 = new A(12);
        A a3 = new A(10, 5);
        A a4 = new A("Ali");

        System.out.println(a1.value);
        System.out.println(a2.value);
        System.out.println(a3.value);
        System.out.println(a4.str);


    }
}
```

> Class A

```java
package inheritance;

public class A {

    public int value ;
    public String str ;

    public A(){
        this.value = 0;
    }
    public A(int c){
        this.value = c;
    }
    public A(int n1, int n2){
        this.value = n1 * n2;
    }

    public A(String s){
        this.str = s;
    }

    public void printA(){
        System.out.println("Class A");
    }
}
```

----

## Getters and setters and private

> Class Main

```java
package inheritance;

public class Main {

    public static void main(String[] args){

        A a = new A();

        int val = a.getVal();

        System.out.println(val);

        a.setVal(500);
        val = a.getVal();
        
        System.out.println(val);

    }
}
```

> Class A

```java
package inheritance;

public class A {

    private int val;

    public A(){
        this.val = 10;
    }

    public void setVal(int val){
        this.val = val;
    }

    public int getVal(){
        return this.val;
    }
}
```

----

## Protected && Default

> **You can access anything Protected if the class inherits from it or is with the same package**

## Protected

> Class Main

```java
package inheritance;

public class Main {

    public static void main(String[] args){

        int val = 10;

        System.out.println(val);

        B b = new B();

        b.printB();
    }
}
```

> Class A

```java
package inheritance;

public class A {

    protected int val;

    public A(){
        this.val = 10;
    }

    public void setVal(int val){
        this.val = val;
    }

    public int getVal(){
        return this.val;
    }
}
```

> Class B

```java
package inheritance;

public class B extends A{

    public void printB(){
        System.out.println(val * 10);
    }
}
```

## Default

> **You can access anything Default if is with the same package**

----

> Class Main

```java
package inheritance;

public class Main {

    public static void main(String[] args){

        int val = 10;

        System.out.println(val * 10);

        A a = new A();

        a.printA();
    }
}
```

> Class A

```java
package inheritance;

public class A {

     int val;

    public A(){
        this.val = 10;
    }

    void printA(){
        System.out.println(val);
    }
}
```

----

## Simple Calculater

> Class Main

```java
package calc;

public class Main {
    public static void main(String[] args) {

        System.out.println("==================== Before getter and setter ====================");

        int x = 10;
        int y = 8;

        SimpleCalc calc = new SimpleCalc(x, y);

        int result = calc.Add();

        System.out.println(x + " + " + y + " = " + result);

        result = calc.Sub();

        System.out.println(x + " - " + y + " = " + result);


        System.out.println("==================== After getter and setter ====================");

        calc.setX(35);
        calc.setY(15);

        result = calc.Add();

        System.out.println(calc.getX() + " + " + calc.getY() + " = " + result);

        result = calc.Sub();

        System.out.println(calc.getX() + " - " + calc.getY() + " = " + result);

    }
}
```

> Class A

```java
package calc;

public class SimpleCalc {
    private int x;
    private int y;

    public SimpleCalc(){
        this.x = 0;
        this.y = 0;
    }

    public SimpleCalc(int x, int y){
        this.x = x;
        this.y = y;

    }

    public int Add(){
        return this.x + this.y;
    }

    public int Sub(){
        return this.x - this.y;
    }

    public void setX(int x) {
        this.x = x;
    }
    public int getX() {
        return x;
    }

    public void setY(int y) {
        this.y = y;
    }
    public int getY() {
        return y;
    }
}
```
