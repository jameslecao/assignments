Flowchart : https://drive.google.com/file/d/1PiuksM_c-QjHK9-ES0mw7eOrA7gaCgW6/view?usp=drive_link

Challenges : The challenge for me was the loop boundaries. I made the mistake of doing it wrong causing an out of bound error. 

Video : https://www.loom.com/share/32d3b32b456d4605b48f454e3cebaea1

Code : 

      import java.util.Scanner;
    public class InsertionSort {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in); 
        
        int n = scan.nextInt();
        
        int[] arr = new int[n]; //create array size 'n'

        for (int i = 0; i < n; i++) {

            arr[i] = scan.nextInt();
        }

        printArray(arr); 

        int comparison = 0;

        int swap = 0;
        
        for (int i = 1; i < n; i++) { 

            int key = arr[i];
            int j = i - 1;
            
            while (j >= 0 && arr[j] > key) {
                comparison++; 
                arr[j + 1] = arr[j]; 
                swap++; 
                j--; 
            }

            if (j >= 0) {
                comparison++;
            }

            arr[j + 1] = key; 

            printArray(arr); 

        }

        System.out.println();

        System.out.println("comparison: " + comparison); 

        System.out.println("swap: " + swap); 
    }

    private static void printArray(int[] arr) { 

        for (int num : arr) {
            System.out.print(num + " ");  
        }
        System.out.println();  
    }
}
