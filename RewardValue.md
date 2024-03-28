# RewardValue
 java.util.Scanner;

public class RewardsConverter {
    
     public static class Rewards_Value {
        private double cashValue;
        private double milesValue;

        // Constructor
        public Rewards_Value(double cashValue) {
            this.cashValue = cashValue;
            // Assuming a conversion rate; for example, 1 dollar = 1.5 miles
            this.milesValue = convertCashToMiles(cashValue);
        }

        private double convertCashToMiles(double cash) {
            // Define the conversion logic here
            double conversionRate = 1.5;
            return cash * conversionRate;
        }

        // Method to get miles value
        public double getMilesValue() {
            return this.milesValue;
        }

        // Optionally, if you need to retrieve the cash value as well
        public double getCashValue() {
            return this.cashValue;
        }
    }

    public static void main(String[] args) {
        var scanner = new Scanner(System.in);
        System.out.println("Welcome to the Credit Card Rewards Converter!");
        System.out.println("Please enter a cash value to convert to airline miles: ");
        var input_value = scanner.nextLine();
        double cashValue;
        try {
            cashValue = Double.parseDouble(input_value);
        } catch (NumberFormatException exception) {
            System.out.println("Could not parse input value as a double, exiting");
            return;
        }
        System.out.println("converting $" + input_value + " to miles");
        var rewardsValue = new Rewards_Value(cashValue);
        System.out.println("$" + input_value + " is worth " + rewardsValue.getMilesValue() + " miles");
    }
}
