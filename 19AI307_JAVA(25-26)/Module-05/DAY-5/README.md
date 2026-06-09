# Ex.No:5(E) MULTITHREADING -SYNCHRONIZATION

## QUESTION:
Use a synchronized block (not method) to safely increment a shared counter using multiple threads.

## AIM:
To write a Java program that uses a synchronized block to safely increment a shared counter using multiple threads and prevent race conditions.

## ALGORITHM :
1.Start the program.

2.Create a Counter class with a shared variable count.

3.Create a lock object for synchronization.

4.Define an increment() method that increases count inside a synchronized block.

5.Create a Worker class that extends Thread.

6.Pass the shared Counter object and number of increments to each worker thread.

7.In the run() method, repeatedly call increment().

8.Read the number of threads and increments per thread from the user.

9.Create and start all worker threads.

10.Wait for all threads to finish using join().

11.Display the final value of the counter.

12.Stop the program.




## PROGRAM:
 ```
/*
Program to implement a Synchronization concept using Java
Developed by: 
RegisterNumber:  
*/
```

## SOURCE CODE:
```
import java.util.Scanner;
class Counter {
    private int count = 0;
    private final Object lock = new Object();
    public void increment() {
        synchronized (lock) {  
            count++;
        }
    }
    public int getCount() {
        return count;
    }
}
class Worker extends Thread {
    private final Counter counter;
    private final int increments;
    public Worker(Counter counter, int increments) {
        this.counter = counter;
        this.increments = increments;
    }
    public void run() {
        for (int i = 0; i < increments; i++) {
            counter.increment();
        }
    }
}
public class Main {
    public static void main(String[] args) throws InterruptedException {
        Scanner sc = new Scanner(System.in);
        int numThreads = sc.nextInt();
        int incrementsPerThread = sc.nextInt();
        Counter counter = new Counter();
        Worker[] workers = new Worker[numThreads];
        for (int i = 0; i < numThreads; i++) {
            workers[i] = new Worker(counter, incrementsPerThread);
            workers[i].start();
        }
        for (int i = 0; i < numThreads; i++) {
            workers[i].join();
        }
        System.out.println("Final count: " + counter.getCount());
    }
}
```





## OUTPUT:
<img width="1265" height="336" alt="image" src="https://github.com/user-attachments/assets/0ba1492c-8993-4971-92ba-a1eb14b658bc" />



## RESULT:
The program successfully uses a synchronized block to ensure that multiple threads safely increment a shared counter without race conditions.
