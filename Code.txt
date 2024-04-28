import java.util.ArrayList;
import java.util.Scanner;

public class studentgradetracker {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<Integer> grades = new ArrayList<>();

        System.out.println("Welcome to the Student Grade Tracker!");

        // Ask the user for the number of students
        System.out.print("Enter the number of students: ");
        int numStudents = scanner.nextInt();

        // Input loop to get grades for each student
        for (int i = 1; i <= numStudents; i++) {
            System.out.print("Enter the grade for student " + i + ": ");
            int grade = scanner.nextInt();
            grades.add(grade);
        }

        // Calculate average
        double average = calculateAverage(grades);

        // Find highest and lowest grades
        int highest = findHighest(grades);
        int lowest = findLowest(grades);

        // Display results
        System.out.println("\nResults:");
        System.out.println("Average Grade: " + average);
        System.out.println("Highest Grade: " + highest);
        System.out.println("Lowest Grade: " + lowest);

        scanner.close();
    }

    // Method to calculate average
    public static double calculateAverage(ArrayList<Integer> grades) {
        double sum = 0;
        for (int grade : grades) {
            sum += grade;
        }
        return sum / grades.size();
    }

    // Method to find highest grade
    public static int findHighest(ArrayList<Integer> grades) {
        int highest = Integer.MIN_VALUE;
        for (int grade : grades) {
            if (grade > highest) {
                highest = grade;
            }
        }
        return highest;
    }

    // Method to find lowest grade
    public static int findLowest(ArrayList<Integer> grades) {
        int lowest = Integer.MAX_VALUE;
        for (int grade : grades) {
            if (grade < lowest) {
                lowest = grade;
            }
        }
        return lowest;
    }
}

