1. Flowchart : https://drive.google.com/file/d/1XhqVGlCTIkVvskcurmpMiHuF_TafRPAA/view?usp=sharing

2. Challenges : A challenge I had with this assignment was getting the input from a file and having it read out correctly. I had to review over again.

3. Video : https://www.loom.com/share/eed765827b97432ca30188a9b3e7ca07?sid=042c2448-7c23-48e0-82e8-a76b014830eb

4. Code : 
        import java.io.File;
        import java.io.FileNotFoundException;
        import java.util.Scanner;
        
        public class PhotoInfoConverter {
            public static void main(String[] args) {
               
                String inputFileName = "ParkPhotos.txt";
        
                try {
                    
                    File inputFile = new File(inputFileName);
        
                    
                    Scanner scanner = new Scanner(inputFile);
        
                    
                    while (scanner.hasNextLine()) {
                        
                        String photoFileName = scanner.nextLine().trim();
        
                        
                        if (!photoFileName.isEmpty()) {
                            
                            String infoFileName = photoFileName.replace("_photo.jpg", "_info.txt");
                            
                            System.out.println(infoFileName);
                        }
                    }
                    
                    scanner.close();
                } catch (FileNotFoundException e) {
                    
                    System.out.println("Error: File not found -> " + inputFileName);
                }
            }
        }
