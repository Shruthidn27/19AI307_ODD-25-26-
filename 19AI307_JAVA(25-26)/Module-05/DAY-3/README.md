# Ex.No:5(C)  FILE HANDLING USING JAVA
## QUESTION:
Write a program to count the number of words in a file.

## AIM:
To write a Java program that counts the number of words present in a file.

## ALGORITHM :
1.Start the program.
2.Read a line of text from the user.
3.Create a file named sample.txt.
4.Write the entered text into the file and close it.
5.Open the file using BufferedReader.
6.Read the contents of the file.
7.Check whether the line is not empty.
8.Split the line into words using whitespace (\\s+) as the delimiter.
9.Count the number of words obtained after splitting.
10.Display the word count.
11.Handle any input/output exceptions.
12.Stop the program.




## PROGRAM:
 ```
/*
Program to implement a File Handling using Java
Developed by: SHRUTHI D N
RegisterNumber: 212223240155
*/
```

## SOURCE CODE:
```
import java.io.*;

public class Main {
    public static void main(String[] args) {
        try {
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
            String text = br.readLine();
            FileWriter fw = new FileWriter("sample.txt");
            fw.write(text);
            fw.close();
            BufferedReader fileReader = new BufferedReader(new FileReader("sample.txt"));
            String line = fileReader.readLine();
            fileReader.close();

            int wordCount = 0;
            if (line != null && !line.trim().isEmpty()) {
                wordCount = line.trim().split("\\s+").length;
            }

            System.out.println("Number of words in the file: " + wordCount);

        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```







## OUTPUT:
<img width="1205" height="263" alt="image" src="https://github.com/user-attachments/assets/f605ba8d-4a14-40fe-890a-b480f6df3132" />



## RESULT:
The program successfully writes the input text to a file (sample.txt), reads the file content, counts the number of words using whitespace as the separator, and displays the total word count.
