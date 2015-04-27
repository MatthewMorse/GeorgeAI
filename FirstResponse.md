package mainPackage;

import java.awt.Font;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.util.Random;

import javax.swing.*;

public class FirstResponse extends JFrame implements ActionListener {
	Font fontA = new Font("Aerial", Font.BOLD, 23);
	JLabel firstResponse = new JLabel();
	public FirstResponse() {
		super("George v1.1.1");
		setResizable(false);
		setDefaultCloseOperation(DISPOSE_ON_CLOSE);
		Starter starter = new Starter();
		setBounds(starter.getBounds());
		getContentPane().setLayout(null);
		Random d = new Random();
		int r = d.nextInt(7);
		if (r == 1) {
			firstResponse.setFont(fontA);
			firstResponse.setText("Hullo.");
			firstResponse.setBounds(465, 30, 500, 30);
		}
		
	}
	public void actionPerformed(ActionEvent e) {
		
	}
}
