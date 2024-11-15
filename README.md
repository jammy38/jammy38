using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Welcome to the Multiplication Table Generator!");
        
        string userChoice = "yes";

        while (userChoice.ToLower() == "yes")
        {
            Console.Write("\nEnter the number for which you want the multiplication table: ");
            if (int.TryParse(Console.ReadLine(), out int number))
            {
                Console.Write("Enter the limit (up to which multiple you want): ");
                if (int.TryParse(Console.ReadLine(), out int limit))
                {
                    Console.WriteLine($"\nMultiplication Table for {number} up to {limit}:");
                    
                    int multiplier = 1;
                    while (multiplier <= limit)
                    {
                        Console.WriteLine($"{number} x {multiplier} = {number * multiplier}");
                        multiplier++;
                    }
                }
                else
                {
                    Console.WriteLine("Invalid input for the limit. Please enter a valid number.");
                }
            }
            else
            {
                Console.WriteLine("Invalid input. Please enter a valid number.");
            }

            Console.Write("\nDo you want to generate another multiplication table? (yes/no): ");
            userChoice = Console.ReadLine();
        }

        Console.WriteLine("\nThank you for using the Multiplication Table Generator!");
    }
}
