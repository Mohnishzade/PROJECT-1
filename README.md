# PROJECT-1
//CODE SOFT JULY BATCH24.
import java.util.Scanner;
import java.util.Random;

public class NumberGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        int minRange = 1;
        int maxRange = 100;
        int maxAttempts = 5;
        int rounds = 3;
        int totalScore = 0;

        for (int round = 1; round <= rounds; round++) {
            int numberToGuess = random.nextInt(maxRange - minRange + 1) + minRange;
            int attempts = 0;
            int score = 0;

            System.out.println("Round " + round);

            while (attempts < maxAttempts) {
                System.out.print("Enter your guess (between " + minRange + " and " + maxRange + "): ");
                int guess = scanner.nextInt();
                attempts++;

                if (guess == numberToGuess) {
                    System.out.println("Congratulations! You guessed the number in " + attempts + " attempts.");
                    score = maxAttempts - attempts + 1; 
           break;
                } else if (guess < numberToGuess) {
                    System.out.println("Too low!");
                } else {
                    System.out.println("Too high!");
                }
            }

            if (attempts == maxAttempts) {
                System.out.println("Sorry, you ran out of attempts. The number was " + numberToGuess);
            }

            totalScore += score;
        }

        System.out.println("Your total score is: " + totalScore);
    }
}
