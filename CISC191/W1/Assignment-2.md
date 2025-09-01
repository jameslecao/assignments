#1 - flowchart: https://drive.google.com/file/d/1H_or-NWbnDxFLWAiE2mFN4Cn5eg5FQWj/view?usp=sharing

#2 - I would perform a frequency analysis of a website by taking the text from the website and use the methos getWord frequency. As long as I set the text into parameters the getWordFrequency works, I should be able to get the word frequenct no problem.

#3 -  Challenges I struggled with was understanding how to do the case sensitive in my code as well as . 

#4 - https://www.loom.com/share/aebe4bc9c9204968ba4040bfdf984600

#5 - Code

    import java.util.Scanner;

    public class Main {

    //method to count frequency
    public static int getWordFrequency(String[] wordsList, int listSize, String currWord) {
        int count = 0;

        for (int j = 0; j < listSize; j++) {
            if (wordsList[j].equalsIgnoreCase(currWord)) {
                count++;
            }
        }
        return count;
    }
    //main method
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String line = sc.nextLine();
        String[] wordsList = line.split(" ");
        int listSize = wordsList.length;


        for (int i = 0; i < listSize; i++) {
            String currWord = wordsList[i];
            int count = getWordFrequency(wordsList, listSize, currWord);
            System.out.println(currWord + " " + count);
        }
    }
