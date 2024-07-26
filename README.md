import java.util.Random;
import java.util.Scanner;

public class NumberGuessing {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        System.out.println("Welcome to the Number Guessing Game!");
        System.out.print("Enter the minimum number of the range: ");
        int min = scanner.nextInt();
        System.out.print("Enter the maximum number of the range: ");
        int max = scanner.nextInt();

        if (min >= max) {
            System.out.println("Invalid range. The maximum number must be greater than the minimum number.");
            return;
        }

        int randomNumber = random.nextInt(max - min + 1) + min;
        int guess;
        int attempts = 0;

        System.out.println("I have picked a number between " + min + " and " + max + ". Try to guess it!");

        do {
            System.out.print("Enter your guess: ");
            guess = scanner.nextInt();
            attempts++;

            if (guess < randomNumber) {
                System.out.println("Too low!");
            } else if (guess > randomNumber) {
                System.out.println("Too high!");
            } else {
                System.out.println("Correct! You've guessed the number in " + attempts + " attempts.");
            }
        } while (guess != randomNumber);

        scanner.close();
    }
}
