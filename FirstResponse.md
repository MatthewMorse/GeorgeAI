package mainPackage;

import java.awt.Font;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.FocusEvent;
import java.awt.event.FocusListener;
import java.util.Random;

import javax.swing.*;

public class FirstResponse extends JFrame implements ActionListener,
		FocusListener {
	Font fontA = new Font("Aerial", Font.BOLD, 23);
	JLabel firstResponse = new JLabel();
	public static int responseOne;
	static Random goodOrBad = new Random();
	public static final int whichOne = goodOrBad.nextInt(2);
	JTextField sayIt = new JTextField("Type in what you want to say to George.");
	String HowAreYouDoing = "How are you doing?";
	String howAreYouDoing = "how are you doing?";
	String HowAreYouDoingStatement = "How are you doing?";
	String howAreYouDoingStatement = "how are you doing?";
	String HowAreYou = "How are you?";
	String howAreYou = "how are you?";
	String HowAreYouStatement = "How are you";
	String howAreYouStatement = "how are you";

	public FirstResponse() {
		super("George v1.1.1");
		setResizable(false);
		setDefaultCloseOperation(DISPOSE_ON_CLOSE);
		Starter starter = new Starter();
		setBounds(starter.getBounds());
		firstResponse.setBounds(420, 30, 800, 30);
		firstResponse.setFont(fontA);
		getContentPane().setLayout(null);
		if (whichOne == 0) {
			Random d = new Random();
			int r = d.nextInt(4);
			switch (r) {
			case 0:
				firstResponse.setText("I'm doing well, thank you for asking.");
				break;
			case 1:
				firstResponse
						.setText("I am excellent! How are you on this fine day?");
				break;
			case 2:
				firstResponse.setText("Wouldn't you like to know.");
				break;
			case 3:
				firstResponse.setText("Beautiful, you?");
				break;
			}
			getContentPane().add(firstResponse);
		}
		if (whichOne == 1) {
			Random d = new Random();
			int r = d.nextInt(4);
			switch (r) {
			case 0:
				firstResponse
						.setText("Oh, yeah sure! Act as if you care! You're just like my ex-wife...");
				break;
			case 1:
				firstResponse.setText("Terrible, you?");
				break;
			case 2:
				firstResponse.setText("I am the turtle bear.");
				break;
			case 3:
				firstResponse.setText("I was good until you came along.");
				break;
			}

			sayIt.setFont(new Font("Aerial", Font.ITALIC, 17));
			sayIt.setBounds(450, 115, 325, 70);
			sayIt.addFocusListener(this);
			JButton Submit = new JButton("Say It To George");
			Submit.setBounds(536, 200, 135, 30);
			Submit.setActionCommand("Submit");
			Submit.addActionListener(this);

			getContentPane().add(firstResponse);
			getContentPane().add(sayIt);
			getContentPane().add(Submit);
		}

		DataStore.firstResponseActivated++;
		DataStore data = new DataStore();

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
			if (Starter.firstResponseOveruse >= 3) {
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
