![Github stats](https://github-readme-stats.vercel.app/api?username=MSrinitha)
![ReadMe Card](https://github-readme-stats.vercel.app/api/pin/?username=MSrinitha&repo=OIBSIP-Task2)
# OIBSIP-Task2
### Number Guessing Game in java


import java.io.*; 
import java.util.*; 
import javax.swing.JOptionPane;
class GuessNo
{
	static String nm="name";
	public static void main(String args[]){
		JOptionPane.showMessageDialog(null,"Welcome to Guessing Game!");
		String input;
		int t;
		input=JOptionPane.showInputDialog("Enter your name");
		String name=input;
		nm=name;
		JOptionPane.showMessageDialog(null,"There are 2 levels: Easy and Hard\nChoose a level");
		input=JOptionPane.showInputDialog("Type 1 for Easy Level and 2 for Hard Level");
		t=Integer.parseInt(input);
		fun(t);
	}

	static void fun(int t){
		String pn;
		int tot=100;
		String inp;
		if(t==1){
			JOptionPane.showMessageDialog(null,"you have choosen easy level");
			level(100,tot,10,10);
		}
		else if(t==2){
			JOptionPane.showMessageDialog(null,"you have choosen hard level");
			level(100,tot,5,20);
		}
		else{
			JOptionPane.showMessageDialog(null,"invalid option");
		}
		pn=JOptionPane.showInputDialog("do u want to play again:y/n");
		char p=pn.charAt(0);
		if(p=='y'){
			inp=JOptionPane.showInputDialog("Type 1 for Easy Level and 2 for Hard Level");
			int te=Integer.parseInt(inp);
			fun(te);
		}
		else if(p=='n')
			JOptionPane.showMessageDialog(null,"exit");
		else
			JOptionPane.showMessageDialog(null,"invalid option");
		
	} 
	
	
	 static void level(int n,int tot,int ch,int sc){
		
		JOptionPane.showMessageDialog(null,"guess the number btn 1 and "+n+" in "+ch+" chances");
		int max=1;
		String in;
		int guess_no;
		int min=n;
		int score=tot;
		int random_no=(int)(Math.random()*(max-min+1)+min);
		int ans=0;
		int c=0;
		while(c<ch){
			in=JOptionPane.showInputDialog("guess Number");
			guess_no=Integer.parseInt(in);
			c++;
			if(guess_no<random_no){
				score-=sc;
				JOptionPane.showMessageDialog(null,"you guessed low :( ..try again!! remaining chances "+(ch-c));
				
			}
			else if(guess_no>random_no){
				score-=sc;
				JOptionPane.showMessageDialog(null,"you guessed high :( ..try again!!remaining chances "+(ch-c));
				
			}
			else if(guess_no==random_no){
					ans=guess_no;
					break;
			}	
		}
		if(ans==random_no)
			JOptionPane.showMessageDialog(null,"Congratulations "+nm+" :) u guessed right at "+c+" chance and scored "+score);
		else
			JOptionPane.showMessageDialog(null,"u didn't guessed :(...random no is:"+random_no);
	}
}
