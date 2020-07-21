import java.awt.*;
import java.applet.*;
import java.awt.event.*;
import java.awt.*;
import java.applet.*;
import java.awt.event.*;
/*<applet code="CompoundInterest" width=400 height=200>
</applet>*/
public class CompoundInterest extends Applet implements ActionListener
{
String str="THE AMOUNT IS";
float amount;
Button b1;
Label l1,l2,l3;
TextField t1,t2,t3;
public void init()
{

setBackground(Color.magenta);
setForeground(Color.blue);

l1=new Label("PRINCIPAL");
t1=new TextField(6);
l2=new Label("RATE ");
t2=new TextField(6);
l3=new Label("YEAR");
t3=new TextField(6);
add(l1);
add(t1);
add(l2);
add(t2);
add(l3);
add(t3);
b1=new Button("CALCULATE");
add(b1);
b1.addActionListener(this);
}
public  void actionPerformed(ActionEvent e)
{
int pri=Integer.parseInt(t1.getText().trim());
int year=Integer.parseInt(t2.getText().trim());
int rate=Integer.parseInt(t3.getText().trim());
amount=(pri*(((1+rate)^year)-1));
repaint();
}
public void paint(Graphics g)
{
Font font=new Font("Monotype corsiva",Font.BOLD,30);
g.setFont(font);
FontMetrics fm=g.getFontMetrics();
g.setColor(Color.GREEN);
g.drawString(" THE AMOUNT   "+amount,40,100);
}
}
