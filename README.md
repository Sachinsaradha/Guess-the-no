import java.util.Scanner;
import java.util.Random;

public class GuessTheNumber {
    public static void main(String[] args) {
        // Creating Scanner object for taking input from the user
        Scanner scanner = new Scanner(System.in);
        
        // Creating Random object for generating random numbers
        Random random = new Random();
        
        // Generate a random number between 1 and 100
        int numberToGuess = random.nextInt(100) + 1;
        int numberOfTries = 0;
        int guess;
        boolean win = false;
        
        System.out.println("Guess a number between 1 and 100:");

        // Game loop
        while (!win) {
            guess = scanner.nextInt(); // read the user input
            numberOfTries++;
            
            if (guess == numberToGuess) {
                win = true;
            } else if (guess < numberToGuess) {
                System.out.println("Your guess is too low. Try again:");
            } else if (guess > numberToGuess) {
                System.out.println("Your guess is too high. Try again:");
            }
        }

        System.out.println("Congratulations! You guessed the number in " + numberOfTries + " tries.");

        // Close the scanner
        scanner.close();
    }
}
