# Ex.No:5(D) THREAD PRIORITY

## QUESTION:
Write a java program for determine the priority and name of the current thread.

## AIM:
To write a Java program to determine and display the priority and name of a thread.

## ALGORITHM :
1.Start the program.

2.Read the thread name from the user.

3.Create a new Thread object.

4.Set the thread name using setName().

5.Retrieve the thread priority using getPriority().

6.Retrieve the thread name using getName().

7.Display the priority and name of the thread.

8.Display the thread information using the thread object.

9.Stop the program.




## PROGRAM:
 ```
/*
Program to implement a Thread Priority Concept using Java
Developed by: SHRUTHI D N
RegisterNumber: 212223240155
*/
```

## SOURCE CODE:
```
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String threadName = sc.nextLine();
        Thread t = new Thread();
        t.setName(threadName);
        System.out.println("Priority of Thread: " + t.getPriority());
        System.out.println("Name of Thread: " + t.getName());
        System.out.println(t);
    }
}
```






## OUTPUT:

<img width="1238" height="228" alt="image" src="https://github.com/user-attachments/assets/47bebc8a-6381-4b60-9d70-70979f0cb7f9" />


## RESULT:
The program successfully creates a thread, assigns it a user-defined name, and displays its default priority, name, and complete thread information.
