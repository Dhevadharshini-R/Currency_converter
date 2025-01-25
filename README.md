
import java.util.Scanner;
import java.util.InputMismatchException;

public class CurrencyConverter {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.println("Currency Converter");
            System.out.println("1. USD to INR");
            System.out.println("2. INR to USD");
            System.out.println("3. EUR to USD");
            System.out.println("4. USD to EUR");
            System.out.print("Enter your choice: ");
            int choice = scanner.nextInt();

            System.out.print("Enter the amount: ");
            double amount = scanner.nextDouble();

            double result = 0;

            switch (choice) {
                case 1:
                    result = usdToInr(amount);
                    break;
                case 2:
                    result = inrToUsd(amount);
                    break;
                case 3:
                    result = eurToUsd(amount);
                    break;
                case 4:
                    result = usdToEur(amount);
                    break;
                default:
                    System.out.println("Invalid choice");
                    return;
            }

            System.out.println("Result: " + result);
        } catch (InputMismatchException e) {
            System.out.println("Invalid input. Please enter a valid number.");
        } finally {
            scanner.close();
        }
    }

    private static double usdToInr(double amount) {
        // 1 USD = 82.55 INR (approximate)
        return amount * 82.55;
    }

    private static double inrToUsd(double amount) {
        // 1 INR = 0.0121 USD (approximate)
        return amount * 0.0121;
    }

    private static double eurToUsd(double amount) {
        // 1 EUR = 1.12 USD (approximate)
        return amount * 1.12;
    }

    private static double usdToEur(double amount) {
        // 1 USD = 0.89 EUR (approximate)
        return amount * 0.89;
    }
}
