Q2: Inventory Control System V2

        import java.util.*;
        
        public class ICSV2 {
            public static void main(String[] args) {
                Scanner sc = new Scanner(System.in);
        
        try {
            //painkiller input
            System.out.print("Enter Painkiller Name: ");
            String name = sc.nextLine();
        
            System.out.print("Enter Drug Company: ");
            String company = sc.nextLine();
        
            System.out.print("Enter Expiry Date (e.g. 2025-12-30): ");
            String expiry = sc.nextLine(); // now just a String
        
            System.out.print("Enter Age Group: ");
            String age = sc.nextLine();
        
        Painkiller painkiller = new Painkiller(name, company, expiry, age);
        painkiller.display();
        
        //equipment input;
        
            System.out.print("Enter Equipment Name: ");
            String eqName = sc.nextLine();
            
            System.out.print("Enter Company: ");
            String eqCompany = sc.nextLine();
        
            System.out.print("Enter Weight (lbs): ");
            double weight = Double.parseDouble(sc.nextLine());
        
            Equipment equip = new Equipment(equipName, equipCompany, weight);
            equip.display();
            } catch (NumberFormatException e) { //built-in exception #1
                System.out.println("Error: Weight number is invalid. Please input another
                number.");
            } catch (InputMismatchException e) { //built-in exception #2
                System.out.println("Error: Input type does not match.");
            } catch (Exception e) { //general fallback
                System.out.println("Unexpected error: " + e.getMessage());
                }
            }
        }
