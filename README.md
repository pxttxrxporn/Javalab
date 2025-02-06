import java.awt.*;   /// เครื่องคิดเลข
import java.awt.event.*;
import javax.swing.*;

public class Lab8_3 extends JFrame implements ActionListener { 
    JLabel textLabel; 
    JTextField textField; 
    JButton saveBtn, clearBtn, showBtn; 
    JButton addBtn, subBtn, mulBtn, divBtn; 
    JButton btn1, btn2, btn3 ,btn4 ,btn5 ,btn6 ,btn7 ,btn8 ,btn9 ,btn0; //เพิ่มปุ่ม
    Container container; 
    NumberNew obj;

    public Lab8_3() { 
        super("Program Calculate Number"); 
        container = getContentPane(); 
        container.setLayout(new FlowLayout());

        // Label และ TextField สำหรับแสดงผล
        textLabel = new JLabel("Enter number :"); 
        textLabel.setFont(new Font("Courier New", Font.BOLD, 20)); 
        container.add(textLabel); 

        textField = new JTextField(10); 
        textField.setFont(new Font("Courier New", Font.BOLD, 24)); 
        container.add(textField); 

        // ปุ่ม Save, Clear, Show สำหรับการคำนวณ
        saveBtn = new JButton(" Save "); 
        saveBtn.setFont(new Font("Courier New", Font.BOLD, 20)); 
        saveBtn.addActionListener(this); 
        container.add(saveBtn); 

        clearBtn = new JButton(" Clear "); 
        clearBtn.setFont(new Font("Courier New", Font.BOLD, 20)); 
        clearBtn.addActionListener(this); 
        container.add(clearBtn); 

        showBtn = new JButton(" Show "); 
        showBtn.setFont(new Font("Courier New", Font.BOLD, 20)); 
        showBtn.addActionListener(this); 
        container.add(showBtn); 

        // ปุ่มคำนวณ +, -, *, /
        addBtn = new JButton(" + "); 
        addBtn.setFont(new Font("Courier New", Font.BOLD, 20)); 
        addBtn.addActionListener(this); 
        container.add(addBtn); 

        subBtn = new JButton(" - "); 
        subBtn.setFont(new Font("Courier New", Font.BOLD, 20)); 
        subBtn.addActionListener(this); 
        container.add(subBtn); 

        mulBtn = new JButton(" * "); 
        mulBtn.setFont(new Font("Courier New", Font.BOLD, 20)); 
        mulBtn.addActionListener(this); 
        container.add(mulBtn); 

        divBtn = new JButton(" / "); 
        divBtn.setFont(new Font("Courier New", Font.BOLD, 20)); 
        divBtn.addActionListener(this); 
        container.add(divBtn); 

        // เพิ่มปุ่ม 1, 2, 3
        btn1 = new JButton(" 1 "); 
        btn1.addActionListener(this); 
        container.add(btn1); 

        btn2 = new JButton(" 2 "); 
        btn2.addActionListener(this); 
        container.add(btn2); 

        btn3 = new JButton(" 3 "); 
        btn3.addActionListener(this); 
        container.add(btn3); 

        btn4 = new JButton(" 4 "); 
        btn4.addActionListener(this); 
        container.add(btn4); 

        btn5 = new JButton(" 5 "); 
        btn5.addActionListener(this); 
        container.add(btn5); 

        btn6 = new JButton(" 6 "); 
        btn6.addActionListener(this); 
        container.add(btn6); 

        btn7 = new JButton(" 7 "); 
        btn7.addActionListener(this); 
        container.add(btn7); 

        btn8 = new JButton(" 8 "); 
        btn8.addActionListener(this); 
        container.add(btn8); 

        btn9 = new JButton(" 9 "); 
        btn9.addActionListener(this); 
        container.add(btn9); 

        btn0 = new JButton(" 0 "); 
        btn0.addActionListener(this); 
        container.add(btn0); 


        // ขนาดของหน้าต่าง
        setSize(340, 300); 
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); 
        setVisible(true); 
    } 

    public static void main(String[] args) { 
        Lab8_3 test = new Lab8_3(); 
        // สร้างอ็อบเจกต์ของคลาส NumberNew 
        test.obj = new NumberNew(); 
        test.textField.setText(test.obj.toString()); 
    } 

    public void actionPerformed(ActionEvent event) { 
        String str = textField.getText(); // อ่านค่าจาก textField

        // หากกดปุ่ม 1, 2, 3 ให้เพิ่มตัวเลขลงใน textField
        if (event.getSource() == btn1) { 
            str += "1"; 
            textField.setText(str); 
        } 
        else if (event.getSource() == btn2) { 
            str += "2"; 
            textField.setText(str); 
        } 
        else if (event.getSource() == btn3) { 
            str += "3"; 
            textField.setText(str); 
        } 
        else if (event.getSource() == btn4) { 
            str += "4"; 
            textField.setText(str); 
        }
        else if (event.getSource() == btn5) { 
            str += "5"; 
            textField.setText(str); 
        }
        else if (event.getSource() == btn6) { 
            str += "6"; 
            textField.setText(str); 
        }
        else if (event.getSource() == btn7) { 
            str += "7"; 
            textField.setText(str); 
        }
        else if (event.getSource() == btn8) { 
            str += "8"; 
            textField.setText(str); 
        }
        else if (event.getSource() == btn9) { 
            str += "9"; 
            textField.setText(str); 
        }
        else if (event.getSource() == btn0) { 
            str += "0"; 
            textField.setText(str); 
        }
        // หากกดปุ่ม Save, Clear, Show ให้ทำตามฟังก์ชันที่ต้องการ
        else if (event.getSource() == saveBtn) { 
            int value = Integer.parseInt(textField.getText()); 
            obj.setValue(value); 
            textField.setText(""); 
        } 
        else if (event.getSource() == clearBtn) { 
            obj.setValue(0); 
            textField.setText(""); 
        } 
        else if (event.getSource() == showBtn) { 
            textField.setText(obj.toString()); 
        } 
        // หากกดปุ่มคำนวณ +, -, *, /
        else if (event.getSource() == addBtn) { 
            int value = Integer.parseInt(textField.getText()); 
            obj.add(value); 
            textField.setText(obj.toString()); 
        } 
        else if (event.getSource() == subBtn) { 
            int value = Integer.parseInt(textField.getText()); 
            obj.subtract(value); 
            textField.setText(obj.toString()); 
        } 
        else if (event.getSource() == mulBtn) { 
            int value = Integer.parseInt(textField.getText()); 
            obj.multiply(value); 
            textField.setText(obj.toString()); 
        } 
        else if (event.getSource() == divBtn) { 
            int value = Integer.parseInt(textField.getText()); 
            obj.divide(value); 
            textField.setText(obj.toString()); 
        } 
    } 
}

