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

> Class SimpleCalc

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

----

## Anthor Calculater

> Class Main

```java
package calc;

public class Main {
    public static void main(String[] args) {

        int x= 4;
        int y= 2;

       AnotherCalc calc = new AnotherCalc(x, y);

       float result = calc.Add();

        System.out.println(x + " + " + y + " = " + result);

        result = calc.Sub();

        System.out.println(x + " - " + y + " = " + result);

        result = calc.Mul();

        System.out.println(x + " * " + y + " = " + result);

        result = calc.Div();

        System.out.println(x + " / " + y + " = " + result);
    }
}
```

> Class SimpleCalc

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

> Class AnotherCalc

```java
package calc;

public class AnotherCalc extends SimpleCalc{

 /*   public AnotherCalc(){
        super();
    }*/

    public AnotherCalc(int x, int y){
        super(x, y);
    }

    public int Mul(){
        return this.getX() * this.getY();
    }

    public int Div(){
        int y = this.getY();

        if(y == 0){
            return -1;
        }else {
            return this.getX() / y;
        }
    }
}
```

----

## Static variables

> Class Main

```java
package calc;

public class Main {
    public static void main(String[] args) {

        A.y = 9;

        System.out.println(A.y);

        A z = new A();
        A r = new A();

        z.x = 10;
        r.x = 11;

        System.out.println(z.x);
        System.out.println(r.x);

        A.y = 99;

        System.out.println(A.y);
    }
}
```

> Class A

```java
package calc;

public class A {

    public int x;
    public static int y;
}
```

----

## Static Methods

> Class Main

```java
package calc;

public class Main {
    public static void main(String[] args) {

        A z = new A();

        z.PrintNotStatic();

        A.PrintStatic();

        int result = A.Add(15, 45);

        System.out.println(result);
    }
}
```

> Class A

```java
package calc;

public class A {

    public int x;
    public static int y;

    public static void PrintStatic(){
        System.out.println("This Method using Static");
    }

    public void PrintNotStatic(){
        System.out.println("This Method not using Static");
    }

    public static int Add(int a, int b){
        return a+b;
    }
}
```

----

## Static Calculater

> Class Main

```java
package calc;

public class Main {
    public static void main(String[] args) {

        int a = 12;
        int b = 4;

        int result = A.Add(a, b);

        System.out.println(a + " + " + b + " = " + result);

        result = A.Sub(a, b);

        System.out.println(a + " - " + b + " = " + result);

        result = A.Mul(a, b);

        System.out.println(a + " * " + b + " = " + result);

        result = A.Div(a, b);

        System.out.println(a + " / " + b + " = " + result);
    }
}
```

> Class A

```java
package calc;

public class A {

    public static int Add(int a, int b){
        return a + b;
    }

    public static int Sub(int a, int b){
        return a - b;
    }

    public static int Mul(int a, int b){
        return a * b;
    }

    public static int Div(int a, int b){

        if(b == 0){
            return -1;
        }
        return a / b;
    }
}
```

----

## The objects count with static

> Class Main

```java
package calc;

public class Main {
    public static void main(String[] args) {

        TheCount a = new TheCount();
        TheCount b = new TheCount();
        TheCount c = new TheCount();

        System.out.println("The objects count: " + TheCount.getCount());
    }
}
```

> Class TheCount

```java
package calc;

public class TheCount {

    private static int count = 0;

    public TheCount(){
        count++;
    }

    public static int getCount(){
        return count;
    }
}
```

----

## Method overloading

> Class Main

```java
package calc;

public class Main {
    public static void main(String[] args) {

        A a = new A();

        int r1 = a.Add(12, 4);
        int r2 = a.Add(45);

        System.out.println(r1);
        System.out.println(r2);

    }
}
```

> Class A

```java
package calc;

public class A {

    private int x,y;

    public int Add(int a, int b){
        this.x = a;
        this.y = b;

        return this.x + this.y;
    }
    public int Add(int a){
        this.x = a;

        return this.x + this.x;
    }
}
```

----

## @Override

> Class Main

```java
package calc;

public class Main {
    public static void main(String[] args) {

        A a = new A();

        a.PrintA();

        B b = new B();

        b.PrintA();

    }
}
```

> Class A

```java
package calc;

public class A {

   public void PrintA(){
       System.out.println("Class A.");
   }
}
```

> Class B

```java
package calc;

public class B extends A{

    @Override
    public void PrintA() {
        System.out.println("Class B");
    }
}
```

----

## method overload vs method override

> Class Main

```java
package calc;

public class Main {
    public static void main(String[] args) {

        A a = new A();

        a.PrintA();
        a.Demo();
        a.Demo(12);

        B b = new B();

        b.PrintA();
        b.Demo(2.4F);

    }
}
```

> Class A

```java
package calc;

public class A {

   public void PrintA(){
       System.out.println("Class A.");
   }

   public void Demo(){
       System.out.println("Demo1 from A");
   }

    public void Demo(int a){
        System.out.println("Demo2 from A");
    }
}
```

> Class B

```java
package calc;

public class B extends A{

    @Override
    public void PrintA() {
        System.out.println("Class B");
    }

    public void Demo(float a){
        System.out.println("Demo3 from B");
    }
}
```
