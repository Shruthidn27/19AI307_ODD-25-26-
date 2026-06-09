# Ex.No:5(A) INPUTSTREAMREADER 

## QUESTION:
Write a program to write an array of strings into a file using PrintWriter.

## AIM:
To write the contents of an array of strings into a text file using the PrintWriter class in Java.

## ALGORITHM :
1.Start the program.

2.Create an array of strings.

3.Create a PrintWriter object using FileWriter to open/create the output file.

4.Traverse the array using a loop.

5.Write each string from the array into the file using println().

6.Close the PrintWriter object.

7.Display a success message.

8.Handle any exceptions that may occur during file operations.

9.Stop the program.
## PROGRAM:
 ```
/*
Program to implement a InputStreamReader using Java
Developed by: shruthi D N
RegisterNumber: 212223240155
*/
```

## SOURCE CODE:
```
import java.io.FileWriter;
import java.io.PrintWriter;

public class Main {
    public static void main(String[] args) {
        String[] arr = {"welcome"};

        try {
            PrintWriter pw = new PrintWriter(new FileWriter("output.txt"));

            for (String s : arr) {
                pw.println(s);
            }

            pw.close();
            System.out.println("Array of strings written to file successfully.");
        } catch (Exception e) {
            System.out.println("Error writing to file.");
        }
    }
}
```

## OUTPUT:
<img width="1200" height="266" alt="image" src="https://github.com/user-attachments/assets/50c45a93-aaf9-4925-9ce7-73c3132ee4b0" />

## RESULT:
Array of strings written to file successfully.
