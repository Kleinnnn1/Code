import java.util.Random;
import java.util.Scanner;

public class Arrays {

	public static void main(String[] args) {
		Random rnd = new Random();
		
		int Rock = 1;
		int Paper = 2;
		int Scissor = 3;
		int[] array = {Rock, Paper, Scissor};
		
		
		int player_Win = 2;
		int ai_Win = 2;
		int playerScore = 0;
		int aiScore = 0;
		char continueGame = 0;
	

		int type = 0;
		
		Scanner s = new Scanner(System.in);
		System.out.println("""
				Rock Paper Scissor vs AI Game
				Instruction: 1=Rock, 2=Paper, 3=Scissor
				The game is best of 3
				""");
		
		do {
			
			do{
				int randomfromarray = array[rnd.nextInt(3)];
				System.out.print("Enter a number: ");
				type = s.nextInt();
				
			
				
				if (type==1) {
					if (randomfromarray==1) {
						System.out.println("You choose rock and the Ai choose Rock");
					}
					else if (randomfromarray==2) {
						System.out.println("You choose rock and the Ai choose Paper");
					}
					else {
						System.out.println("You choose rock and the Ai choose Scissor");
					}
					
				
				}
				else if (type==2) {
					if (randomfromarray==1) {
						System.out.println("You choose Paper and the Ai choose Rock");
					}
					else if (randomfromarray==2) {
						System.out.println("You choose Paper and the Ai choose Paper");
					}
					else {
						System.out.println("You choose Paper and the Ai choose Scissor");
					}
				}
				else if (type==3) {
					if (randomfromarray==1) {
						System.out.println("You choose Scissor and the Ai choose Rock");
					}
					else if (randomfromarray==2) {
						System.out.println("You choose Scissor and the Ai choose Paper");
					}
					else {
						System.out.println("You choose Scissor and the Ai choose Scissor");
					}
				}
				else {
					System.out.println("Please input only from 1 to 3.");
					System.out.println();
					
				}
				
				if(type==randomfromarray) {
					System.out.println("DRAW!");
					System.out.println();
				}
				else if (type==Rock && randomfromarray==Scissor) {
					System.out.println("You win!");
					playerScore++;
					System.out.println();
					
					}
				else if (type==Rock && randomfromarray==Paper) {
					System.out.println("Ai win!");
					System.out.println();
					aiScore++;
					
					}
				else if (type==Paper && randomfromarray==Rock) {
					System.out.println("You win!");
					System.out.println();
					playerScore++;
					 
					}
				else if (type==Paper && randomfromarray==Scissor) {
					System.out.println("Ai win!");
					System.out.println();
					aiScore++;
					 
					}
				else if (type==Scissor && randomfromarray==Paper) {
					System.out.println("You win!");
					System.out.println();
				 	playerScore++;
				 	
				}
				else if (type==Scissor && randomfromarray==Rock) {
					 System.out.println("Ai win!");
					 System.out.println();
					 aiScore++; 
					
				}
			
			} while(playerScore!=player_Win && aiScore!=ai_Win);

			if(aiScore==ai_Win) {
				System.out.println("Aww you lose!\n");
			}
			else if(playerScore==player_Win) {
				System.out.println("Congratulation you win!\n");
			}
			
			
			player_Win = 2;
			ai_Win = 2;
			playerScore = 0;
			aiScore = 0;
			continueGame = 0;
			type = 0;
			
			System.out.print("Enter Y to continue and N to quit: ");
			continueGame = s.next().charAt(0);
			if (continueGame=='N' || continueGame=='n') {
				System.out.println("Rest you idiot");
				
			} 
			
		}while (continueGame=='Y' || continueGame=='y');

	
	}

}

