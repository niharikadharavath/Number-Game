
import java.util.Scanner;
public class NumberGame
{
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        int chances=7;
        int finals=0;
        boolean playAgain=true;
        System.out.println("Welcome player!");
        System.out.println("Hey player you have about"+chances+"to win the game");
        while(playAgain){
            int rand=getrandN(1,100);
            boolean guess=false;
            for(int i=0;i<chances;i++){
        
                 System.out.println("Chance"+(i+1)+" Enter your guess:");
                int User=sc.nextInt();
                if(User==rand){
                     guess=true;
                    finals+=1;
                    System.out.println("You Won it");
                     break;
                }
                else if(User>rand){
                    System.out.println("Too High");
                }
                 else{
                    System.out.println("Too Low");
                }
            }
             if(guess==false){
                System.out.println("Sorry You Lost the Chances.The number is"+rand);
            }
            System.out.println("Do you want toplay Again(y/n)");
            String pA=sc.next();
            playAgain=pA.equalsIgnoreCase("y");
        }
        System.out.println("That's it player,you enjoyed the it");
        System.out.println("Here is your Score"+finals);
    }
        public static int getrandN(int min,int max){
            return(int)(Math.random()*(max-min+1)+min);
        }
    
}
    
