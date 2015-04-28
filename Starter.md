package mainPackage;

import java.awt.Font;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.FocusEvent;
import java.awt.event.FocusListener;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;
import java.util.Random;

import javax.swing.*;

public class Starter extends JFrame implements ActionListener, FocusListener {
	public static int a;
	public static int b;
	public static int c;
	public static int firstResponseOveruse = 0;
	Font fontA = new Font("Aerial", Font.BOLD, 23);
	JTextField sayIt = new JTextField("Type in what you want to say to George.");
	String HowAreYouDoing = "How are you doing?";
	String howAreYouDoing = "how are you doing?";
	String HowAreYouDoingStatement = "How are you doing?";
	String howAreYouDoingStatement = "how are you doing?";
	String HowAreYou = "How are you?";
	String howAreYou = "how are you?";
	String HowAreYouStatement = "How are you";
	String howAreYouStatement = "how are you";

	String howrudoing = "how r u doing";

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
		// Runs all stored integer calculations

		sayIt.setFont(new Font("Aerial", Font.ITALIC, 17));
		sayIt.setBounds(450, 115, 325, 70);
		sayIt.addFocusListener(this);

		JButton Submit = new JButton("Say It To George");
		Submit.setBounds(536, 200, 135, 30);
		Submit.setActionCommand("Submit");
		Submit.addActionListener(this);
		JLabel MyName = new JLabel("Hello, my name is George.");
		MyName.setFont(fontA);
		MyName.setBounds(465, 40, 285, 30);
		JLabel labelTwo = new JLabel("I am a very poorly designed AI.");
		labelTwo.setFont(fontA);
		labelTwo.setBounds(447, 70, 332, 30);
		getContentPane().add(MyName);
		getContentPane().add(labelTwo);
		getContentPane().add(Submit);
		getContentPane().add(sayIt);
	}

	public void actionPerformed(ActionEvent e) {
		String Said = sayIt.getText();
		if (e.getActionCommand() == "Submit" && Said.equals(HowAreYouDoing)
				|| e.getActionCommand() == "Submit"
				&& Said.equals(howAreYouDoing)
				|| e.getActionCommand() == "Submit"
				&& Said.equals(HowAreYouDoingStatement)
				|| e.getActionCommand() == "Submit"
				&& Said.equals(howAreYouDoingStatement)
				|| e.getActionCommand() == "Submit" && Said.equals(HowAreYou)
				|| e.getActionCommand() == "Submit" && Said.equals(howAreYou)
				|| e.getActionCommand() == "Submit"
				&& Said.equals(HowAreYouStatement)
				|| e.getActionCommand() == "Submit"
				&& Said.equals(howAreYouStatement)) {
			if (firstResponseOveruse >= 3) {
				FirstResponseOverused first = new FirstResponseOverused();
				first.setVisible(true);
				dispose();
			} else {
				if (e.getActionCommand() == "Submit"
						&& Said.equals(HowAreYouDoing)
						|| e.getActionCommand() == "Submit"
						&& Said.equals(howAreYouDoing)
						|| e.getActionCommand() == "Submit"
						&& Said.equals(HowAreYouDoingStatement)
						|| e.getActionCommand() == "Submit"
						&& Said.equals(howAreYouDoingStatement)
						|| e.getActionCommand() == "Submit"
						&& Said.equals(HowAreYou)
						|| e.getActionCommand() == "Submit"
						&& Said.equals(howAreYou)
						|| e.getActionCommand() == "Submit"
						&& Said.equals(HowAreYouStatement)
						|| e.getActionCommand() == "Submit"
						&& Said.equals(howAreYouStatement)) {
					FirstResponse first = new FirstResponse();
					first.setVisible(true);
					dispose();
				} else {
					dispose();
					// Edit later
				}
			}
		}
	}

	public void focusGained(FocusEvent e) {
		if (e.getComponent() == sayIt
				&& sayIt.getText().equals(
						"Type in what you want to say to George.")) {
			sayIt.setText("");
		}
	}

	public void focusLost(FocusEvent e) {
		if (e.getComponent() == sayIt && sayIt.getText().equals("")) {
			sayIt.setText("Type in what you want to say to George.");
		}
	}
}
