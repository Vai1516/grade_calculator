# grade_calculator
import java.util.Scanner;

public class GradeCalculator {
    public static void main(String[] args) {
        try (Scanner scanner = new Scanner(System.in)) {
            System.out.println("Welcome to the Student Grade Calculator!");

            System.out.print("Enter the number of subjects: ");
            int numSubjects = scanner.nextInt();

            int totalMarks = 0;
            double averagePercentage;

            for (int i = 1; i <= numSubjects; i++) {
                System.out.print("Enter marks obtained in subject " + i + ": ");
                int marks = scanner.nextInt();
                totalMarks += marks;
            }

            averagePercentage = (double) totalMarks / numSubjects;
            String grade = calculateGrade(averagePercentage);

            System.out.println("\nResults:");
            System.out.println("Total Marks: " + totalMarks);
            System.out.println("Average Percentage: " + averagePercentage + "%");
            System.out.println("Grade: " + grade);

            scanner.close();
        }
    }

    public static String calculateGrade(double percentage) {
        if (percentage >= 90) {
            return "A+";
        } else if (percentage >= 80) {
            return "A";
        } else if (percentage >= 70) {
            return "B";
        } else if (percentage >= 60) {
            return "C";
        } else if (percentage >= 50) {
            return "D";
        } else {
            return "F";
        }
    }
}
