flowchart : https://drive.google.com/file/d/1dmNSFqpE0sU_sVol_-v0a5JUSYwDaDpH/view?usp=sharing

challeges : I had trouble displaying the text for the results. I would just mess up on the formating. 

video : 

code :

    import javax.swing.*;
    import java.awt.*;
    import java.awt.event.*;
    import java.text.NumberFormat;

    public class DistanceConverter {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Distance Converter");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(350, 220);
        frame.setLayout(new GridLayout(5, 2, 10, 10));
        
        JLabel milesLabel = new JLabel("Enter distance (miles):");
        NumberFormat numberFormat = NumberFormat.getNumberInstance();
        JFormattedTextField milesField = new JFormattedTextField(numberFormat);
        milesField.setValue(0.0);
        
        JLabel kmLabel = new JLabel("Kilometers:");
        JLabel mLabel = new JLabel("Meters:");
        JLabel ftLabel = new JLabel("Feet:");

        JLabel kmResult = new JLabel("");
        JLabel mResult = new JLabel("");
        JLabel ftResult = new JLabel("");
        
        JButton calcButton = new JButton("Convert");
        
        calcButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                try {
                    double miles = ((Number) milesField.getValue()).doubleValue();
                    
                    double kilometers = miles * 1.60934;
                    double meters = kilometers * 1000;
                    double feet = miles * 5280;

                    kmResult.setText(String.format("%.3f km", kilometers));
                    mResult.setText(String.format("%.2f m", meters));
                    ftResult.setText(String.format("%.2f ft", feet));
                } catch (Exception ex) {
                    kmResult.setText("Invalid input");
                    mResult.setText("");
                    ftResult.setText("");
                }
            }
        });
        
        frame.add(milesLabel);
        frame.add(milesField);
        frame.add(kmLabel);
        frame.add(kmResult);
        frame.add(mLabel);
        frame.add(mResult);
        frame.add(ftLabel);
        frame.add(ftResult);
        frame.add(new JLabel("")); 
        frame.add(calcButton);
        
        frame.setVisible(true);
    }
}
