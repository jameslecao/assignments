Flowchart : https://drive.google.com/file/d/16a4XiH0tO3qUQRZt-yws6S7pXXRuiK2q/view?usp=sharing

Challenges : A challenge I had while performing this lab was getting the proper number for the salary as it wouldn't round correctly. 

Video : 

Code : 

    import javax.swing.*;
    import java.awt.*;
    import java.awt.event.ActionEvent;
    import java.awt.event.ActionListener;
    
    public class SalaryCalculator {
      public static void main(String[] args) {
        JFrame frame = new JFrame("Yearly Salary Calculator");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(350, 200);
        frame.setLayout(new GridLayout(4, 2, 10, 10)); 
        
        JLabel wageLabel = new JLabel("Hourly wage ($):");
        JLabel hoursLabel = new JLabel("Hours per week:");
        JLabel resultLabel = new JLabel("Yearly salary: ");
        JLabel outputLabel = new JLabel(""); 
        
        JTextField wageField = new JTextField();
        JTextField hoursField = new JTextField();
        
        JButton calcButton = new JButton("Calculate");
        
        calcButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                try {
                    double wage = Double.parseDouble(wageField.getText());
                    double hoursPerWeek = Double.parseDouble(hoursField.getText());
                    
                    double salary = wage * hoursPerWeek * 52;
                    
                    outputLabel.setText(String.format("$%.2f", salary));
                } catch (NumberFormatException ex) {
                    outputLabel.setText("Please enter valid numbers!");
                }
            }
        });
        
        frame.add(wageLabel);
        frame.add(wageField);
        frame.add(hoursLabel);
        frame.add(hoursField);
        frame.add(resultLabel);
        frame.add(outputLabel);
        frame.add(new JLabel(""));  
        frame.add(calcButton);
        
        frame.setVisible(true);
    }
}
