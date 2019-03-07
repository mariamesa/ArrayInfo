# ArrayInfo
This program reads in numbers from a file into an array, prints them, prints specified elements in the array, then finds the min and max.

import java.util.Scanner;
import java.io.*;

public class ArrayInfo {
    public static void main(String [] arg) throws IOException {
        double [] array = readIn();
        printArray(array);
        printElements(array);
        findMax(array);
        findMin(array);
    }
    public static double [] readIn() throws IOException {
        Scanner inFile = new Scanner(new File("numbers.text"));
        int header = inFile.nextInt();
        double [] array = new double [header];
        for(int i = 0; i < header; i++)
            array[i] = inFile.nextDouble();
        inFile.close();
        return array;
    }
    public static void printArray(double [] array) {
        System.out.print("The array: {");
        for (int i = 0; i < array.length - 1; i++)
                System.out.print(array[i] + ", "); 
        System.out.print(array[array.length - 1] + "} contains 8 elements \n");
    }
    public static void printElements(double [] array) {
        int pos = 0;
        System.out.println("The first element of the array is " + array[0]);
        System.out.print("The last element of the array is " + array[array.length - 1]);
        for(int i = 0; i < array.length; i++)
            if (array[i] == array[array.length - 1])
                pos = i;
        System.out.print(" and is at position " + pos + "\nThe middle element of the array is " + array[(array.length - 1)/2]);
        for(int i = 0; i < array.length; i++)
            if(array[i] == array[(array.length - 1)/2])
                pos = i;
        System.out.print(" and is at position " + pos + "\n");
    }
    public static void findMax(double [] array) {
        double max = array[0];
        int pos = 0;
        System.out.print("The largest element of the array is ");
        for(int i = 1; i < array.length; i++)
            if(array[i] > max)
                max = array[i];
        System.out.print(max + " and is at position ");
        for(int i = 0; i < array.length; i++)
            if(array[i] == max)
                pos = i;
         System.out.print(pos + "\n");
    }
    public static void findMin(double [] array) {
        double min = array[0];
        int pos = 0;
        System.out.print("The smallest element of the array is ");
        for(int i = 1; i < array.length; i++)
            if(array[i] < min)
                min = array[i];
        System.out.print(min + " and is at position ");
        for(int i = 0; i < array.length; i++)
            if(array[i] == min)
                pos = i;
        System.out.print(pos);
    }
}
