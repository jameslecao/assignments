1. Flowchart : https://drive.google.com/file/d/1qhOps9Be0ohDpdVghuyrolCdP55DrYjZ/view?usp=drive_link

2. Challenges : A challenge I had while doing this code was understanding deque.

3. Video : https://www.loom.com/share/61edb1b9457d40c18710250ebfc49275

4. Code :


        import java.util.Deque;
        import java.util.LinkedList;
        import java.util.Scanner;
        
        public class PalindromeChecker {
            public static void main(String[] args) {
        
                Scanner sc = new Scanner(System.in);
        
                System.out.print("Enter text: ");
        
                String input = sc.nextLine();
        
                input = input.toLowerCase().replaceAll("[^a-z]", "");
        
                sc.close();
        
                Deque<Character> deque = new LinkedList<>();
        
                for (char c : input.toCharArray()) {
                    deque.addLast(c);
                }
        
                boolean isPalindrome = true;
        
                while (deque.size() > 1) {
                    char first = deque.removeFirst();   
                    char last = deque.removeLast();     
        
                    if (first != last) {
                        isPalindrome = false;        
                        break;                          
                    }
                }
        
                if (isPalindrome) {
                    System.out.println("Yes, " + input + " is a palindrome.");
                } else {
                    System.out.println("No, \"" + input + "\" is not a palindrome.");
                }
            }
        }  
