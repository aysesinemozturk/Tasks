
### Task 2
```
Title: Simulate the Game "Rock(🪨), Paper(📰), Scissors(️️✂️)"

1. Get Player's Nicknames:

   Create a function that asks for nicknames 
   and returns these values to the main method.

2. Take the inputs
   
   Create a function which takes the selections as integers

   The function takes the input of both players 

      * 1 -> (Rock(🪨)
      * 2 -> Paper(📰)
      * 3 -> Scissors(️️✂️))

   Return the selections to the main method

3. Decide Winner
   
   Create a function that tooks the players and selections.
   Return the winner player's nickname

   The rules of Rock(🪨), Paper(📰), Scissors(️️✂️), if not known:

     Both players have to say either 
     "Rock(🪨)", "Paper(📰)" or "Scissors(️️✂️)" at the same time.

  -> Rock(🪨)     beats   Scissors(️️✂️)
  -> Paper(📰)    beats   Rock(🪨)
  -> Scissors(️️✂️)  beats   Paper(📰)

4. Announce the Winner

   Take the output of the method written in third step.
   Announce the winner in a fancy way !

5. Create a Fork on GitHub

6. Clone the repository

7. Add your code & changes

8. Push to the GitHub & Create a pull request

```
### Sample Case
```
===============> Welcome to Rock Paper Scissors Game <===============

Author      : Durmuş Kartci & Emin Kartci
Date        : 05/02/2021
GitHub      : eminkartci
-----------------------------------------------------------------

Player 1 Nickname: <Take Input> (eminK)
Player 2 Nickname: <Take Input> (durmusK)

-----------------------||Game is Starting||-----------------------

Player 1 Turn: <Take Input> (Paper)
Player 2 Turn: <Take Input> (Rock)

---------------------------!! WINNER !!---------------------------

"eminK" is the winner !!

```
---
### Thanks
```
Author      : Durmuş Kartci & Emin Kartci
Date        : 05/02/2021
Difficulty  : Easy
Website     : eminkartci.com
```
//extension version of task 2
package to_do_list;

import java.util.*;

public class second_task_extension {

	public static void main(String[] args) {
		
		Scanner console = new Scanner(System.in);
		
		System.out.println("===============> Welcome to Rock Paper Scissors Game <===============");
		
		//assigning player names, this game can be done with exactly 2 players
		String player_1 =  Get_nickname(console);
		String player_2 =  Get_nickname(console);
		System.out.println("Player 1 Nickname: " + player_1);
		System.out.println("Player 2 Nickname: " + player_2);
		
		System.out.println("-----------------------||GAME IS STARTING||-----------------------");
		
		int player_1_points = 0;
		int player_2_points = 0;
		
		//continue gaming until whoever get 3 points in total
		game(player_1, player_2, player_1_points, player_2_points, console);
		
		
		System.out.println("-----------------------||THE FINAL WINNER||-----------------------");
		
		//assigning final winner
		System.out.println("final winner is " + winner(player_1_points, player_2_points, player_1, player_2));
		
}
	
	public static String Get_nickname(Scanner console) {
		//take nicknames of both players
				String nickname = console.next();
				return nickname;
	
	}
	
	public static void game(String player_1, String player_2, int player_1_points, int player_2_points, Scanner console) {
		
		int i =1;
		
		while (player_1_points < 3 && player_2_points < 3) {
			
			System.out.println("-----------------------||ROUND" + i + "||-----------------------");
			
			String player_1_decision = console.next();
			String player_2_decision = console.next();
			
			//if they choose same thing
			if(player_1_decision.equals(player_2_decision)) {
				
				System.out.println(player_1 +"'s turn: " + player_1_decision);
			    System.out.println(player_2 +"'s turn: " + player_2_decision);
				System.out.println("it is a tie, no points gained for both players");
				i++;
			
				
			// the cases where player 1 wins	
			} else if(
					(player_1_decision.equals("rock")&& player_2_decision.equals("scissors")) ||
					(player_1_decision.equals("paper") && player_2_decision.equals("rock")) ||
					(player_1_decision.equals("scissors") && player_2_decision.equals("paper"))) {
				
				       System.out.println(player_1 +"'s turn: " + player_1_decision);
				       System.out.println(player_2 +"'s turn: " + player_2_decision);
				       System.out.println(player_1 + " wins!");
				       player_1_points++;
				       i++;
				      
			
			} else {
				
				System.out.println(player_1 +"'s turn: " + player_1_decision);
			    System.out.println(player_2 +"'s turn: " + player_2_decision);
				System.out.println(player_2 + " wins!");
			      
				player_2_points++;
				i++;
				
			}
			
			
		}
		
	}
	
	//who gets 3 points at the end of the game is our final winner
	public static String winner(int player_1_points, int player_2_points, String player_1, String player_2) {

		if (player_1_points == 3) {
			
			return player_1;
		
		} else {

			return player_2;
			
		
		}	
	}
}
	

