Flow chart : https://drive.google.com/file/d/1Tg5wGPpiNZsS951_mJQgD3ou4jWJufb1/view?usp=drive_link

Challeges : A challenge I faced was storing into a derrived class properly. 

Video : 

Code : 

        public class Course {
            private String courseNumber;
            private String courseTitle;
            
            public void setCourseNumber(String number) {
                courseNumber = number;
            }
            
            public void setCourseTitle(String title) {
                courseTitle = title;
            }
            
            public String getCourseNumber() {
                return courseNumber;
            }
            
            public String getCourseTitle() {
                return courseTitle;
            }
            
            public void printInfo() {
                System.out.println("Course Information:");
                System.out.println("   Course Number: " + courseNumber);
                System.out.println("   Course Title: " + courseTitle);
            }
        }
        // ===== end =====
        
        
        // ===== Code from file OfferedCourse.java =====
        public class OfferedCourse extends Course {
        
            private String instructorName;
            private String location;
            private String classTime;
            
            public void setInstructorName(String name) {
                instructorName = name;
            }
        
            public void setLocation(String loc) {
                location = loc;
            }
        
            public void setClassTime(String time) {
                classTime = time;
            }
            
            public String getInstructorName() {
                return instructorName;
            }
        
            public String getLocation() {
                return location;
            }
        
            public String getClassTime() {
                return classTime;
            }
            
            @Override
            public void printInfo() {
                super.printInfo();
                
                System.out.println("   Instructor Name: " + instructorName);
                System.out.println("   Location: " + location);
                System.out.println("   Class Time: " + classTime);
            }
        }
        // ===== end =====
        
        
        
        import java.util.Scanner;
        
        public class CourseInformation {
            public static void main(String[] args) {
                Scanner scnr = new Scanner(System.in);
                
                Course course1 = new Course();
                
                OfferedCourse course2 = new OfferedCourse();
                
                String course1Num = scnr.nextLine();
                String course1Title = scnr.nextLine();
                String course2Num = scnr.nextLine();
                String course2Title = scnr.nextLine();
                String instructor = scnr.nextLine();
                String location = scnr.nextLine();
                String classTime = scnr.nextLine();
                
                course1.setCourseNumber(course1Num);
                course1.setCourseTitle(course1Title);
                
                course2.setCourseNumber(course2Num);
                course2.setCourseTitle(course2Title);
                course2.setInstructorName(instructor);
                course2.setLocation(location);
                course2.setClassTime(classTime);
                
                course1.printInfo();
                course2.printInfo();
        
                scnr.close();
            }
