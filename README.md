# java-2
package jobexams;

import java.util.HashMap;
import java.util.Scanner;
import java.util.Map;

public class RomanToInteger {
    public static void main(String[] args) {
    	Scanner scan=new Scanner(System.in);
        Map<Character, Integer> romanNumerals = new HashMap<>();
        romanNumerals.put('I', 1);
        romanNumerals.put('V', 5);
        romanNumerals.put('X', 10);
        romanNumerals.put('L', 50);
        romanNumerals.put('C', 100);
        romanNumerals.put('D', 500);
        romanNumerals.put('M', 1000);
        
        System.out.println("enter the roman number");
        String romanInput = scan.next(); // Replace with user input

        int result = 0;
        int prevValue = 0;

        for (int i = romanInput.length() - 1; i >= 0; i--) {
            int value = romanNumerals.get(romanInput.charAt(i));
            if (value < prevValue) {
                result -= value;
            } else {
                result += value;
            }
            prevValue = value;
        }

        System.out.println("The integer value is: " + result);
    }
}

