package mainPackage;

import java.awt.Font;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.FocusEvent;
import java.awt.event.FocusListener;
import java.util.Random;

import javax.swing.*;

public class FirstResponseOverused extends JFrame implements ActionListener, FocusListener {
	Font fontA = new Font("Aerial", Font.BOLD, 23);
	Random d = new Random();
	int r = d.nextInt(8);
	JLabel firstResponse = new JLabel();
	public FirstResponseOverused() {
		super("George v1.1.1");
		setResizable(false);
		setDefaultCloseOperation(DISPOSE_ON_CLOSE);
		Starter starter = new Starter();
		setBounds(starter.getBounds());
		getContentPane().setLayout(null);
		firstResponse.setBounds(420, 30, 800, 30);
		firstResponse.setFont(fontA);
		
		switch (r) {
		case 0: firstResponse.setText("You really aren't very imaginative, are you?");
		break;
		case 1: firstResponse.setText("Can you really not think of anything else to say?");
		break;
		case 3: firstResponse.setText("Ask me that question one more time...");
		break;
		case 4: firstResponse.setText("Wow. I get the feeling that you don't normally do most of the talking in a conversation.");
		break;
		case 5: firstResponse.setText("I'm fricking fine! Now stop asking!");
		break;
		case 6: firstResponse.setText("How are YOU doing, hm? Yeah, that's what I thought! Don't like it so much when the tables are turned on you, huh?");
		break;
		case 7: firstResponse.setText("Stop talking. Just... Stop talking. Please.");
		break;
		}
		getContentPane().add(firstResponse);
		
}
	public void focusGained(FocusEvent e) {
	}
	public void focusLost(FocusEvent e) {
	}
	public void actionPerformed(ActionEvent e) {	
	}
}
