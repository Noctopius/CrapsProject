import java.util.Scanner;
public class Craps
// Daniel Kim
// README - Simulation Mode that was added in this program is not related to the assignment.
//          Simply enter anything but "yes" (case is ignored), to enter Normal Mode.
{
    public static void main(String[] args)
    {
        System.out.println("Daniel Kim\n"); // Prints out name.
        boolean gameRunning = true; // Sets the status of the game to running.
        Scanner in = new Scanner(System.in); // Declares Scanner.
        System.out.print("Do you wish to enter Simulation Mode? "); // Prompts the user whether they want to enter Simulation Mode. This mode is not part of the assignment.
        String mode = in.nextLine();
        if(mode.equalsIgnoreCase("yes")) // Checks whether the user answered "yes", ignoring case. See else statement for Normal Mode.
        {
            System.out.println("You have entered Simulation Mode."); // Informs the user that they have entered Simulation Mode.
            System.out.print("\nEnter starting money: "); // Prompts the user to enter starting money.
            int simulationStartingBalance = in.nextInt(); // Stores the response to be used as a constant.
            int simulationBalance = simulationStartingBalance; // Stores an identical value into the variable that will actually be manipulated.
            System.out.print("Enter bet: "); // Prompts the user to enter a bet.
            int simulationBet = in.nextInt(); // Stores the response.
            System.out.print("Enter the number of cycles: "); // Prompts the user to enter the number of repetitions.
            int simulationCycles = in.nextInt(); // Stores the response.
            int simulationGreatestBalance = simulationStartingBalance; // Sets the greatest value of balance to the current balance.
            int simulationLeastBalance = simulationStartingBalance; // Sets the least value of balance to the current balance.
            int i = 0; // Declares i.
            while(i < simulationCycles) // While i is less than the value stores in simulationCycles, ...
            {
                int simulationDie1 = (int)(Math.random() * 6 + 1); // Rolls the first die.
                int simulationDie2 = (int)(Math.random() * 6 + 1); // Rolls the second die.
                int simulationRoll = simulationDie1 + simulationDie2; // Stores the sum.
                System.out.println("\nRoll: " + simulationDie1 + ", " + simulationDie2); // Prints out the roll.
                switch(simulationRoll) // Initializes switch
                {
                    case 2 : // If simulationRoll is this value or any of the ones right after, ...
                    case 3 :
                    case 12 :
                        System.out.println("Result: Loss"); // Informs of the loss.
                        simulationBalance -= simulationBet; // Subtracts the bet from the balance.
                        System.out.println("Balance: " + simulationBalance); // Informs of the balance.
                        break; // Breaks out.
                    case 7 : // Else, if simulationRoll is this value or any of the ones right after, ...
                    case 11 :
                        System.out.println("Result: Victory"); // Informs of the victory. 
                        simulationBalance += simulationBet; // Adds the bet to the balance.
                        System.out.println("Balance: " + simulationBalance); // Informs of the balance.
                        break; // Breaks out.
                    default : // Otherwise, ...
                        System.out.println("Result: Tie"); // Informs of the tie.
                        System.out.println("Balance: " + simulationBalance); // Informs of the balance.
                }
                i++;
                if(simulationBalance > simulationGreatestBalance) // If balance is greater than the stored greatest balance, ...
                    simulationGreatestBalance = simulationBalance; // Stores the balance as the new greatest balance.
                if(simulationBalance < simulationLeastBalance) // If balance is less than the stored least balance, ...
                    simulationLeastBalance = simulationBalance; // Stores the balance as the new least balance.
                if(simulationBalance <= 0) // If balance is less than or equal to 0, ...
                    break; // Stops the simulation.
            }
            System.out.println("\nCycles Completed: " + i); // Informs of the cycles completed.
            System.out.println("Final Balance: " + simulationBalance); // Informs of the final balance.
            System.out.println("Total Profit: " + (simulationBalance - simulationStartingBalance)); // Informs of the total profit.
            System.out.println("Average Profit: " + (simulationBalance - simulationStartingBalance) / (double)(simulationCycles)); // Informs of the average profit.
            System.out.println("Lowest Balance: " + simulationLeastBalance); // Informs of the lowest recorded balance.
            System.out.println("Highest Balance: " + simulationGreatestBalance); // Informs of the greateset recorded balance.
            
        }
        else
        {
            System.out.println("You have entered Normal Mode."); // Informs the user that they have entered Normal Mode.
            System.out.print("\nHow much money do you have? "); // Prompts the user to enter their balance.
            int balance = in.nextInt(); // Receives and stores the balance.
            if(balance == 0) // If the balance is 0, ...
            {
                System.out.println("You're broke!"); // Tells the user that they are broke.
                gameRunning = false; // Ends the game.
            }
            while(balance < 0) // Simultaneously checks whether and continues running until the balance is a positive number. If it is negative, ...
            {
                System.out.print("Enter a positive value! "); // Prompts the user to enter a positive value.
                balance = in.nextInt(); // Stores the response.
            }
            while(gameRunning) // Executes the game while gameRunning is true.
            {
                System.out.print("How much do you wish to bet? "); // Prompts the user to enter their desired bet.
                int bet = in.nextInt();
                while(bet > balance) // Simultaneously checks whether and continues running until the user's bet is less than or equal to their balance. 
                {
                    System.out.print("You don't have that much! Enter another amount: "); // Prompts the user to enter another amount.
                    bet = in.nextInt(); // Stores the response.
                }
                if(bet == 0) // Checks whether the bet is 0.
                {
                    System.out.println("Why did you even start the game?? Bye!"); // Dismisses the user.
                    break; // Stops the game.
                }
                while(bet < 0) // Simultaneously checks whether the bet is less than 0 and continues running until it is not.
                {
                    System.out.print("Enter a positive value! "); // Prompts the user to enter a positive value.
                    bet = in.nextInt(); // Saves the response.
                }
                int die1 = (int)(Math.random() * 6 + 1); // Rolls the first die.
                int die2 = (int)(Math.random() * 6 + 1); // Rolls the second die.
                System.out.println("Your roll: " + die1 + ", " + die2); // Tells the user the values of the two dice.
                int roll = die1 + die2; // Stores the sum of the two dice.
                if(roll == 2 || roll == 3 || roll == 12) // Checks whether the sum is a losing value. If it is, ...
                {
                    System.out.println("YOU LOSE!!!"); // Tells the user that they lost.
                    balance -= bet; // Subtracts their bet from their balance.
                    System.out.println("Your Balance: " + balance); // Tells the user their balance.
                }
                else if(roll == 7 || roll == 11) // If it is not, checks whether it is a winning value. If it is, ...
                {
                    System.out.println("YOU WIN!!!"); // Tells the user that they won.
                    balance += bet; // Adds their bet to their balance.
                    System.out.println("Your Balance: " + balance); // Tells the user their balance.
                }
                else // If it is not, ...
                    switch(roll)
                    {
                        case 4 :
                        case 5 :
                        case 6 :
                        case 8 :
                        case 9 :
                        case 10 :
                            System.out.println("try again"); // Tells the user to try again.
                    }
                if(balance == 0) // Checks if the user's balance is 0. If it is, ...
                {
                    System.out.println("You're busted!"); // Tells them they're busted.
                    gameRunning = false; // Stops the game.
                }
                else // If it is not, ...
                {
                    System.out.print("New game(n), continue(c), or exit(e)? "); // Prompts the user to enter their action.
                    in.nextLine(); // Refreshes Scanner
                    String action = in.nextLine(); // Receives and stores the action.
                    if(action.equalsIgnoreCase("new game") || action.equalsIgnoreCase("n")) // Checks whether the action is equal to "new game" or "n", ignoring the case. If it is, ...
                    {
                        System.out.print("\nHow much money do you have? "); // Prompts the user to enter their balance.
                        balance = in.nextInt(); // Receives and stores the balance.
                    }
                    else if(action.equalsIgnoreCase("continue") || action.equalsIgnoreCase("c")) // If it is not, checks whether the user's action is equal to "continue" or "c", ignoring the case. If it is, ...
                        System.out.println(); // Prints out an empty line.
                    else // If it is not, ...
                        gameRunning = false; // Stops the game.
                }
            }
        }
    }
}
