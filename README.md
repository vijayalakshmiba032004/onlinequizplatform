# onlinequizplatform
import java.util.Scanner;

public class SimpleBankingApp {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double balance = 0.0; // Initialize the account balance to 0

        while (true) {
            System.out.println("\nWelcome to Simple Banking App!");
            System.out.println("1. Deposit Money");
            System.out.println("2. Withdraw Money");
            System.out.println("3. Check Balance");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");

            int choice = scanner.nextInt();

            switch (choice) {
                case 1: // Deposit Money
                    System.out.print("Enter the amount to deposit: ");
                    double depositAmount = scanner.nextDouble();
                    if (depositAmount > 0) {
                        balance += depositAmount;
                        System.out.println("₹" + depositAmount + " deposited successfully.");
                    } else {
                        System.out.println("Deposit amount must be positive.");
                    }
                    break;

                case 2: // Withdraw Money
                    System.out.print("Enter the amount to withdraw: ");
                    double withdrawAmount = scanner.nextDouble();
                    if (withdrawAmount > 0 && withdrawAmount <= balance) {
                        balance -= withdrawAmount;
                        System.out.println("₹" + withdrawAmount + " withdrawn successfully.");
                    } else if (withdrawAmount > balance) {
                        System.out.println("Insufficient balance!");
                    } else {
                        System.out.println("Withdrawal amount must be positive.");
                    }
                    break;

                case 3: // Check Balance
                    System.out.println("Your current balance is: ₹" + balance);
                    break;

                case 4: // Exit
                    System.out.println("Thank you for using Simple Banking App. Goodbye!");
                    scanner.close();
                    return;

                default:
                    System.out.println("Invalid choice! Please choose a valid option.");
            }
        }
    }
}
