#1 - Flowchart: https://drive.google.com/file/d/10gqiveTSmhhEnPq8jTXdU5iMboRlXVjQ/view?usp=sharing

#2 - I decided on using bubble sorting as it one of the most known and simplest sorting algorithms to code. I have also used bubble sorting the most comparitiveley to other algorithms so it seemed best to just use this one. 

#3 - Challenges I had in this lab was determining what I needed to do and remembering how to do the actual code I needed. 

#4 - 

#5 - code

    import java.util.Scanner;

    public class Main {

    /*method to sort array into desc order*/
    public static void sortArray(int[] myArr, int arrSize) {
        for (int i = 0; i < arrSize - 1; i++) {
            for (int j = 0; j < arrSize - 1 - i; j++) {
                if (myArr[j] < myArr[j + 1]) {
                    int sub = myArr[j];
                    myArr[j] = myArr[j + 1];
                    myArr[j + 1] = sub;
                }
            }
        }
    }

    /*main method*/
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String[] input = sc.nextLine().split(" ");

        int arrSize = Integer.parseInt(input[0]);

        int[] myArr = new int[arrSize];

        for (int i = 0; i < arrSize; i++) {
            myArr[i] = Integer.parseInt(input[i + 1]);
        }

        sortArray(myArr, arrSize);

        for (int i = 0; i < arrSize; i++) {
            System.out.print(myArr[i]);
            if (i < arrSize - 1) {
                System.out.print(","); 
            }
        }
    }
}
