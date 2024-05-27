import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class DataExtractorApp extends JFrame implements ActionListener {
    private JRadioButton amexRadioButton, ccdRadioButton;
    private JButton openButton;

    public DataExtractorApp() {
        setTitle("Unified Data Extractor");
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setSize(300, 200);
        setLocationRelativeTo(null);
        setLayout(new FlowLayout());
        getContentPane().setBackground(new Color(128, 0, 128)); // Purple background

        amexRadioButton = new JRadioButton("Amex");
        ccdRadioButton = new JRadioButton("CCD");

        ButtonGroup radioButtonGroup = new ButtonGroup();
        radioButtonGroup.add(amexRadioButton);
        radioButtonGroup.add(ccdRadioButton);

        openButton = new JButton("Open");
        openButton.addActionListener(this);

        add(amexRadioButton);
        add(ccdRadioButton);
        add(openButton);

        setVisible(true);
    }

    public void actionPerformed(ActionEvent e) {
        if (amexRadioButton.isSelected()) {
            System.out.println("Amex selected");
        } else if (ccdRadioButton.isSelected()) {
            System.out.println("CCD selected");
        }
    }

    public static void main(String[] args) {
        new DataExtractorApp();
    }
}
