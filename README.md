# Build-a-Basic-Bank-Account-System-with-Deposit-and-Withdrawal

import java.util.Scanner;

public class BankAccount {
    private String accountHolder;
    private double balance;

    // Constructor
    public BankAccount(String name, double initialBalance) {
        accountHolder = name;
        balance = initialBalance;
    }

    // Deposit method
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: ₹" + amount);
        } else {
            System.out.println("Invalid deposit amount.");
        }
    }

    // Withdraw method
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Withdrawn: ₹" + amount);
        } else {
            System.out.println("Insufficient balance or invalid amount.");
        }
    }

    // Display balance
    public void displayBalance() {
        System.out.println("Current Balance: ₹" + balance);
    }

    // Main method
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Welcome to Simple Bank System");

        System.out.print("Enter your name: ");
        String name = scanner.nextLine();

        System.out.print("Enter initial deposit amount: ₹");
        double initialAmount = scanner.nextDouble();

        BankAccount account = new BankAccount(name, initialAmount);
        account.displayBalance();

        boolean exit = false;
        while (!exit) {
            System.out.println("\nChoose an operation:");
            System.out.println("1. Deposit");
            System.out.println("2. Withdraw");
            System.out.println("3. Show Balance");
            System.out.println("4. Exit");
            System.out.print("Enter choice: ");
            int choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter amount to deposit: ₹");
                    double depositAmount = scanner.nextDouble();
                    account.deposit(depositAmount);
                    break;
                case 2:
                    System.out.print("Enter amount to withdraw: ₹");
                    double withdrawAmount = scanner.nextDouble();
                    account.withdraw(withdrawAmount);
                    break;
                case 3:
                    account.displayBalance();
                    break;
                case 4:
                    exit = true;
                    System.out.println("Thank you for using the bank system!");
                    break;
                default:
                    System.out.println("Invalid choice. Try again.");
            }
        }
        scanner.close();
    }
}

Output:
Output :

Welcome to Simple Bank System
Enter your name: GauravSingh
Enter initial deposit amount: ₹5000
Current Balance: ₹5000.0

Choose an operation:
1. Deposit
2. Withdraw
3. Show Balance
4. Exit
Enter choice: 1
Enter amount to deposit: ₹1500
Deposited: ₹1500.0

Choose an operation:
1. Deposit
2. Withdraw
3. Show Balance
4. Exit
Enter choice: 3
Current Balance: ₹6500.0
