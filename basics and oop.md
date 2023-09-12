# Basics

## 1- String equal with or without Case

```java
package test;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter Your Site: ");
        String site = input.next();
        String xSite = "www.ali.net";

        if(xSite.equalsIgnoreCase(site)){
            System.out.println("ok");
        }else {
            System.out.println("Not ok");
        }

    }
}
```

----

## 2- Array

```java
//way 1:

package test;

public class Main {
    public static void main(String[] args) {
       int[] z = new int[5];

       z[0] = 1;
       z[1] = 2;
       z[2] = 3;
       z[3] = 4;

        System.out.println(z[0]);
        

    }
}
```

```java
//Way 2:
package test;

public class Main {
    public static void main(String[] args) {
        int[] z = {1, 2, 3, 4};
        System.out.println(z[3]);
    }
}
```

```java
package test;

public class Main {

    public static int[] createArray(int size){

        return new int[size];
    }

    public static void main(String[] args) {
        //Variable size array
        int[] z = createArray(5);
        System.out.println(z.length);

        //fixed size array
        int[] x = new int[8];
        int[] y = {1, 2, 3};

    }
}
```

```java
package test;

public class Main {

    public static void main(String[] args) {

        int [] a = {1, 2, 3, 4};
//       way 1 to access array
        System.out.println("=======================Way 1================");

        for(int i = 0; i < a.length; i++){
            System.out.println(a[i]);
        }
//       way 2 to access array
        System.out.println("=======================Way 2================");

        for(int value : a){
            System.out.println(value);
        }

    }
}
```

```java
// 2-D array
package test;

public class Main {

    public static void main(String[] args) {

        int [][] x = {
                {1, 2, 3},
                {4, 5, 6},
                {7, 8, 9}
        };

        for (int[] rows : x) {
            for (int cols : rows) {
                System.out.println(cols);
            }
        }


    }
}
```

----

## 3- Data Type

```java
//float and double
package test;

public class Main {

    public static void main(String[] args) {

        float x = 1.5f;
        double y = 1.877868963782165489686735987264986239;


        System.out.println(x + x);
        System.out.println(y + y);
    }
}
```

```java
// short, int and long
package test;

public class Main {

    public static void main(String[] args) {
		byte x = 127; // -128 to 127
        byte y = -128; // -128 to 127
        short x = 12345; // 16 bit
        int y = 1234567890; // 32 bit
        long z = 1234567890121123213L; // 64 bit

        System.out.println(x + "\n" + y + "\n" + z + "\n");

    }
}
```

```java
// Boolean
package test;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter 'true' or 'false':");
        boolean x = input.nextBoolean();

        if(x){
            System.out.println("Yes");
        }else {
            System.out.println("No");
        }
        
    }
}
```

----

## 4- Print String

----

```java
package first;

public class Main {

	public static void main(String[] args) {

		String site = "www.ali.net";
		
		for(int i = 0; i < site.length(); i++) {
			
			char ch = site.charAt(i);
			
			System.out.print(ch + " ");
		}
		
		System.out.println();

		for(int i = site.length() - 1; i >= 0 ; i--) {
			
			char ch = site.charAt(i);
			
			System.out.print(ch + " ");
		}

	}

}
```

----

### String To Array

>Class StrOp

```java
package first;


public class StrOp {
	
	public String value;
	
	public StrOp(String s) {
		this.value = s;
	}
	
	public char [] strToArray() {
		
		int length = value.length();
		
		char [] ch = new char[length];
		
		for(int i = 0; i < length; i++) {
			ch[i] = value.charAt(i);
		}
		
		return ch;
		
	}
	
	
}
```

>Main Class

```java
package first;

public class Main {

	public static void main(String[] args) {
		
		StrOp str = new StrOp("Hello!");
		
		char [] ch = str.strToArray();
	
		for (char c : ch) {
			System.out.println(c);
		}
		System.out.println(ch);
		
	}

}

```

----

### calculator

>Class Calc

```java
package first;

public class Calc {
	
	public int sum(int number1, int number2) {
		
		return number1 + number2;
	}

	public int sub(int number1, int number2) {
		
		return number1 - number2;
	}
	
	public int mul(int number1, int number2) {
		
		return number1 * number2;
	}
	
	public int div(int number1, int number2) {
		
		if(number2 == 0) {
			return 0;
		}
		else {
			return number1/number2;
		}
	}
	
	public int [] mulArray(int [] a, int [] b) {
		
		if(a.length != b.length) {
			return null;
		}
		else {
			int [] c = new int[a.length];
			
			for(int i = 0; i < a.length; i++) {
				c[i] = a[i] * b[i];
			}
			return c;
		}
	}

}
```

>Main Class

```java
package first;

public class Main {

	public static void main(String[] args) {
		
		Calc c1 = new Calc();
		
		int [] a = {1, 2, 3, 4, 5, 90};
		int [] b = {10, 20, 30, 40, 50};
		
		int [] c = c1.mulArray(a, b);
		
		if(c == null) {
			System.out.println("Null");
		}else {
			for (int i : c) {
				System.out.println(i);
			}
		}
		
	}

}
```

----

### Book

>Class Book

```java
package first;

public class Book {

	public String name;
	public String author;
	public int pubDate;
	
	public int lastPageNumber;
	public int currentPage;
	
	public boolean isOpen;
	
	public Book(String name, String author, int pubDate, int lastPageNumber) {
		this.name = name;
		this.author = author;
		this.pubDate = pubDate;
		this.lastPageNumber = lastPageNumber;
		this.isOpen = false;
	}
	
	void openBook() {
		if(isOpen) {
			System.out.println("Is Open");
		}else {
			isOpen = true;
		}
	}
	
}
```

>Main Class

```java
package first;

public class Main {

	public static void main(String[] args) {
		
		Book b = new Book("Java", "Ali BAsheer", 2020, 150);
		
		b.openBook();
		b.openBook();
		
	}

}
```
