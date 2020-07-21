import java.awt.*;
import java.applet.*;
import java.awt.event.*;
import java.awt.*;
import java.applet.*;
import java.awt.event.*;
/*<applet code="HouseConstructionCost" width=400 height=200>
</applet>*/
public class HouseConstructionCost extends Applet implements ActionListener
{
String str="TOTAL COST IN INR";
float amount;
Button b1;
Label l1,l2,l3;
TextField t1,t2,t3;
public void init()
{

setBackground(Color.magenta);
setForeground(Color.blue);

l1=new Label("TOTAL AREA");//area
t1=new TextField(6);
l2=new Label("STANDARD MATERIAL(0),ABOVE STANDARD(1),HIGH STANDARD(2)");
t2=new TextField(20);
l3=new Label("FULLY AUTOMATED HOUSE(0/1)");
t3=new TextField(20);
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
int ta=Integer.parseInt(t1.getText().trim());
int sm=Integer.parseInt(t2.getText().trim());
int fah=Integer.parseInt(t3.getText().trim());
if(sm==0 && fah==0)
{
amount=ta*12000;
}
if(sm==1 && fah==0)
{
amount=ta*15000;
}
if(sm==2 && fah==0)
{
amount=ta*18000;
}
if(sm==2 && fah==1)
{
amount=ta*25000;
}
if(sm==0 && fah==1)
{
amount=0;
}
if(sm==1 && fah==1)
{
amount=0;
}
repaint();
}
public void paint(Graphics g)
{
Font font=new Font("Monotype corsiva",Font.BOLD,20);
g.setFont(font);
FontMetrics fm=g.getFontMetrics();
g.setColor(Color.GREEN);
g.drawString("TOTAL COST IN INR  "+amount,150,200);
}
}
