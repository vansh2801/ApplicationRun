# ApplicationRun
java assignment -2


import java.util.Scanner;

class SmartCalculator {

    int sum(int x, int y) {
        return x + y;
    }

    double sum(double x, double y) {
        return x + y;
    }

    int difference(int x, int y) {
        return x - y;
    }

    double product(double x, double y) {
        return x * y;
    }

    int quotient(int x, int y) {
        if (y == 0) {
            System.out.println("Error: Cannot divide by zero.");
            return 0;
        }
        return x / y;
    }
}

class CalculatorUI extends SmartCalculator {
    Scanner input = new Scanner(System.in);

    void handleSum() {
        System.out.println("Choose operation type:");
        System.out.println("1. Integer Addition");
        System.out.println("2. Decimal Addition");
        int choice = input.nextInt();

        if (choice == 1) {
            System.out.print("Enter first integer: ");
            int x = input.nextInt();
            System.out.print("Enter second integer: ");
            int y = input.nextInt();
            int output = super.sum(x, y);
            System.out.println("Sum: " + output);
        } else if (choice == 2) {
            System.out.print("Enter first decimal number: ");
            double x = input.nextDouble();
            System.out.print("Enter second decimal number: ");
            double y = input.nextDouble();
            double output = super.sum(x, y);
            System.out.println("Sum: " + output);
        } else {
            System.out.println("Invalid choice for addition type.");
        }
    }

    void handleDifference() {
        System.out.print("Enter first number: ");
        int x = input.nextInt();
        System.out.print("Enter second number: ");
        int y = input.nextInt();
        int result = super.difference(x, y);
        System.out.println("Difference: " + result);
    }

    void handleProduct() {
        System.out.print("Enter first number: ");
        double x = input.nextDouble();
        System.out.print("Enter second number: ");
        double y = input.nextDouble();
        double result = super.product(x, y);
        System.out.println("Product: " + result);
    }

    void handleQuotient() {
        System.out.print("Enter dividend: ");
        int x = input.nextInt();
        System.out.print("Enter divisor: ");
        int y = input.nextInt();
        int result = super.quotient(x, y);
        if (y != 0) {
            System.out.println("Quotient: " + result);
        }
    }

    void startApp() {
        int choice;
        do {
            System.out.println("\n=== Welcome to Smart Calculator ===");
            System.out.println("1. Add Numbers");
            System.out.println("2. Subtract Numbers");
            System.out.println("3. Multiply Numbers");
            System.out.println("4. Divide Numbers");
            System.out.println("5. Exit");
            System.out.print("Enter your option: ");
            choice = input.nextInt();

            if (choice == 1) {
                handleSum();
            } else if (choice == 2) {
                handleDifference();
            } else if (choice == 3) {
                handleProduct();
            } else if (choice == 4) {
                handleQuotient();
            } else if (choice == 5) {
                System.out.println("Exiting... Goodbye! 👋");
            } else {
                System.out.println("Invalid Selection! Please try again.");
            }
        } while (choice != 5);
        
        input.close();
    }
}

public class ApplicationRun {
    public static void main(String[] args) {
        CalculatorUI calc = new CalculatorUI();
        calc.startApp();
    }
}
