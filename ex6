package bank;
import java.util.Scanner;

interface BankAccount {
    void deposit(double amount);
    void withdraw(double amount) throws Exception;
    void balance();
}

class Account implements BankAccount {
    String name;
    int accNo;
    double balance;

    Account(String name, int accNo, double balance) {
        this.name = name;
        this.accNo = accNo;
        this.balance = balance;
    }

    public void deposit(double amount) {
        if (amount <= 0) {
            System.out.println("Invalid deposit amount");
        } else {
            balance += amount;
            System.out.println("Amount Deposited Successfully");
            System.out.println("Available Balance: Rs. " + balance);
        }
    }

    public void withdraw(double amount) throws Exception {
        if (amount <= 0) {
            throw new Exception("Invalid withdrawal amount");
        }
        if (amount > balance) {
            throw new Exception("Insufficient Balance");
        }
        balance -= amount;
        System.out.println("Amount Withdrawn Successfully");
        System.out.println("Available Balance: Rs. " + balance);
    }

    public void balance() {
        System.out.println("Available Balance: Rs. " + balance);
    }
}

public class Bank {
    public static void main(String[] args) throws Exception {
        Scanner sc = new Scanner(System.in);

        System.out.println("Account Holder Name: ");
        String name = sc.nextLine();

        System.out.println("Enter Account Number: ");
        int acc = sc.nextInt();

        System.out.print("Enter Initial Balance: ");
        double balance = sc.nextDouble();

        Account b = new Account(name, acc, balance);

        System.out.println("Enter your choice: ");
        sc.nextLine(); // Consume newline
        String ch = sc.nextLine();

        switch (ch) {
            case "Deposit":
                System.out.print("Enter deposit amount: ");
                double d = sc.nextDouble();
                b.deposit(d);
                break;

            case "Draw":
                System.out.print("Enter withdraw amount: ");
                double w = sc.nextDouble();
                b.withdraw(w);
                break;

            case "Balance":
                b.balance();
                break;

            default:
                System.out.println("Invalid choice");
        }

        sc.close();
    }
}
