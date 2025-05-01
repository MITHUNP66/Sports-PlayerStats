# Sports-PlayerStats
A simple Java-based console application demonstrating the use of object-oriented programming concepts such as inheritance, encapsulation, and input validation. The program allows users to create and manage basic profiles for two types of players — Cricket and Football — capturing both shared and sport-specific details.

code:
package com.javeprograming;
class Account {
    private int accountNumber;
    protected double balance;

    public Account(int accountNumber, double balance) {
        this.accountNumber = accountNumber;
        this.balance = balance;
    }

    public int getAccountNumber() {
        return accountNumber;
    }

    public double getBalance() {
        return balance;
    }

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: " + amount);
        } 
        else {
            System.out.println("Invalid deposit amount.");
        }
    }

    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Withdrawn: " + amount);
        } 
        else {
            System.out.println("Invalid or insufficient balance for withdrawal.");
        }
    }

    // Method to be overridden
    public double calculateInterest() {
        return 0.0;
    }
}

// Subclass: SavingsAccount
class SavingsAccount extends Account {
    private double interestRate;

    public SavingsAccount(int accountNumber, double balance, double interestRate) {
        super(accountNumber, balance);
        this.interestRate = interestRate;
    }

    @Override
    public double calculateInterest() {
        return balance * interestRate;
    }
}

// Subclass: CheckingAccount
class CheckingAccount extends Account {
    private double monthlyFee;

    public CheckingAccount(int accountNumber, double balance, double monthlyFee) {
        super(accountNumber, balance);
        this.monthlyFee = monthlyFee;
    }

    @Override
    public double calculateInterest() {
        return 0.0; // Checking accounts do not earn interest
    }

    public double getMonthlyFee() {
        return monthlyFee;
    }
}

// Main class to test the system
public class test14 {
    public static void main(String[] args) {
        SavingsAccount savings = new SavingsAccount(101, 1000.0, 0.05); 
        CheckingAccount checking = new CheckingAccount(102, 2000.0, 15.0);

        System.out.println("Savings Account #" + savings.getAccountNumber());
        System.out.println("Balance: $" + savings.getBalance());
        System.out.println("Interest: $" + savings.calculateInterest());

        System.out.println("\nChecking Account #" + checking.getAccountNumber());
        System.out.println("Balance: $" + checking.getBalance());
        System.out.println("Interest: $" + checking.calculateInterest());

        savings.deposit(500);
        checking.withdraw(1000);

        System.out.println("\nUpdated Savings Balance: $" + savings.getBalance());
        System.out.println("Updated Checking Balance: $" + checking.getBalance());
    }
}
