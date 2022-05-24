# Matrix-of-Palindromes
Write a program to generate the following matrix of palindromes of 3 letters with r rows and c columns like the one in the examples below.     • Rows define the first and the last letter: row 0 -> ‘a’, row 1 -> ‘b’, row 2 -> ‘c’, …     • Columns + rows define the middle letter:          ◦ column 0, row 0 -> ‘a’, column 1, row 0 -> ‘b’, column 2, row 0 -> ‘c’, …         ◦ column 0, row 1 -> ‘b’, column 1, row 1 -> ‘c’, column 2, row 1 -> ‘d’, …
package MultidimensionalArrays;

import java.util.Scanner;

public class P02MatrixofPalindromes {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String[] size = scanner.nextLine().split("\\s+");
        int rows = Integer.parseInt(size[0]);
        int cols = Integer.parseInt(size[1]);

        String[][] matrix = new String[rows][cols];

        fillInMatrixOfPalindromes(rows, cols, matrix);

        ptrintMatrix(rows, cols, matrix);
    }

    private static void ptrintMatrix(int rows, int cols, String[][] matrix) {
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }

    private static void fillInMatrixOfPalindromes(int rows, int cols, String[][] matrix) {
        char outer = 'a';
        for (int row = 0; row < rows; row++) {
            for (int col = 0; col < cols; col++) {
                char middle = (char) (outer + col);

                matrix[row][col] = String.valueOf(outer) + middle + outer;

            }
            outer = (char) (outer + 1);

        }
    }

}
