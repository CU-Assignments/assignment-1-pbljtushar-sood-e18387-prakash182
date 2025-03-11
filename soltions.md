// Problem 1: String Analysis
import java.util.Scanner;
```
class StringAnalyzer {
    public void analyzeString(String str) {
        int vowels = 0, consonants = 0, digits = 0, specialChars = 0;
        str = str.toLowerCase();
        
        for (char ch : str.toCharArray()) {
            if (Character.isDigit(ch)) {
                digits++;
            } else if (ch >= 'a' && ch <= 'z') {
                if ("aeiou".indexOf(ch) != -1) vowels++;
                else consonants++;
            } else if (!Character.isWhitespace(ch)) {
                specialChars++;
            }
        }
        
        System.out.println("Vowels: " + vowels);
        System.out.println("Consonants: " + consonants);
        System.out.println("Digits: " + digits);
        System.out.println("Special Characters: " + specialChars);
    }
}
```
// Problem 2: Matrix Operations
```
class MatrixOperations {
    public int[][] add(int[][] A, int[][] B) {
        int rows = A.length, cols = A[0].length;
        int[][] result = new int[rows][cols];
        for (int i = 0; i < rows; i++)
            for (int j = 0; j < cols; j++)
                result[i][j] = A[i][j] + B[i][j];
        return result;
    }
    
    public int[][] subtract(int[][] A, int[][] B) {
        int rows = A.length, cols = A[0].length;
        int[][] result = new int[rows][cols];
        for (int i = 0; i < rows; i++)
            for (int j = 0; j < cols; j++)
                result[i][j] = A[i][j] - B[i][j];
        return result;
    }
    
    public int[][] multiply(int[][] A, int[][] B) {
        int rows = A.length, cols = B[0].length, common = A[0].length;
        int[][] result = new int[rows][cols];
        for (int i = 0; i < rows; i++)
            for (int j = 0; j < cols; j++)
                for (int k = 0; k < common; k++)
                    result[i][j] += A[i][k] * B[k][j];
        return result;
    }
}
```
// Problem 3: Basic Banking System
```
class BankAccount {
    private String name;
    private String accountNumber;
    private double balance;
    
    public BankAccount(String name, String accountNumber, double initialBalance) {
        this.name = name;
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }
    
    public void deposit(double amount) {
        balance += amount;
        System.out.println("Deposit successful! Current Balance: " + balance);
    }
    
    public void withdraw(double amount) {
        if (amount > balance) {
            System.out.println("Error: Insufficient funds. Current Balance: " + balance);
        } else {
            balance -= amount;
            System.out.println("Withdrawal successful! Current Balance: " + balance);
        }
    }
    
    public double getBalance() {
        return balance;
    }
}
```