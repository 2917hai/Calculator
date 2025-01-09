# Calculator
# I have made a Calculator with the help of java GUI

import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.util.Scanner;

public class Calculator extends Frame{
    JButton b1,b2,b3,b4,b5,b6,b7,b8,b9,ba,bb,bc,bd,be,bf,bg;
    JTextField j1;
    String operator = "";
    double firstNumber = 0;
    double result = 0;
    Calculator() {
        setLayout(null);
       
        JLabel jl = new JLabel("Simple Calculator Made by Umesh  ");
        jl.setFont(new Font("Times New Roman", Font.BOLD, 30));
        jl.setForeground(Color.BLUE);
        jl.setBounds(5, 5, 500, 90);
        add(jl);
        

        b1 = new JButton("1");
        // Add ActionListener to button 1
        b1.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                j1.setText(j1.getText() + "1");
            }
        });
        b1.setFont(new Font("Times New Roman", Font.BOLD, 40));
        b1.setBounds(20, 250, 100, 100);
        add(b1);


        b2 = new JButton("4");
        b2.setFont(new Font("Times New Roman", Font.BOLD, 40));
        b2.setBounds(20, 370, 100, 100);
        b2.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                j1.setText(j1.getText() + "4");
            }
        });
        add(b2);
        b3 = new JButton("7");
        b3.setFont(new Font("Times New Roman", Font.BOLD, 40));
        b3.setBounds(20, 490, 100, 100);
        b3.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                j1.setText(j1.getText() + "7");
            }
        });
        add(b3);

        bb = new JButton("Dlt.");
        bb.setFont(new Font("Times New Roman", Font.BOLD, 40));
        bb.setBounds(20, 610, 100, 100);
        bb.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                String currentText = j1.getText();
                if (currentText.length() > 0) {
                    j1.setText(currentText.substring(0, currentText.length() - 1));
                }
            }
        });
        add(bb);

        b4 = new JButton("2");
        b4.setFont(new Font("Times New Roman", Font.BOLD, 40));
        b4.setBounds(150, 250, 100, 100);
        b4.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                j1.setText(j1.getText() + "2");
            }
        });
        add(b4);

        b5 = new JButton("5");
        b5.setFont(new Font("Times New Roman", Font.BOLD, 40));
        b5.setBounds(150, 370, 100, 100);
        b5.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                j1.setText(j1.getText() + "5");
            }
        });
        add(b5);

        b6 = new JButton("8");
        b6.setFont(new Font("Times New Roman", Font.BOLD, 40));
        b6.setBounds(150, 490, 100, 100);
        b6.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                j1.setText(j1.getText() + "8");
            }
        });
        add(b6);

        ba = new JButton("0");
        ba.setFont(new Font("Times New Roman", Font.BOLD, 40));
        ba.setBounds(150, 610, 100, 100);
        ba.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                j1.setText(j1.getText() + "0");
            }
        });
        add(ba);

        b7 = new JButton("3");
        b7.setFont(new Font("Times New Roman", Font.BOLD, 40));
        b7.setBounds(280, 250, 100, 100);
        b7.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                j1.setText(j1.getText() + "3");
            }
        });
        add(b7);

        b8 = new JButton("6");
        b8.setFont(new Font("Times New Roman", Font.BOLD, 40));
        b8.setBounds(280, 370, 100, 100);
        b8.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                j1.setText(j1.getText() + "6");
            }
        });
        add(b8);

        b9 = new JButton("9");
        b9.setFont(new Font("Times New Roman", Font.BOLD, 40));
        b9.setBounds(280, 490, 100, 100);
        b9.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                j1.setText(j1.getText() + "9");
            }
        });
        add(b9);

        // In this line we declear = equal button operation
        bc = new JButton("=");
        bc.setFont(new Font("Times New Roman", Font.BOLD, 40));
        bc.setBounds(280, 610, 100, 100);
        bc.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if (!j1.getText().isEmpty()) {
                    double secondNumber = Double.parseDouble(j1.getText());
                    switch (operator) {
                        case "+":
                            result = firstNumber + secondNumber;
                            break;
                        case "-":
                            result = firstNumber - secondNumber;
                            break;
                        case "*":
                            result = firstNumber * secondNumber;
                            break;
                        case "/":
                            if (secondNumber != 0) {
                                result = firstNumber / secondNumber;
                            } else {
                                j1.setText("Error");
                            }
                            break;
                    }
                    j1.setText(Double.toString(result));
                }
            }
        });
        add(bc);

///////OPERATION  BUTTON + //////////////////////////////////////////////////////////////////////////////////////////
        bd = new JButton("+");
        bd.setFont(new Font("Times New Roman", Font.BOLD, 40));
        bd.setBounds(420, 250, 100, 100);
        bd.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if (!j1.getText().isEmpty()) {
                    firstNumber = Double.parseDouble(j1.getText());
                    operator = "+";
                    j1.setText("");
                }
            }
        });
        add(bd);

        // in this line we declear - sub button
        be = new JButton("-");
        be.setFont(new Font("Times New Roman", Font.BOLD, 60));
        be.setBounds(420, 370, 100, 100);
        be.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if (!j1.getText().isEmpty()) {
                    firstNumber = Double.parseDouble(j1.getText());
                    operator = "-";
                    j1.setText("");
                }
            }
        });
        add(be);

        //in this line we declear * multiply button
        bf = new JButton("*");
        bf.setFont(new Font("Times New Roman", Font.BOLD, 40));
        bf.setBounds(420, 490, 100, 100);
        bf.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if (!j1.getText().isEmpty()) {
                    firstNumber = Double.parseDouble(j1.getText());
                    operator = "*";
                    j1.setText("");
                }
            }
        });
        add(bf);

        //In this line we declear / (devide) button
        bg = new JButton("/");
        bg.setFont(new Font("Times New Roman", Font.BOLD, 40));
        bg.setBounds(420, 610, 100, 100);
        bg.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if (!j1.getText().isEmpty()) {
                    firstNumber = Double.parseDouble(j1.getText());
                    operator = "/";
                    j1.setText("");
                }
            }
        });
        add(bg);

//this line declear textfield size and color
        j1 = new JTextField();
        j1.setFont(new Font("Times New Roman", Font.BOLD, 60));
        j1.setBounds(5, 100, 575, 80);
        add(j1);

//this line declear frame size and color
        setSize(600, 1000);
        setBackground(Color.BLACK);
        setVisible(true);
    }
        public static void main(String[]args)
        {
            new Calculator();
        }
    }


    //this is git class
