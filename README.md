import java.util.Scanner;

public class MultiFunctionProgram {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        int choice;
        do {
            System.out.println("Select a function to perform: \n");
            System.out.println("1. Check for palindrome number: \n");
            System.out.println("2. Print pattern of stars: \n");
            System.out.println("3. Check whether a number is prime: \n");
            System.out.println("4. Print Fibonacci series: \n");
            System.out.println("0. Exit \n");
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();
            
            switch (choice) {
                case 1:
                    System.out.print("Enter a number: ");
                    int num1 = scanner.nextInt();
                    if (isPalindrome(num1)) {
                        System.out.println(num1 + " is a palindrome number.");
                    } else {
                        System.out.println(num1 + " is not a palindrome number.");
                    }
                    break;
                case 2:
                    System.out.print("Enter the number of levels: ");
                    int levels = scanner.nextInt();
                    printPattern(levels);
                    break;
                case 3:
                    System.out.print("Enter a number: ");
                    int num2 = scanner.nextInt();
                    if (isPrime(num2)) {
                        System.out.println(num2 + " is a prime number.");
                    } else {
                        System.out.println(num2 + " is not a prime number.");
                    }
                    break;
                case 4:
                    System.out.print("Enter the size of Fibonacci series: ");
                    int size = scanner.nextInt();
                    printFibonacciSeries(size);
                    break;
                case 0:
                    System.out.println("Exiting the program.");
                    break;
                default:
                    System.out.println("Invalid choice. Please select a valid option.");
            }
            
        } while (choice != 0);
    }
    
    public static boolean isPalindrome(int num) {
        int original = num;
        int reversed = 0;
        
        while (num != 0) {
            int digit = num % 10;
            reversed = reversed * 10 + digit;
            num /= 10;
        }
        
        return original == reversed;
    }
    
    public static void printPattern(int levels) {
        for (int i = levels; i >= 1; i--) {
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
    
    public static boolean isPrime(int num) {
        if (num <= 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }
    
    public static void printFibonacciSeries(int size) {
        int first = 0, second = 1;
        System.out.print(first + " " + second + " ");
        for (int i = 2; i < size; i++) {
            int next = first + second;
            System.out.print(next + " ");
            first = second;
            second = next;
        }
        System.out.println();
    }
}
