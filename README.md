# Create-CheckBox-in-java
import java.awt.Color;
import java.awt.event.*;
import javax.swing.*;

class fr9 extends JFrame implements ItemListener {
    JRadioButton r1, r2, r3;
    ButtonGroup brg;
    JLabel lb;

    fr9() {
        setLayout(null);

        brg = new ButtonGroup();

        r1 = new JRadioButton("RED");
        r2 = new JRadioButton("GREEN");
        r3 = new JRadioButton("BLUE");

        brg.add(r1);
        brg.add(r2);
        brg.add(r3);

        lb = new JLabel("This is Label");

        r1.setBounds(100, 100, 150, 30);
        r2.setBounds(300, 100, 150, 30);
        r3.setBounds(500, 100, 150, 30);
        lb.setBounds(100, 200, 200, 30);

        add(r1);
        add(r2);
        add(r3);
        add(lb);

        r1.addItemListener(this);
        r2.addItemListener(this);
        r3.addItemListener(this);

        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setSize(500, 500);
        setVisible(true);
    }

    @Override
    public void itemStateChanged(ItemEvent e) {
        if (e.getSource() == r1) {
            lb.setForeground(Color.RED);
        } else if (e.getSource() == r2) {
            lb.setForeground(Color.GREEN);
        } else {
            lb.setForeground(Color.BLUE);
        }
    }

    public static void main(String[] args) {
        fr9 obj1 = new fr9();
    }
}
