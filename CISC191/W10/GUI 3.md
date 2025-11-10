flowchart : https://drive.google.com/file/d/1q8SRTWZMge3XFRynVhOburXHjOBl6YyZ/view?usp=sharing

challenges : I had trouble this lab using the jspinner properly.

video : https://www.loom.com/share/4ed9135292c14c4193cc31a596144da4

code : 

    import javax.swing.*;
    import java.awt.*;
    import java.awt.event.*;

    public class unitConverter {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Miles to Kilometers Converter");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 150);
        frame.setLayout(new GridLayout(3, 2, 10, 10));
        
        JLabel milesLabel = new JLabel("Enter distance (miles):");
        
        SpinnerNumberModel model = new SpinnerNumberModel(0.0, 0.0, 10000.0, 0.1);
        JSpinner milesSpinner = new JSpinner(model);
        
        JLabel resultLabel = new JLabel("Distance in kilometers:");
        JLabel outputLabel = new JLabel(""); // where result is displayed
        
        JButton convertButton = new JButton("Convert");
        
        convertButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                double miles = (Double) milesSpinner.getValue();
                
                double kilometers = miles * 1.60934;
                
                outputLabel.setText(String.format("%.3f km", kilometers));
            }
        });
        
        frame.add(milesLabel);
        frame.add(milesSpinner);
        frame.add(resultLabel);
        frame.add(outputLabel);
        frame.add(new JLabel("")); // spacer
        frame.add(convertButton);
        
        frame.setVisible(true);
    }
}
