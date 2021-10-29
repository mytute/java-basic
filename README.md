# JAVA  

## download and installing java

google java jdk (java development kit)

(In here we are going to use "IntelJ" code editor)
note :
(JRE java runtime environment for run Main.class file in any os )
# Anatomy of a JAVA program

* smallest building block in java programs are function
 (function - a block of code that performs a task )

### function

* syntax

ReturnType name_of_function(){

}

if no return we are put 'void' keyword

* main funtion

every program of the java have at least one function call 'main'.    
'main' function is the entry point of our program to execute it.

* class

class is a container for related functions.    
every java program should have at least one class call main.

class Main{
  void main(){

  }
}

inside Main class curly braces we are put the methods. when function inside in the class it's call method.

we have access modifier for classes and methods like "public" and "private" that make allow access
current class from diffrent class.

## make proper name for "Classes" and "Methods".
PascalNamingConvention (first letter of every work is uppercase )  >for Classes
camelNamingConvention (first letter of every work is uppercase except first word) >for methods.

## start first java program using IntelJ IDEA
1 open IntelJ and click 'Create New Project'    
2 new open window select java && select project SDK && click next.    
3 new open window select "Command Line App" && click next.    
3 new open window give the Project name && click next.    
    com.package is the concept that group the classes.    
4 go created project directory [projectName>src>packageName>Main.java] 

 
If you want create class by scratch      
[r-click] on 'src' folder > [select] 'new' > [select] 'Java Class' > [write] "main"   


```java
package com.company;

public class Main {

    public static void main(String[] args) {
	   System.out.println('hellow world');
    }
}
```
 System[class].out[function].println[method] you can see this data where IntelJ suggetions
 when you typing.

 To execute > click run button

# How Java Code Gets Executed. (background process)
  1 Compilation
  2 Execution

  run on IntelJ
  Source code(.java) > Java Compiler > Byte Code(.class)

  background process
  Byte Code(.class) > Java Virtual Machine > Native Code(windows,mac)


  to compile our Main.java
  step-1 r-click Main.java tap > select "open terminal"
  step-2 $ javac Main.java
  step-3 go to project src path
  step-4 $java com.packagename.Main
          this will execute project Main.class file that we complied.

  Java Editions.
  Standard Edition(SE) -  core java platform, contain every libulary
  Enterprise Edition(EE) - for large scale and distribute system. have addtional libulary
  Micro Edition(ME) - for mobile . have libularies for mobile.
  Java Card - for smart cards  

## Types

1 Variables and Constants.
2 Primitive and Reference Types.
3 Casting.
4 Numbers, Strings and Arrays.
5 Read Input.

### Variables and Constants.

```java
package com.company;
public class Main {
    public static void main(String[] args) {
        int myAge = 30, temperature =20 ; // multiple variable in same line
        int herAge = myAge; // copy value from variable
	    System.out.println(herAge);
    }
}
```

 int - type of variable.
 age - name of variable(memory location).
 30  - value of variable.

### Primitive and Reference Types.

  Primitive - for storing simple values.
  Reference - for storing complex objects.

   byte     1    [-128,127]
   short    2    [-32K,32K]
   int      4    [-2B, 2B]   
   long     8    []
   float    4    []
   double   8    []
   char     2    [A, B, C..]   
   boolean  1    [ true, false]  

   K- thousand B- Billion

```java
package com.company;
public class Main {
    public static void main(String[] args) {

        // hole number
        long viewsCount = 3_123_456_789L;
        // (java)not declare as 'int' have to add end"L or l"
        // can divide number using underscore
        System.out.println(viewsCount);

        // number with desimal
        float price = 10.99F;
        // (java)not to declare as 'double' add end"F or f".
        System.out.println(price);

        // define character
        char letter = 'A';
        // use single '' for char. for string  double ""
        System.out.println(letter);

        // define boolean
        boolean isEligible = true;
        // value can be only true or false.
        System.out.println(isEligible);

    }
}
```

### Primitive vs Reference

```java
package com.company;

import java.util.Date; // import Date class from java.util package.
import java.awt.*;    // import for definde Point

public class Main {
    public static void main(String[] args) {

        byte age = 30;
        // 'new' keyword make new memory allocation for this 'date' variable from blueprint of 'Date' class.
        // jre take care of releasing this memory allocation when further not using.
        // using dot(eg date.getTime()) operator we can define instance methods of Date() class.
        Date date = new Date();
        System.out.println(date);
        System.out.println(date.getTime());

        Point point1 = new Point(1,1);
        Point point2 = point1;
        point1.x = 2; // as a reference this is this will change point2 value too.
        System.out.println(point2);

    }
}
```

### String
string is sequence of characters.
string is reference type on java. but they are immutable(value not effect with reference).    

```java
package com.company;

public class Main {
    public static void main(String[] args) {
        // there are tow methods to define sting variables.
        String message1 = new String("hello world");
        String message2 = "hello world"; // but this is not primitive type !.
        System.out.println(message1);

        // just see some string functions.
        String msg = "hello world" ;
        System.out.println(msg.endsWith("d"));
        System.out.println(msg.startsWith("h"));
        System.out.println(msg.length());
        System.out.println(msg.indexOf("l")); // get matched first index in string.
        System.out.println(msg.replace("l","z")); // replace all matched characters.
        System.out.println(msg.toLowerCase()+" " +msg.toUpperCase());
        System.out.println(msg.trim()); // remove unnecessary white spaces(start and end string)

        System.out.println(msg); // not effect to original string

    }
}
```

### Escape Sequence

```java
package com.company;

public class Main {
    public static void main(String[] args) {
        // escape double quotes
        String str1 = "Hello \"Mosh\" "; // result Hello "Mosh"
        System.out.println(str1);

        // escape backslash
        String str2 = "c:\\Windows\\.."; // c:\Windows\..
        System.out.println(str2);

        // new line or tab
        String str3 = "c:\nWindows\t.."; //
        System.out.println(str3);
    }
}
```

### Array
use to store list of items(numbers,names ...)

once we define array we cannot add or remove additional items(not like collections).    
```java
package com.company;

import java.util.Arrays; // import array class

public class Main {
    public static void main(String[] args) {
        // *** arrays have fix length ***

        // array define method one
        int[] numbers = new int[5]; // format > type name = new type[length]
        numbers[0] = 1;
        numbers[1] = 2;
        System.out.println(numbers); // [I@7b23ec81 > object address of memory
        System.out.println(Arrays.toString(numbers)); // [1, 2, 0, 0, 0] > array represent as string.
                                                      // * not effect to original(memory location).

        // array define method two
        int[] nums = {2,3,4,5,1,4}; // format > type name = new type[length]
        System.out.println(nums.length);
        Arrays.sort(nums); // effect to original and same memory location.
        System.out.println(Arrays.toString(nums));

        // multidimensional arrays
        int [][] multi = new int[2][3]; // like this can define 3d arrays too
        multi[0][0] =1 ;
        System.out.println(Arrays.toString(multi)); // ** not work for multidimensional
        System.out.println(Arrays.deepToString(multi)); // not work for multidimensional

        // sort way to define array
        int [][] num = {{1,2,3},{3,4,5}};
        System.out.println(Arrays.deepToString(num));
    }
}
```

### Constants

variable that not want to change it value call "Constant".
```java
package com.company;

public class Main {
    public static void main(String[] args) {

        final float PI = 3.14F; // "final" keyword make unchangeable variable
        // it's good to use capital letter for define Constants
    }
}
```


### Arithmetic Expressions.    

```java
package com.company;

public class Main {
    public static void main(String[] args) {

       int add = 10+3;
       System.out.println(add); // > 13

       int subtract = 10-3;
       System.out.println(subtract); // > 7

       int multiplication = 10*3;
       System.out.println(multiplication); // > 30

       int divisionIntNumber = 10/3; // > 3
       double divisionFloatNumber = (double)10/(double)3; // 3.333..
       System.out.println(divisionFloatNumber);

       // increment and decrement operator
        int x =1 ;
        int y = ++x; // y get value after increment of x
        System.out.println(y);
        int w = 1;
        int z = w++; // z get value before increment of w
        System.out.println(z);

        int p = 1;
        p = p + 2; // compound assignment
        p += 2; // augmented assignment operators
        p /= 1; // augmented assignment operators

        // order of operations> () , */ ,+-
    }
}
```

### Casting  and Type Conversion.
```java
package com.company;

public class Main {
    public static void main(String[] args) {

        // ** compatible casting
        // byte > short > int > long > float > double  values convert automatically small in big size.

        // implicit casting (no data lost)
        short x = 1 ; //  2 bytes memory allocation
        int y = x + 2 ; // 4 bytes memory allocation
        System.out.println(y);

        // explicit casting (can be data lost)
        double p = 1.1;
        int q = (int) p + 2;
        System.out.println(q);

        // ** incompatible casting
        String a = "1";
        int b = Integer.parseInt(a) + 2 ;
        System.out.println(b);
        // Double.parseInt(a) , Float.parseFloat(a)
    }
}
```

### The Math Class.    
```java
package com.company;

public class Main {
    public static void main(String[] args) {

        int round = Math.round(1.1F); // result = 1
        int ceil  = (int)Math.ceil(1.1F); // result = 2
        int floor  = (int)Math.floor(1.1F); // result = 1
        int max   = Math.max(1,3);  // result = 3
        int min   = Math.min(1,3);  // result = 1
        double random   = Math.random();  // random double type number between 0-1
        int randomInt = (int) Math.round(Math.random()*100);
        System.out.println(randomInt);
    }
}
```

### Formatting Numbers   
```java
package com.company;

import java.text.NumberFormat;

public class Main {
    public static void main(String[] args) {

        NumberFormat currency = NumberFormat.getCurrencyInstance(); // define number format class
        String result1 = currency.format(1234567.891); // define format of the number
        System.out.println(result1);

        NumberFormat percent = NumberFormat.getPercentInstance(); // define number format class
        String result2 = percent.format(0.1); // define format of the number
        System.out.println(result2);
    }
}
```

### Reading Input    
```java  
package com.company;

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

    }
}
```   

### Comparison Operators(operators to compare primitive values)
 TODO

### If Statement
```java
package com.company;

public class Main {
    public static void main(String[] args) {
       int income = 120_000;

       // single statement without curly braces
        if(income > 100_000){
            System.out.println("frist");
            System.out.println("second");
        }
        else if(income < 120_000)
            System.out.println("three");
        else
            System.out.println("four");


       // simplifying if statements
        boolean hasHighIncome = income > 100_000;

       // ternary operator
        String className = income > 100_000 ? "Frist" : "Economy";
    }
}

```     

### Switch Statement

``` java
package com.company;

public class Main {
    public static void main(String[] args) {

        String role = "Admin";

        switch (role){
            case "admin":
                System.out.println("you're an admin");
                break;
            case "moderator":
                System.out.println("you're a moderator");
                break;
            default:
                System.out.println("you're a guest");
        }
    }
}
```   
### Loops (for,while,do while, foreach)    

```java
package com.company;

import java.util.Scanner; // for input user value

public class Main {
    public static void main(String[] args) {
        // for loop structure
        for(int i = 0; i < 5; i++ ){ // curly braces need when multiple statements only
            System.out.println("Hello world.."+i);
        }

        // while loops ex 1
        int i =2;
        while(i>0){
            System.out.println("Hello world "+ i);
            i--;
        }
        // while loops ex 2
        Scanner scanner = new Scanner(System.in);
        String input = "";
        while(!input.equals("quit")){
            System.out.print("Enter cmd : ");
            input = scanner.next();
            if (input.equals("pass")) // stop flow from here and continue from start
                continue;
            if (input.equals("quit"))
                break; // you can replase condition "!input.equals("quit")" > "true"
            System.out.println(input);
        }
        scanner.close(); // you can remove when no need further memory allocation

        //Do while loops
        Scanner scanner_do = new Scanner(System.in);
        String input_do = "quit";
        do {
            System.out.print("Enter cmd : ");
            input = scanner.next();
            System.out.println(input);
        }while(!input.equals("quit"));


        // for Each loop
        // only forward, no access to item index
        String[] fruits = {"Apple", "Mango", "Orange"};
        for(String fruit : fruits ){
            System.out.println(fruit);
        }

    }
}
```

## eclipse
[click] create java project > {new window}[click] don't create module >
[r-click] "src" file on left bar > [select] "new" > [select] "class" >
[checked] "public static void main (String[] args)" for only first file and
[input] name.

add JRE system library
[r-click] on project > [click] properties > [select] "Java Build Path" >
{java build path}[select tab] "libulares" > [click]"Add Library" >
[select] "JRE System Library"

to change theme
{toolbar}[click]"window" > [click]"Preference" > [click] "General" >
[click] "Appearance" > {on Appearance} [select] theme you want.


### Read files
here read file and store in "Array List"

List<String> = just interface  
new ArrayList<String> = specific implementation on that interface.

```java
package java_pro;

import java.io.File;
import java.io.FileNotFoundException;
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class kangaroo {

	public static void main(String[] args) throws FileNotFoundException {

	   // import new file on the system
	   File file = new File("C:\\Users\\Admin\\Desktop\\java research\\text.txt"); // define file location

	   Scanner upload = new Scanner(file); // get file to java program

	   List<String> students = new ArrayList<String>(); // define array list.

	   while(upload.hasNextLine()) { // read if there have any next line after already read
		   //System.out.println(upload.nextLine()); // read  file line by line
		   students.add(upload.nextLine());
	   }

	   for(int i =0; i < students.size(); i++) {
		   System.out.println("name: "+students.get(i));
	   }

	   System.out.println("upload next line :"+upload.hasNextLine()); // is there any next line on the file
       upload.close();
	}

}
```


## LinkedList , add, push, remove, pop, removeFirst     

in "LinkList" there have "add" and "remove" functions.  

```java
package java_pro;


import java.util.LinkedList;

public class kangaroo {

	public static void main(String[] args)  {

      LinkedList<String> names = new LinkedList<String>();
      names.add("samadhi");
      names.add("laksahan");
      names.add("piyasiri"); // add to end
      names.push("pasindu"); // add to start

      System.out.println(names);

      System.out.println(names.pop()); // remove from start
      System.out.println(names.remove()); // remove from start when no argument
      System.out.println(names.removeFirst()); // remove from start
      System.out.println(names.remove()); // remove  x index when include argument

	}

}
```


## iterator


````java
package java_pro;

import java.util.Iterator;
import java.util.LinkedList;
import java.util.ListIterator;

public class kangaroo {

	public static void main(String[] args)  {

		LinkedList<String> names = new LinkedList<String>();

		names.push("samadhi"); // add to start of list
		names.push("laksahan");
		names.push("piyasiri");
		names.add(2,"pasindu"); // add value to x index of list position.

        // make iterator ********************************************
		Iterator<String> it = names.iterator();

		//System.out.println(it.next());
		//System.out.println(it.next());
		//System.out.println(it.next());

		while(it.hasNext()) { // use while loop to print iterable values
			System.out.println(it.next());
		}

		for(String n: names) { // output same result (forEach loop)
			System.out.println("loop :"+n);
		}

		LinkedList<String> plaese = new LinkedList<String>();
		plaese.push("balangoda"); // add to start of list
		plaese.push("rathnapura");
		plaese.push("colombo"); // add value to x index of list position.

        // make list iterator ****************************************
		ListIterator<String> lit = plaese.listIterator();

		lit.next();
		lit.next();
		lit.add("binari"); // add to 2 index in plaese list but not lit because lit already defined.

		for(String n: plaese) { // output same result (forEach loop)
			System.out.println("plaese :"+n);
		}

	}

}
```       









###  shortcust for some ide's
###  "sout+Tab"  for System.out.println();
