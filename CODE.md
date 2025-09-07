# BANKING-SYSTEM
import java.util.Scanner;

public class BankingSystem {
    // Action constants
    static final int ADD_MONEY = 1;
    static final int WITHDRAW_MONEY = 2;
    static final int CHECK_WALLET = 3;
    static final int EXIT_APP = 4;

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int wallet = 18745; // Starting amount
        int action;

        do {
            System.out.println("\n--- BankingSystem Menu ---");
            System.out.println(ADD_MONEY + ". Add Money");
            System.out.println(WITHDRAW_MONEY + ". Withdraw Money");
            System.out.println(CHECK_WALLET + ". Check Wallet");
            System.out.println(EXIT_APP + ". Quit");
            System.out.print("Choose option: ");
            action = scan.nextInt();

            switch (action) {
                case ADD_MONEY:
                    System.out.print("Enter amount to add: ");
                    int add = scan.nextInt();
                    wallet += add;
                    System.out.println(add + " added successfully.");
                    break;

                case WITHDRAW_MONEY:
                    System.out.print("Enter amount to withdraw: ");
                    int take = scan.nextInt();
                    if (take <= wallet) {
                        wallet -= take;
                        System.out.println(take + " withdrawn.");
                    } else {
                        System.out.println("Not enough amount to be withdrawn.");
                    }
                    break;

                case CHECK_WALLET:
                    System.out.println("Current Wallet Balance: " + wallet);
                    break;

                case EXIT_APP:
                    System.out.println("Session ended. Thank you!");
                    break;

                default:
                    System.out.println("Invalid input. Try again.");
            }
        } while (action != EXIT_APP);

        scan.close();
    }
}
