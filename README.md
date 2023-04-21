import java.util.Scanner;

public class ElectionSystem {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        String[] candidates = {"Candidate A", "Candidate B", "Candidate C", "Candidate D"};
        int[] votes = new int[candidates.length];

        System.out.println("Welcome to the Online Election System!");
        System.out.println("Please select your option:");
        System.out.println("1. Vote");
        System.out.println("2. View Results");
        System.out.println("3. Exit");

        int choice = input.nextInt();

        while (choice != 3) {
            if (choice == 1) {
                System.out.println("Please select your candidate:");
                for (int i = 0; i < candidates.length; i++) {
                    System.out.println((i + 1) + ". " + candidates[i]);
                }
                int candidateChoice = input.nextInt();

                if (candidateChoice < 1 || candidateChoice > candidates.length) {
                    System.out.println("Invalid candidate choice. Please try again.");
                } else {
                    votes[candidateChoice - 1]++;
                    System.out.println("Thank you for voting!");
                }
            } else if (choice == 2) {
                System.out.println("Election Results:");
                for (int i = 0; i < candidates.length; i++) {
                    System.out.println(candidates[i] + ": " + votes[i] + " votes");
                }
            } else {
                System.out.println("Invalid option. Please try again.");
            }

            System.out.println("\nPlease select your option:");
            System.out.println("1. Vote");
            System.out.println("2. View Results");
            System.out.println("3. Exit");
            choice = input.nextInt();
        }

        System.out.println("Thank you for using the Online Election System!");
    }
}
