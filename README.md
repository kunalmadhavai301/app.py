Problem 1
Q: Write a program to input marks of students in 5 subjects, calculate total, 
average, and grade using methods and handle invalid marks using exception 
handling.
A:
import java.util.InputMismatchException;
import java.util.Scanner;
public class StudentMarksEasy {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 int marks[] = new int[5];
 int total = 0;
 double avg;
 char grade;
 try {
 for (int i = 0; i < 5; i++) {
 System.out.print("Enter marks of subject " + (i + 1) + ": ");
 marks[i] = sc.nextInt();
 if (marks[i] < 0 || marks[i] > 100) {
 throw new IllegalArgumentException("Invalid marks! Marks 
should be between 0 and 100.");
 }
 total += marks[i];
 }
 avg = total / 5.0;
 if (avg >= 90)
 grade = 'A';
 else if (avg >= 75)
 grade = 'B';
 else if (avg >= 60)
 grade = 'C';
 else if (avg >= 45)
 grade = 'D';
 else
 grade = 'F';
 System.out.println("\nTotal Marks = " + total);
 System.out.printf("Average = %.2f%n", avg);
 System.out.println("Grade = " + grade);
 } catch (InputMismatchException ime) {
 System.out.println(" Invalid input! Please enter numbers only.");
 } catch (Exception e) {
 System.out.println(" " + e.getMessage());
 } finally {
 sc.close();
 }
 }
}
🟩 Problem 2
Q: Accept item names, price, and quantity. Calculate total, apply a discount if 
total > 2000, and display formatted bill using methods.
A:
import java.util.InputMismatchException;
import java.util.Scanner;
public class SimpleBill {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 try {
 System.out.print("Enter item name: ");
 String item = sc.nextLine();
 System.out.print("Enter price: ");
 double price = sc.nextDouble();
 System.out.print("Enter quantity: ");
 int qty = sc.nextInt();
 double total = price * qty;
 double finalAmount = total > 2000 ? total - (total * 0.10) : total;
 System.out.println("\n----- BILL -----");
 System.out.println("Item Name : " + item);
 System.out.printf("Price : %.2f%n", price);
 System.out.println("Quantity : " + qty);
 System.out.printf("Total : %.2f%n", total);
 if (total > 2000) System.out.println("Discount : 10%");
 System.out.printf("Final Amount: %.2f%n", finalAmount);
 System.out.println("----------------");
 } catch (InputMismatchException e) {
 System.out.println(" Invalid input! Please enter numeric values for 
price and quantity.");
 } finally {
 sc.close();
 }
 }
}
🟩 Problem 3
Q: Take a sentence and count the number of words and occurrences of a 
specific word using arrays and string methods.
A:
import java.util.Scanner;
public class SimpleWordCount {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 System.out.print("Enter a sentence: ");
 String sentence = sc.nextLine();
 System.out.print("Enter a word to count: ");
 String search = sc.next();
 String[] words = sentence.trim().split("\\s+");
 int totalWords = (sentence.trim().isEmpty()) ? 0 : words.length;
 int count = 0;
 for (String w : words) {
 if (w.equalsIgnoreCase(search)) count++;
 }
 System.out.println("\nTotal words: " + totalWords);
 System.out.println("Occurrences of \"" + search + "\": " + count);
 sc.close();
 }
}
🟩 Problem 4
Q: Check password strength: Length ≥ 8, contains uppercase, lowercase, digit, 
and symbol. Throw an exception if invalid.
A:
import java.util.Scanner;
public class EasyPasswordCheck {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 System.out.print("Enter your password: ");
 String pwd = sc.nextLine();
 try {
 if (pwd.length() < 8)
 throw new Exception("Password must be at least 8 characters long.");
 if (!pwd.matches(".*[A-Z].*"))
 throw new Exception("Password must contain at least one uppercase 
letter.");
 if (!pwd.matches(".*[a-z].*"))
 throw new Exception("Password must contain at least one lowercase 
letter.");
 if (!pwd.matches(".*[0-9].*"))
 throw new Exception("Password must contain at least one digit.");
 if (!pwd.matches(".*[@#$%^&+=!].*"))
 throw new Exception("Password must contain at least one symbol 
(@,#,$,%,^,&,+,=,!).");
 System.out.println(" Password is strong.");
 } catch (Exception e) {
 System.out.println(" " + e.getMessage());
 } finally {
 sc.close();
 }
 }
}
🟩 Problem 5
Q: Simulate ATM operations like deposit, withdraw, and check balance. Use 
methods for each operation and handle insufficient balance with exception 
handling.
A:import java.util.InputMismatchException;
import java.util.Scanner;
public class VeryEasyATM {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 double balance = 0;
 while (true) {
 System.out.println("\n--- ATM MENU ---");
 System.out.println("1. Deposit");
 System.out.println("2. Withdraw");
 System.out.println("3. Check Balance");
 System.out.println("4. Exit");
 System.out.print("Enter your choice: ");
 try {
 int choice = sc.nextInt();
 if (choice == 1) {
 System.out.print("Enter amount to deposit: ");
 double amt = sc.nextDouble();
 if (amt > 0) {
 balance += amt;
 System.out.printf(" Deposited: %.2f%n", amt);
 } else System.out.println(" Invalid amount!");
 } else if (choice == 2) {
 System.out.print("Enter amount to withdraw: ");
 double amt = sc.nextDouble();
 if (amt <= 0) System.out.println(" Invalid amount!");
 else if (amt > balance) System.out.println(" Insufficient 
balance!");
 else {
 balance -= amt;
 System.out.printf(" Withdrawn: %.2f%n", amt);
 }
 } else if (choice == 3) {
 System.out.printf(" Current Balance: %.2f%n", balance);
 } else if (choice == 4) {
 System.out.println("Thank you for using the ATM! ");
 break;
 } else System.out.println(" Invalid choice!");
 } catch (InputMismatchException e) {
 System.out.println(" Invalid input! Please enter numbers only.");
 sc.nextLine();
 }
 }
 sc.close();
 }
}
🟩 Problem 6
Q: Accept basic salary and compute HRA, DA, PF, and gross salary. Display 
results using methods and handle invalid inputs with exceptions.
A:
import java.util.InputMismatchException;
import java.util.Scanner;
public class EasySalaryCalculator {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 try {
 System.out.print("Enter basic salary: ");
 double basic = sc.nextDouble();
 if (basic < 0) {
 System.out.println(" Salary cannot be negative!");
 return;
 }
 double HRA = basic * 0.10;
 double DA = basic * 0.08;
 double PF = basic * 0.05;
 double gross = basic + HRA + DA - PF;
 System.out.println("\n--- Salary Details ---");
 System.out.printf("Basic Salary : %.2f%n", basic);
 System.out.printf("HRA (10%%) : %.2f%n", HRA);
 System.out.printf("DA (8%%) : %.2f%n", DA);
 System.out.printf("PF (5%%) : %.2f%n", PF);
 System.out.printf("Gross Salary : %.2f%n", gross);
 } catch (InputMismatchException e) {
 System.out.println(" Invalid input! Please enter a valid number.");
 } finally {
 sc.close();
 }
 }
}
🟩 Problem 7
Q: Accept total bill and membership type (Silver/Gold/Platinum) and apply 
discounts accordingly using if-else and methods.
A:
import java.util.InputMismatchException;
import java.util.Scanner;
public class EasyMembershipDiscount {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 try {
 System.out.print("Enter total bill amount: ");
 double total = sc.nextDouble();
 sc.nextLine();
 System.out.print("Enter membership type (Silver/Gold/Platinum): ");
 String membership = sc.nextLine();
 double finalAmount = total;
 if (membership.equalsIgnoreCase("Silver"))
 finalAmount -= total * 0.05;
 else if (membership.equalsIgnoreCase("Gold"))
 finalAmount -= total * 0.10;
 else if (membership.equalsIgnoreCase("Platinum"))
 finalAmount -= total * 0.15;
 else System.out.println(" Invalid membership! No discount 
applied.");
 System.out.printf("%nTotal Bill : %.2f%n", total);
 System.out.println("Membership Type : " + membership);
 System.out.printf("Final Amount : %.2f%n", finalAmount);
 } catch (InputMismatchException e) {
 System.out.println(" Invalid input! Please enter numeric values.");
 } finally {
 sc.close();
 }
 }
}
🟩 Problem 8
Q: For ‘n’ products, store product name, price, and quantity in arrays. Calculate 
total stock value and handle out-of-stock errors via exception handling.
A:
import java.util.InputMismatchException;
import java.util.Scanner;
public class SuperEasyProductStock {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 try {
 System.out.print("Enter number of products: ");
 int n = sc.nextInt();
 if (n <= 0) {
 System.out.println(" Number of products must be positive!");
 return;
 }
 double totalStockValue = 0;
 for (int i = 1; i <= n; i++) {
 System.out.println("\nProduct " + i + ":");
 System.out.print("Enter product name: ");
 String name = sc.next();
 System.out.print("Enter price: ");
 double price = sc.nextDouble();
 System.out.print("Enter quantity: ");
 int qty = sc.nextInt();
 if (qty <= 0) {
 System.out.println(" Product " + name + " is out of stock!");
 } else {
 totalStockValue += price * qty;
 }
 }
 System.out.printf("%nTotal Stock Value: %.2f%n", totalStockValue);
 } catch (InputMismatchException e) {
 System.out.println(" Invalid input! Please enter numbers correctly.");
 } finally {
 sc.close();
 }
 }
}
Problem 1
Q: Process a coffee order: take customer size choice, calculate total price based 
on size and add-ons, and handle a list of 5 drink types.
A:
import java.util.InputMismatchException;
import java.util.Scanner;
public class CoffeeOrder {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 String[] drinks = {"Espresso", "Latte", "Cappuccino", "Mocha", 
"Americano"};
 double[] prices = {120, 150, 160, 170, 140};
 try {
 System.out.println("Available Drinks:");
 for (int i = 0; i < drinks.length; i++) {
 System.out.println((i + 1) + ". " + drinks[i] + " - ₹" + prices[i]);
 }
 System.out.print("Choose your drink (1-5): ");
 int choice = sc.nextInt();
 if (choice < 1 || choice > 5)
 throw new Exception("Invalid drink selection!");
 System.out.print("Select size (S/M/L): ");
 char size = sc.next().toUpperCase().charAt(0);
 double sizeCost = switch (size) {
 case 'S' -> 0;
 case 'M' -> 20;
 case 'L' -> 40;
 default -> throw new Exception("Invalid size choice!");
 };
 System.out.print("Add whipped cream? (yes/no): ");
 String cream = sc.next();
 double addOn = cream.equalsIgnoreCase("yes") ? 15 : 0;
 double total = prices[choice - 1] + sizeCost + addOn;
 System.out.printf("%n Order 
Summary:%nDrink: %s%nSize: %c%nAdd-on: %s%nTotal Price: ₹%.2f%n",
 drinks[choice - 1], size, cream, total);
 } catch (InputMismatchException e) {
 System.out.println(" Enter numbers only for choices!");
 } catch (Exception e) {
 System.out.println(" " + e.getMessage());
 } finally {
 sc.close();
 }
 }
}
🟩 Problem 2
Q: Create a method that accepts two numbers and an operation symbol. Use a 
switch to perform addition, subtraction, multiplication, or division.
A:
import java.util.Scanner;
public class SimpleCalculator {
 static double calculate(double a, double b, char op) {
 return switch (op) {
 case '+' -> a + b;
 case '-' -> a - b;
 case '*' -> a * b;
 case '/' -> (b != 0) ? a / b : Double.NaN;
 default -> Double.NaN;
 };
 }
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 System.out.print("Enter first number: ");
 double n1 = sc.nextDouble();
 System.out.print("Enter second number: ");
 double n2 = sc.nextDouble();
 System.out.print("Enter operation (+,-,*,/): ");
 char op = sc.next().charAt(0);
 double result = calculate(n1, n2, op);
 if (Double.isNaN(result))
 System.out.println(" Invalid operation!");
 else
 System.out.println(" Result: " + result);
 sc.close();
 }
}
🟩 Problem 3
Q: Input a string and count vowels, consonants, digits, and special characters 
using loops and conditionals.
A:
import java.util.Scanner;
public class CountCharacters {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 System.out.print("Enter a string: ");
 String str = sc.nextLine();
 int vowels = 0, consonants = 0, digits = 0, special = 0;
 for (char ch : str.toCharArray()) {
 if (Character.isLetter(ch)) {
 ch = Character.toLowerCase(ch);
 if ("aeiou".indexOf(ch) != -1)
 vowels++;
 else
 consonants++;
 } else if (Character.isDigit(ch))
 digits++;
 else if (!Character.isWhitespace(ch))
 special++;
 }
 System.out.println("Vowels: " + vowels);
 System.out.println("Consonants: " + consonants);
 System.out.println("Digits: " + digits);
 System.out.println("Special Characters: " + special);
 sc.close();
 }
}
🟩 Problem 4
Q: For n customers, input name, account type, and balance. Apply 4 % interest 
for savings and 6 % for fixed accounts, then display updated balances.
A:
import java.util.Scanner;
public class BankInterest {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 System.out.print("Enter number of customers: ");
 int n = sc.nextInt();
 sc.nextLine();
 for (int i = 1; i <= n; i++) {
 System.out.println("\nCustomer " + i + ":");
 System.out.print("Enter name: ");
 String name = sc.nextLine();
 System.out.print("Enter account type (Savings/Fixed): ");
 String type = sc.nextLine();
 System.out.print("Enter balance: ");
 double bal = sc.nextDouble();
 sc.nextLine();
 double rate = type.equalsIgnoreCase("Savings") ? 0.04 :
 type.equalsIgnoreCase("Fixed") ? 0.06 : 0;
 if (rate == 0)
 System.out.println(" Invalid account type!");
 else {
 bal += bal * rate;
 System.out.printf(" %s new balance: ₹%.2f%n", name, bal);
 }
 }
 sc.close();
 }
}
🟩 Problem 5
Q: Read 5 daily temperatures into an array. Use a loop and a method to convert 
each from Celsius to Fahrenheit, displaying both.
A:
import java.util.Scanner;
public class TempConverter {
 static double toFahrenheit(double c) {
 return (c * 9 / 5) + 32;
 }
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 double[] tempC = new double[5];
 for (int i = 0; i < 5; i++) {
 System.out.print("Enter temperature " + (i + 1) + " in °C: ");
 tempC[i] = sc.nextDouble();
 }
 System.out.println("\nCelsius\t→\tFahrenheit");
 for (double c : tempC)
 System.out.printf("%.2f°C\t→\t%.2f°F%n", c, toFahrenheit(c));
 sc.close();
 }
}
🟩 Problem 6
Q: Accept number of units consumed and calculate bill based on slab rates 
using conditionals and methods.
A:
import java.util.Scanner;
public class ElectricityBill {
 static double calcBill(int units) {
 double bill;
 if (units <= 100)
 bill = units * 1.5;
 else if (units <= 300)
 bill = (100 * 1.5) + (units - 100) * 2;
 else
 bill = (100 * 1.5) + (200 * 2) + (units - 300) * 3;
 return bill;
 }
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 System.out.print("Enter units consumed: ");
 int units = sc.nextInt();
 System.out.printf("Total Bill: ₹%.2f%n", calcBill(units));
 sc.close();
 }
}
🟩 Problem 7
Q: Input a string and check if it’s a palindrome (ignore case and spaces). Use 
string methods and exception handling.
A:
import java.util.Scanner;
public class PalindromeCheck {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 try {
 System.out.print("Enter a string: ");
 String str = sc.nextLine().replaceAll("\\s+", "").toLowerCase();
 String rev = new StringBuilder(str).reverse().toString();
 if (str.equals(rev))
 System.out.println(" Palindrome!");
 else
 System.out.println(" Not a palindrome.");
 } catch (Exception e) {
 System.out.println("Error: " + e.getMessage());
 } finally {
 sc.close();
 }
 }
}
🟩 Problem 8
Q: Read a word. Use a loop and a switch on each character to replace 'a' → '4', 
'e' → '3', 'o' → '0'.
A:
import java.util.Scanner;
public class ReplaceChars {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 System.out.print("Enter a word: ");
 String word = sc.nextLine().toLowerCase();
 StringBuilder newWord = new StringBuilder();
 for (char ch : word.toCharArray()) {
 switch (ch) {
 case 'a' -> newWord.append('4');
 case 'e' -> newWord.append('3');
 case 'o' -> newWord.append('0');
 default -> newWord.append(ch);
 }
 }
 System.out.println("Converted Word: " + newWord);
 sc.close();
 }
}
