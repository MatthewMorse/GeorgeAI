package mainPackage;
import java.awt.Font;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.KeyListener;
import java.util.Random;

import javax.swing.*;
public class Starter extends JFrame implements ActionListener, KeyListener {
	public static int a;
	public static int b;
	public static int c;
	Font fontA = new Font("Aerial", Font.BOLD, 23);
	
	public Starter() {
		super("George v1.1.1");
		setResizable(false);
		setDefaultCloseOperation(DISPOSE_ON_CLOSE);
		setBounds(317, 100, 1200, 800);
		getContentPane().setLayout(null);
		JMenuBar menuBar = new JMenuBar();
		JMenu File = new JMenu("File");
		JMenu Edit = new JMenu("Edit");
		
		menuBar.add(File);
		menuBar.add(Edit);
		setJMenuBar(menuBar);
		
		DataStore data = new DataStore();
		//Runs all stored integer calculations
		
		JButton test = new JButton ("Continue");
		test.setBounds(500, 65, 20, 30);
		test.setActionCommand("test");
		test.addActionListener(this);
		JLabel MyName = new JLabel("Hello, my name is George.");
		MyName.setFont(fontA);
		MyName.setBounds(465, 40, 285, 30);
		JLabel labelTwo = new JLabel("I am a very poorly designed AI.");
		labelTwo.setFont(fontA);
		labelTwo.setBounds(447, 70, 332, 30);
		getContentPane().add(MyName);
		getContentPane().add(labelTwo);
		getContentPane().add(test);
	}
	public void actionPerformed(ActionEvent e) {
		if (e.getActionCommand() == "test") {
			FirstResponse first = new FirstResponse();
			first.setVisible(true);
			dispose();
		}
	}
}
