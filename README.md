# weak2-day1
import javax.naming.ldap.SortControl;
import java.util.Arrays;
import java.util.Collection;
import java.util.InputMismatchException;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        System.out.print("Enter the number of elements you want to store: ");
        try {
            Scanner sc = new Scanner(System.in);
            int n = sc.nextInt();
            int[] array = new int[n];


         System.out.println("Enter the elements of the array: ");
         for (int i = 0; i < n; i++) {
             array[i] = sc.nextInt();
         }

        mainLoop:
        while (true) {
            Scanner inn = new Scanner(System.in);
            System.out.println("\n***Menu***");
            System.out.println("1. Accept element of array");
            System.out.println("2. Display element of an array");
            System.out.println("3. Search elements");
            System.out.println("4. Sort the array in descending way");
            System.out.println("5. To stop the program");
            System.out.println("Enter action number (1-5): ");
            int command;
            if (inn.hasNextInt()) {
                command = inn.nextInt();
                inn.nextLine();
            } else {
                System.out.println("\n YOU MUST ENTER A NUMBER.");
                inn.nextLine();
                continue;
            }
            switch (command) {
                case 1:
                    System.out.println(": ");
                    for (int i = 0; i < array.length; i++) {
                        System.out.println(array[i]);
                    }

                    break;
                case 2:
                    System.out.println("Array elements are: ");
                    for (int i = 0; i < n; i++) {
                        System.out.println(array[i]);
                    }
                    break;
                case 3:
                    boolean found = false;
                    System.out.println("Enter the value you want to search for");
                    int v = sc.nextInt();
                    for (int i = 0; i < array.length; i++) {
                        if (v == array[i]) {
                            found = true;
                            System.out.println("The number you are search for Is" + v);
                        }
                        if (!found) {
                            System.out.println("not found");
                        }
                    }
                case 4:
                    int temp;
                    for (int i = 0; i < array.length; i++) {
                        for (int j = i + 1; j < array.length; j++) {
                            if (array[i] > array[j]) {
                                temp = array[i];

                            temp = array[i];
                            array[i] = array[j];
                            array[j] = temp;}
                        }
                    }

                    System.out.println("Array elements in descending order:");
                    //accessing element of the array
                    for (int i = 0; i <= array.length - 1; i++) {
                        System.out.println(array[i]);
                    }

                case 5:
                    System.out.println("Program terminated");
                    break mainLoop;
                default:
                    System.out.println("Wrong choice!!");

            } }}catch (InputMismatchException e1){
                System.out.println("You should enter Number");
            }
     catch (Exception e3){
         System.out.println("Exception => " + e3.getMessage());
     }
     finally {
                System.out.println("Finally block is always executed");

            }
        }
    }
