# Hotel-Management-Systems
import java.awt.*;
import java.awt.event.*;
import java.sql.*;
public class HotelReservation 
{
	
	Button b1,b2;
	Frame frame=new Frame("Welcome");
	Label l1;
	HotelReservation()
	{
	//welcome page
	b1=new Button("Reservation");
	b2=new Button("Exit");
	l1=new Label("Welcome Customer");
	frame.setBackground(Color.MAGENTA);
	frame.setLayout(new FlowLayout());
	frame.add(l1);
	frame.add(b1);
	frame.add(b2);
	frame.setSize(350,200);
	frame.setVisible(true);
	frame.setTitle("Welcome");
	b1.addActionListener(new ActionListener()
	{
	//action for reservation log in page
	public void actionPerformed(ActionEvent e)
	{
	Label l2,l3,l4,l5,l6;
	Frame frame=new Frame("Customer");
	final TextField tf1,tf2,tf3,tf4;
	Button b3,b4;
	l2=new Label("Details of Customer::");
	l3=new Label("Name");
	l4=new Label("Phone No");
	l5=new Label("Email_id");
	l6=new Label("Address");
	tf1=new TextField(15);
	tf2=new TextField(10);
	tf3=new TextField(10);
	tf4=new TextField(15);
	b3=new Button("Submit");
	b4=new Button("Ok");
	frame.add(l2);
	frame.add(l3);
	frame.add(tf1);
	frame.add(l4);
	frame.add(tf2);
	frame.add(l5);
	frame.add(tf3);
	frame.add(l6);
	frame.add(tf4);
	frame.add(b3);
	frame.add(b4);
	frame.setLayout(new FlowLayout());
	frame.setSize(400,200);
	frame.setVisible(true);
	b3.addActionListener(new ActionListener()
	{
		public void actionPerformed(ActionEvent e)
		{
			String str1=tf1.getText();
			int str2=Integer.parseInt(tf2.getText());
			String str3=tf3.getText();
			String str4=tf4.getText();
			try
			{
				Class.forName("oracle.jdbc.driver.OracleDriver");
				Connection conn=DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521","system","demo");
				Statement stmt=conn.createStatement();
				System.out.println("--connected--");
				stmt.executeUpdate("insert into customer(name,phno,email_id,address) values('"+str1+"','"+str2+"','"+str3+"','"+str4+"')");
			stmt.close();
			conn.close();
			}

			catch(Exception e1)
			{
				e1.printStackTrace();
			}
			
		}
	});
	b4.addActionListener(new ActionListener()
	{
		//action for choosing options
		public void actionPerformed(ActionEvent e)
		{
			Label l7,l8,l9,l10;
			Frame frame=new Frame("Accomdation");
			final TextField tf5,tf6,tf7;
			Button b5;
			l7=new Label("Accomdation Details");
			l8=new Label("Type Of Room");
			l9=new Label("Availability Of Room");
			l10=new Label("Package Type");
			tf5=new TextField(20);
			tf6=new TextField(10);
			tf7=new TextField(30);
			b5=new Button("Ok");
			frame.add(l7);
			frame.add(l8);
			frame.add(tf5);
			frame.add(l9);
			frame.add(tf6);
			frame.add(l10);
			frame.add(tf7);
			frame.add(b5);
			frame.setLayout(new FlowLayout());
			frame.setSize(200,275);
			frame.setVisible(true);
	}
	});
	}
});
	
	
	
	frame.addWindowListener(new WindowAdapter()
	{
		public void windowClosing(WindowEvent e)
		{
		System.exit(0);
		}
	});
	frame.addWindowListener(new WindowAdapter()
	{
		public void windowClosing(WindowEvent e)
		{
		System.exit(0);
		}
	});
	frame.addWindowListener(new WindowAdapter()
	{
		public void windowClosing(WindowEvent e)
		{
		System.exit(0);
		}
	});
	

	
	}	
		public static void main(String args[])
		{
		new HotelReservation();
		}
	}

	
