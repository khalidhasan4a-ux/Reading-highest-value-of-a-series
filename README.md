import java.io.File;
import java.io.PrintWriter;
import java.util.Scanner;

public class Lab2DataProcessor {

    public static void main(String[] args) throws Exception {

        Scanner fileScanner = new Scanner(new File("Input.txt"));
        fileScanner.useDelimiter("[,\\s]+");

        int highest = Integer.MIN_VALUE;
        int sum = 0;

        while (fileScanner.hasNextInt()) {

            int num = fileScanner.nextInt();

            sum += num;

            if (num > highest) {
                highest = num;
            }
        }

        fileScanner.close();

        PrintWriter pw = new PrintWriter("Output.txt");

        pw.println("Highest Value: " + highest);
        pw.println("Sum: " + sum);

        pw.close();

        System.out.println("Processing completed. Check Output.txt");
    }
}
