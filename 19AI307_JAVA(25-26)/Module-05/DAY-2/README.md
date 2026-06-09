# Ex.No:5(B) SERIALIZATION AND DESERIALIZATION 

## QUESTION:
Write a Java program to serialize a collection of objects (like ArrayList<Student>) into a file.

## AIM:
To write a Java program that serializes a collection of objects (ArrayList<Student>) into a file and then deserializes the collection back from the file.

## ALGORITHM :
1.Start the program.

2.Create a Student class that implements the Serializable interface.

3.Read the number of students from the user.

4.Create an ArrayList<Student>.

5.Read the student details (id, name, marks) and add them to the list.

6.Create an ObjectOutputStream connected to a file.

7.Write the ArrayList<Student> object into the file using writeObject().

8.Close the output stream.

9.Create an ObjectInputStream connected to the same file.

10.Read the serialized object using readObject() and typecast it to ArrayList<Student>.

11.Close the input stream.

12.Display the deserialized student records.

13.Handle exceptions if any occur.

14.Stop the program.
## PROGRAM:
 ```
/*
Program to implement a Serialization and Deserialization using Java
Developed by: shruthi D N
RegisterNumber: 212223240155 
*/
```

## SOURCE CODE:
```
import java.io.*;
import java.util.*;

class Student implements Serializable {
    private static final long serialVersionUID = 1L;

    int id;
    String name;
    double marks;

    Student(int id, String name, double marks) {
        this.id = id;
        this.name = name;
        this.marks = marks;
    }

    public String toString() {
        return "Student{id=" + id + ", name='" + name + "', marks=" + marks + "}";
    }
}

public class Main {
    @SuppressWarnings("unchecked")
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String fileName = "students.dat";

        try {
            int n = Integer.parseInt(sc.nextLine().trim());

            ArrayList<Student> students = new ArrayList<Student>();

            for (int i = 0; i < n; i++) {
                int id = Integer.parseInt(sc.nextLine().trim());
                String name = sc.nextLine();
                double marks = Double.parseDouble(sc.nextLine().trim());

                students.add(new Student(id, name, marks));
            }

            ObjectOutputStream oos =
                    new ObjectOutputStream(new FileOutputStream(fileName));
            oos.writeObject(students);
            oos.close();

            System.out.println("Students serialized successfully into: " + fileName);

            ObjectInputStream ois =
                    new ObjectInputStream(new FileInputStream(fileName));

            ArrayList<Student> deserializedStudents =
                    (ArrayList<Student>) ois.readObject();
            ois.close();

            System.out.println("Students deserialized successfully from: " + fileName);
            System.out.println();
            System.out.println("Deserialized Students:");

            for (Student s : deserializedStudents) {
                System.out.println(s);
            }

        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```


## OUTPUT:
<img width="1179" height="795" alt="image" src="https://github.com/user-attachments/assets/e72130fb-423a-48e4-9cdb-ec9185a685d6" />



## RESULT:
The ArrayList<Student> object was successfully serialized into the file students.dat using ObjectOutputStream and later deserialized using ObjectInputStream, preserving all student data correctly.
