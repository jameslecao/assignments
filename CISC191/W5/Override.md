Flow Chart : https://drive.google.com/file/d/1bY4kCmCG4Zy0RBpodwgDS08QRECLbbc-/view?usp=drive_link

Challeges: A challenge I faced was setting up all fields.

Video : 

Code : 

        // ===== Code from file Book.java =====
        public class Book {
            
            private String title;
            private String author;
            private String publisher;
            private String publicationDate;
        
            
            public void setTitle(String bookTitle) {
                title = bookTitle;
            }
        
            public void setAuthor(String bookAuthor) {
                author = bookAuthor;
            }
        
            public void setPublisher(String bookPublisher) {
                publisher = bookPublisher;
            }
        
            public void setPublicationDate(String pubDate) {
                publicationDate = pubDate;
            }
        
            
            public String getTitle() {
                return title;
            }
        
            public String getAuthor() {
                return author;
            }
        
            public String getPublisher() {
                return publisher;
            }
        
            public String getPublicationDate() {
                return publicationDate;
            }
        
            
            public void printInfo() {
                System.out.println("Book Information: ");
                System.out.println("   Book Title: " + title);
                System.out.println("   Author: " + author);
                System.out.println("   Publisher: " + publisher);
                System.out.println("   Publication Date: " + publicationDate);
            }
        }
        // ===== end =====
        
        
        // ===== Code from file Encyclopedia.java =====
        public class Encyclopedia extends Book {
            
            private String edition;
            private int numPages;
        
            
            public void setEdition(String encyEdition) {
                edition = encyEdition;
            }
        
            public void setNumPages(int pages) {
                numPages = pages;
            }
        
            
            public String getEdition() {
                return edition;
            }
        
            public int getNumPages() {
                return numPages;
            }
        
            
            @Override
            public void printInfo() {
                super.printInfo();
                
                System.out.println("   Edition: " + edition);
                System.out.println("   Number of Pages: " + numPages);
            }
        }
        // ===== end =====
        
        
        // ===== Code from file BookInformation.java =====
        import java.util.Scanner;
        
        public class BookInformation {
            public static void main(String[] args) {
                Scanner scnr = new Scanner(System.in);
        
                
                Book book1 = new Book();
                Encyclopedia encyclopedia1 = new Encyclopedia();
                
                String bookTitle = scnr.nextLine();
                String bookAuthor = scnr.nextLine();
                String bookPublisher = scnr.nextLine();
                String bookPubDate = scnr.nextLine();
                
                String encyTitle = scnr.nextLine();
                String encyAuthor = scnr.nextLine();
                String encyPublisher = scnr.nextLine();
                String encyPubDate = scnr.nextLine();
                String encyEdition = scnr.nextLine();
                int encyPages = scnr.nextInt();
                
                book1.setTitle(bookTitle);
                book1.setAuthor(bookAuthor);
                book1.setPublisher(bookPublisher);
                book1.setPublicationDate(bookPubDate);
                
                encyclopedia1.setTitle(encyTitle);
                encyclopedia1.setAuthor(encyAuthor);
                encyclopedia1.setPublisher(encyPublisher);
                encyclopedia1.setPublicationDate(encyPubDate);
                encyclopedia1.setEdition(encyEdition);
                encyclopedia1.setNumPages(encyPages);
                
                book1.printInfo();
                encyclopedia1.printInfo();
        
                scnr.close();
            }
        }
