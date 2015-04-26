package mainPackage;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.*;
public class Starter extends JFrame implements ActionListener {
	public static int a = 2;
	public Starter() {
		super("George v1.1.1");
		setResizable(false);
		setDefaultCloseOperation(EXIT_ON_CLOSE);
		setBounds(317, 100, 1200, 800);
		getContentPane().setLayout(null);
		JMenuBar menuBar = new JMenuBar();
		JMenu File = new JMenu("File");
		JMenu Edit = new JMenu("Edit");
		
		menuBar.add(File);
		menuBar.add(Edit);
		setJMenuBar(menuBar);
		
		DataStore data = new DataStore();
		
		
		JButton Cont = new JButton ("Continue");
		Cont.setBounds(500, 65, 20, 30);
		Cont.setActionCommand("cont");
		Cont.addActionListener(this);
		JLabel test = new JLabel("" + a);
		test.setBounds(50, 40, 20, 30);
		getContentPane().add(test);
		
	}

	public void actionPerformed(ActionEvent e) {
	}
}
