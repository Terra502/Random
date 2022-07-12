import javax.swing.*;
import java.awt.event.*;
import java.awt.*;
import javax.swing.JButton;
import java.awt.GridBagConstraints;
import java.awt.GridBagLayout;
import java.awt.BorderLayout;
import java.io.*;

public class Tetris_Niederlage extends JFrame implements ActionListener
{
  JLabel _text       = new JLabel("<html><body><h1 style=\"font-size:2em;color:red;\">Highscore</h1></body></html>");
  JLabel _highscore  = new JLabel();
  JLabel _neuerText  = new JLabel("<html><body><h2 style=\"font-size:2em;color:red;\">Erreichte Punkte</h2></body></html>");
  JLabel _neuerScore = new JLabel();
  
  JButton _erneut    = new JButton("<html><body><font color=\"red\">Erneut</font></body></html>");
  JButton _verlassen = new JButton("<html><body><font color=\"blue\">Verlassen</font></body></html>");
  
  JPanel _panelErneut    = new JPanel();
  JPanel _panelVerlassen = new JPanel();
  JPanel _panelText      = new JPanel();
  JPanel _panelHighscore = new JPanel();
  JPanel _panelNeuerText = new JPanel();
  JPanel _panelNeuerScore= new JPanel();    
  
  int highscore = 0;
  int aktuell   = 0;
  
  String _line;
  
  GridBagConstraints _gbc;
  
  Tetris_Niederlage(String title)
  {
    super(title);
    setLayout(new GridBagLayout());
    getContentPane().setBackground(new Color(211,211,211));
    _panelErneut.setBackground(new Color(211,211,211));
    _panelVerlassen.setBackground(new Color(211,211,211));
    _panelText.setBackground(new Color(211,211,211));
    _panelHighscore.setBackground(new Color(211,211,211));
    _panelNeuerText.setBackground(new Color(211,211,211));
    _panelNeuerScore.setBackground(new Color(211,211,211));
    _gbc = new GridBagConstraints();
    
    _panelText.add(_text);
    _gbc.gridx = 2;
    _gbc.gridy = 0;
    _gbc.anchor = GridBagConstraints.PAGE_START;
    add(_panelText, _gbc);
    
    
    _panelHighscore.add(_highscore);
    _gbc.gridx = 2;
    _gbc.gridy = 2;
    _gbc.anchor = GridBagConstraints.PAGE_START;
    add(_panelHighscore, _gbc);
    
    
    
    _panelNeuerText.add(_neuerText);
    _gbc.gridx = 2;
    _gbc.gridy = 3;
    _gbc.anchor = GridBagConstraints.PAGE_START;
    add(_panelNeuerText, _gbc);
    
    _panelNeuerScore.add(_neuerScore);
    _gbc.gridx = 2;
    _gbc.gridy = 4;
    _gbc.anchor = GridBagConstraints.PAGE_START;
    add(_panelNeuerScore, _gbc);
    
    
    
    _panelErneut.setLayout(new BorderLayout());
    _panelErneut.add(_erneut, BorderLayout.SOUTH);
    _panelErneut.setPreferredSize(new Dimension(100,100));
    _gbc.gridx = 1;
    _gbc.gridy = 4;
    _gbc.anchor = GridBagConstraints.LAST_LINE_START;
    add(_panelErneut, _gbc);
    _erneut.addActionListener(this);
    _erneut.setActionCommand("erneut");
    
    _panelVerlassen.setLayout(new BorderLayout());
    _panelVerlassen.add(_verlassen);
    _panelErneut.setPreferredSize(new Dimension(100,100));
    _gbc.gridx = 3;
    _gbc.gridy = 4;
    _gbc.anchor = GridBagConstraints.LAST_LINE_END;
    add(_panelVerlassen, _gbc);
    _verlassen.addActionListener(this);
    _verlassen.setActionCommand("verlassen");
    
    
    File fileName = new File("log.txt");
    BufferedReader reader = null;
    String _line       = null;
    
    try {
      reader = new BufferedReader(new FileReader(fileName));
      _line = reader.readLine();
      while (_line != null) { 
        if (_line.equals("")) {
        } else {
          aktuell = Integer.parseInt(_line);
          if (aktuell > highscore) {
            highscore = aktuell;
          } // end of if  
        } // end of if-else
        _line = reader.readLine();
      }// end of while
    } catch (FileNotFoundException e) {
      e.printStackTrace();
    } catch (IOException e) {
      e.printStackTrace();
    } finally {
      try {
        if (reader != null) {
          reader.close();
        }
      } catch (IOException e) {
      }
    }
    _highscore.setText("<html><body><h1 style=\"font-size:2em;color:red;\">" + highscore + "</h1></body></html>");
    _neuerScore.setText("<html><body><h2 style=\"font-size:2em;color:red;\">" + aktuell + "</h2></body></html>");
    
    setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
  }
  
  public void actionPerformed(ActionEvent evt)
  {
    if (evt.getActionCommand().equals("erneut")) {
      dispose();
      Tetris_V3 frame = new Tetris_V3("Tetris");
      frame.pack();
      frame.setSize(500,800);
      frame.setLocation(600,200);
      frame.setResizable(false);
      frame.setVisible(true);
    } // end of if
    if (evt.getActionCommand().equals("verlassen")) {
      System.exit(0);
    } // end of if
  }
}
