import java.util.ArrayList;
import java.util.Scanner;

public class StudentGradeAnalyzer {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // ArrayList to store marks
        ArrayList<Integer> marks = new ArrayList<>();

        System.out.print("Enter number of subjects: ");
        int n = sc.nextInt();

        // Input marks
        for (int i = 0; i < n; i++) {
            System.out.print("Enter mark for subject " + (i + 1) + ": ");
            marks.add(sc.nextInt());
        }

        // Calculate total, average, highest, lowest
        int total = 0;
        int highest = marks.get(0);
        int lowest = marks.get(0);

        for (int m : marks) {
            total += m;
            if (m > highest) highest = m;
            if (m < lowest) lowest = m;
        }

        double average = (double) total / n;

        // Grade calculation
        String grade;
        if (average >= 90) grade = "A+";
        else if (average >= 80) grade = "A";
        else if (average >= 70) grade = "B";
        else if (average >= 60) grade = "C";
        else if (average >= 50) grade = "D";
        else grade = "Fail";

        // Output results
        System.out.println("\n----- Student Grade Analysis -----");
        System.out.println("Marks: " + marks);
        System.out.println("Total Marks: " + total);
        System.out.println("Average: " + average);
        System.out.println("Highest Mark: " + highest);
        System.out.println("Lowest Mark: " + lowest);
        System.out.println("Final Grade: " + grade);
    }
}
