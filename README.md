import javax.swing.*;
import java.awt.*;

class UIComponents {
    private JFrame frame;
    private JRadioButton amexRadioButton, ccdRadioButton;
    private JButton openButton;

    public UIComponents() {
        frame = new JFrame("Unified Data Extractor");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 200);
        frame.setLocationRelativeTo(null);
        frame.setLayout(new FlowLayout());
        frame.getContentPane().setBackground(new Color(128, 0, 128)); // Purple background

        amexRadioButton = new JRadioButton("Amex");
        ccdRadioButton = new JRadioButton("CCD");

        ButtonGroup radioButtonGroup = new ButtonGroup();
        radioButtonGroup.add(amexRadioButton);
        radioButtonGroup.add(ccdRadioButton);

        openButton = new JButton("Open");

        frame.add(amexRadioButton);
        frame.add(ccdRadioButton);
        frame.add(openButton);
    }

    public void addActionListener(ActionListener listener) {
        openButton.addActionListener(listener);
    }

    public void setVisible(boolean visible) {
        frame.setVisible(visible);
    }

    public boolean isAmexSelected() {
        return amexRadioButton.isSelected();
    }

    public boolean isCcdSelected() {
        return ccdRadioButton.isSelected();
    }
}

public class Main {
    public static void main(String[] args) {
        UIComponents uiComponents = new UIComponents();
        uiComponents.setVisible(true);

        uiComponents.addActionListener(e -> {
            if (uiComponents.isAmexSelected()) {
                System.out.println("Amex selected");
            } else if (uiComponents.isCcdSelected()) {
                System.out.println("CCD selected");
            }
        });
    }
}
