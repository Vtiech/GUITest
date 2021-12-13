package EduHatch;

import java.awt.BorderLayout;
import java.awt.Color;
import java.awt.Container;
import java.awt.Dimension;
import java.awt.FlowLayout;
import java.awt.GridLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.MouseEvent;
import java.awt.event.MouseListener;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JMenu;
import javax.swing.JMenuBar;
import javax.swing.JMenuItem;
import javax.swing.JPanel;
import javax.swing.JScrollPane;
import javax.swing.JTable;
import javax.swing.JTextField;
import javax.swing.SwingConstants;
import javax.swing.border.LineBorder;
import javax.swing.table.DefaultTableModel;

public class CL implements ActionListener, MouseListener {

	JFrame f = new JFrame("EduHatch");

	private JPanel p = new JPanel();
	private JTextField tex1 = new JTextField();
	private JTextField tex2 = new JTextField();
	private JTextField tex3 = new JTextField();
	private JTextField tex4 = new JTextField();
	private JButton baton = new JButton("Submit");
	private JLabel label = new JLabel("Name ");
	private JLabel labels = new JLabel("Age ");
	private JLabel lebal = new JLabel("Gender ");
	private JLabel lebals = new JLabel("Address ");
	private JLabel labelss = new JLabel();
	private JLabel textt = new JLabel();
	private JLabel gender = new JLabel();
	private JLabel address = new JLabel();
	
	private JPanel mainPanel, topPanel, centerPanel, bottomPanel;
	private JTable dataTable;
	private JScrollPane scrollPane;
	private DefaultTableModel dtm;
	private JLabel nameLabel, bookLabel, priceLabel, borrowdate;
	private JTextField nameField, bookField, priceField, borrowField;
	private JButton addBtn, deleteBtn;
	private JMenuBar menu = new JMenuBar();
	
	Function_File file = new Function_File(this);
	
	JButton button1 = new JButton("Button1");
	JButton button2 = new JButton("Button2");
	JButton button3 = new JButton("Button3");
	JButton button4 = new JButton("Button4");
	JButton button5 = new JButton("Book");
	JButton button6 = new JButton("Lend");
	JButton button7 = new JButton("Search");
	JButton button8 = new JButton("Note");
	JButton button9 = new JButton("Button9");
	JButton button10 = new JButton("Button10");
	JButton button11 = new JButton("Button11");
	
	public CL() {
		// TODO Auto-generated constructor stub
		
		f.add(new JLabel("Welcome, " + "Alex"), BorderLayout.NORTH);
		
		mainPanel = new JPanel(new BorderLayout());
		topPanel = new JPanel();
		centerPanel = new JPanel(new GridLayout(4, 2));
		bottomPanel = new JPanel();
		
		//Top Panel
		Object[][] rows = {
				{"2440101143", "Cheque book", "Vasdev Mohi", 15000},
				{"2445237812", "The Overstory", "Richard Powers", 50000},
				{"2481273123", "The Braille edition of the book Exam Warriors", "PM Narendra Modi", 45000},
				{"1230987145", "Mind-Master", "Viswanathan Anand and Susan Ninan", 30000},
				{"2440101143", "Politics of Opportunism", "R P N Singh", 20000},
				{"2445237812", "Malayalam poetry", "Akkitham Achuthan Namboodri", 25000},
				{"2481273123", "The Testaments", "Margaret Atwood", 35000},
				{"1230987145", "Celestial Bodies", "Jokha Alharthi", 40000},
				{"2440101143", "Cheque book", "Vasdev Mohi", 15000},
				{"2445237812", "Hemant Karkare: A Daughter’s Memoir", "Hemant Karkare's daughter Jui Karkare", 50000},
				{"2481273123", "\"Courts of India\"", "Chief Justice of India (CJI) Ranjan Gogoi", 45000},
				{"1230987145", "Bridgital Nation", "Shri N Chandrasekaran", 30000},
				{"2440101143", "Girl Power: Indian Women Who Broke The Rules", "Neha J Hiranandani", 20000},
				{"2445237812", "‘150 Years of Celebrating the Mahatma–the South African Legacy’", "Fakir Hassen", 25000},
				{"2481273123", "Turbulence and Triumph: The Modi Years", "Rahul Agarwal and Bharathi S Pradhan", 35000},
				{"1230987145", "Handbook on Fisheries Statistics - 2018", "Ministry of fisheries", 40000},
				{"2440101143", "“Sridevi: Girl Woman Superstar”", "Satyarth Nayak", 20000},
				{"2445237812", "Listening, Learning and Leading", "Venkaiah Naidu", 25000},
				{"2481273123", "'My Life, My Mission'", "Baba Ramdev", 35000},
				{"1230987145", "'The New Delhi Conspiracy'", "Meenakshi Lekhi", 40000},
				{"2481273123", "‘The Diary of Manu Gandhi’", "Tridip Suhrud", 35000},
				{"1230987145", "\"A Prime Minister to Remember- Memories of a Military Chief\"", "Sushil Kumar", 40000}
		};
		
		Object[] columns = {"ID", "Book", "Author", "Book Price"};
		
		dtm = new DefaultTableModel(rows, columns);
		
		dataTable = new JTable(dtm);
		
		scrollPane = new JScrollPane(dataTable);
		
		topPanel.add(scrollPane);
		scrollPane.setPreferredSize(new Dimension(450, 350));
		
		nameLabel = new JLabel("ID");
		bookLabel = new JLabel("Book");
		priceLabel = new JLabel("Author");
		borrowdate = new JLabel("Book Price");
		
		nameField = new JTextField();
		bookField = new JTextField();
		priceField = new JTextField();
		borrowField = new JTextField();
		
		centerPanel.add(nameLabel);
		centerPanel.add(nameField);
		centerPanel.add(bookLabel);
		centerPanel.add(bookField);
		centerPanel.add(priceLabel);
		centerPanel.add(priceField);
		centerPanel.add(borrowdate);
		centerPanel.add(borrowField);
		
//		nameLabel.setForeground(Color.WHITE);
//		bookLabel.setForeground(Color.WHITE);
//		priceLabel.setForeground(Color.WHITE);
//		borrowdate.setForeground(Color.WHITE);
		
		//Bottom Panel
		addBtn = new JButton("Borrow");
		deleteBtn = new JButton("Return");
				
//		bottomPanel.add(addBtn);
//		bottomPanel.add(deleteBtn);

//		topPanel.setBackground(Color.DARK_GRAY);
//		centerPanel.setBackground(Color.DARK_GRAY);
//		bottomPanel.setBackground(Color.DARK_GRAY);
				
		mainPanel.add(topPanel, BorderLayout.NORTH);
		mainPanel.add(centerPanel, BorderLayout.CENTER);
		mainPanel.add(bottomPanel, BorderLayout.SOUTH);
		
		//Add Listener
		dataTable.addMouseListener(this);
		addBtn.addActionListener(this);
		deleteBtn.addActionListener(this);
		
		Container mainContainer = new Container();
		mainContainer.setLayout(new BorderLayout(8, 6));
//		mainContainer.setBackground(Color.YELLOW);
		
		//Top Box
		JPanel topPanel = new JPanel();
		topPanel.setBorder(new LineBorder(Color.BLACK, 1));
//		topPanel.setBackground(Color.ORANGE);
		topPanel.setLayout(new FlowLayout(5));
		topPanel.add(button1);
		topPanel.add(button2);
		topPanel.add(button3);
		topPanel.add(button4);
//		mainContainer.add(topPanel, BorderLayout.NORTH);
		
		//Left Inside Box Outer
		JPanel middlePanel = new JPanel();
		middlePanel.setBorder(new LineBorder(Color.BLACK, 1));
		middlePanel.setLayout(new FlowLayout(4, 4, 4));
//		middlePanel.setBackground(Color.CYAN);
		
		//Left Inside Box Inner
		JPanel gridPanel = new JPanel();
		gridPanel.setLayout(new GridLayout(4, 1, 5, 5));
		gridPanel.setBorder(new LineBorder(Color.BLACK, 1));
//		gridPanel.setBackground(Color.RED);
		
		gridPanel.add(button5);
		gridPanel.add(button6);
		gridPanel.add(button7);
		gridPanel.add(button8);
		
		//Center Box
		JLabel label = new JLabel();
		label.setOpaque(true);
		label.setBorder(new LineBorder(Color.BLACK, 1));
		
		middlePanel.add(gridPanel);
//		mainContainer.add(label);
		mainContainer.add(mainPanel);
		mainContainer.add(middlePanel, BorderLayout.WEST);
		
		f.setVisible(true);
		f.setSize(600, 600);
		f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		f.setLocationRelativeTo(null);
		f.add(mainContainer);
		f.setJMenuBar(menu);
		
		//Bottom Box
		JPanel bottomPanel = new JPanel();
		bottomPanel.setLayout(new FlowLayout(3));
		
		bottomPanel.add(addBtn);
		bottomPanel.add(deleteBtn);
//		bottomPanel.setBackground(Color.MAGENTA);
//		bottomPanel.setBorder(new LineBorder(Color.BLUE, 3));
		mainContainer.add(bottomPanel, BorderLayout.SOUTH);
		
		JMenu menuu = new JMenu("Menu");
		menu.add(menuu);
		JMenuItem newe = new JMenuItem("New");
		newe.addActionListener(this);
		newe.setActionCommand("New");
		menuu.add(newe);
		JMenuItem help = new JMenuItem("Help");
		menuu.add(help);
		JMenuItem exit = new JMenuItem("Exit");
		menuu.add(exit);
		
		JMenu regis = new JMenu("Registration");
		menu.add(regis);
		JMenuItem sign = new JMenuItem("Sign in");
		regis.add(sign);

		JMenu main = new JMenu("Feature");
		menu.add(main);
		JMenuItem lend = new JMenuItem("Lend");
		main.add(lend);
	}

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		new CL();
	}

	@Override
	public void actionPerformed(ActionEvent e) {
		// TODO Auto-generated method stub
		
		String command = e.getActionCommand();
		
		String input = tex1.getText();
		labelss.setText(input);
		labelss.setForeground(new Color(0xFFFFFF));
	
		//Age
		String inputy = tex2.getText();
		textt.setText(inputy);
		textt.setForeground(new Color(0xFFFFFF));
	
		//Gender
		String masuk = tex3.getText();
		gender.setText(masuk);
		gender.setForeground(new Color(0xFFFFFF));
	
		//Address
		String masukk = tex4.getText();
		address.setText(masukk);
		address.setForeground(new Color(0xFFFFFF));
		
		if(e.getSource() == addBtn) {
			boolean priceIsNum = true;
			String name = nameField.getText();
			String book = bookField.getText();
			String price = priceField.getText();
			String borrowdate = borrowField.getText();
			
			Object[] newRow = {name, book, price, borrowdate};
			
			try {
				Integer.parseInt(borrowdate);
			} catch (NumberFormatException e1) {
				priceIsNum = false;
			}
			
			if(priceIsNum && !name.trim().isEmpty() && !book.trim().isEmpty() && !price.trim().isEmpty() && !borrowdate.trim().isEmpty()) {
				dtm.addRow(newRow);
			}
			
		}
		else if(e.getSource() == deleteBtn) {
			int selectedRow = dataTable.getSelectedRow();
			if(selectedRow != -1) {
				dtm.removeRow(selectedRow);
			}
		}
		
		
		
	}

	@Override
	public void mouseClicked(MouseEvent e) {
		// TODO Auto-generated method stub
		if(e.getSource() == dataTable) {
			String name = dataTable.getValueAt(dataTable.getSelectedRow(), 0).toString();
			String book = dataTable.getValueAt(dataTable.getSelectedRow(), 1).toString();
			String price = dataTable.getValueAt(dataTable.getSelectedRow(), 2).toString();
			String borrowdate = dataTable.getValueAt(dataTable.getSelectedRow(), 3).toString();
			
			nameField.setText(name);
			bookField.setText(book);
			priceField.setText(price);
			borrowField.setText(borrowdate);
		}
	}

	@Override
	public void mouseEntered(MouseEvent arg0) {
		// TODO Auto-generated method stub
		
	}

	@Override
	public void mouseExited(MouseEvent arg0) {
		// TODO Auto-generated method stub
		
	}

	@Override
	public void mousePressed(MouseEvent arg0) {
		// TODO Auto-generated method stub
		
	}

	@Override
	public void mouseReleased(MouseEvent arg0) {
		// TODO Auto-generated method stub
		
	}

}
