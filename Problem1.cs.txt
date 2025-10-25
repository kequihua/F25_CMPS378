/*
 * Author: Kimberly Equihua
 * Course: CMPS 378 – C# Programming, Fall 2025
 * Problem 1: Freelance Project Income Tracker
 * 
 * Description:
 * This program allows a freelancer to input their project details,
 * including the project name, hours worked, and hourly rate.
 * It calculates total income, average income, and identifies the
 * highest-earning project. The program demonstrates variables,
 * loops, conditional logic, and formatted output.
 */

using System;

namespace FreelanceProjectIncomeTracker
{
    class Program
    {
        static void Main(string[] args)
        {
            

            // Display welcome message
            Console.WriteLine("****** Welcome to Freelance Project Income Tracker ******\n");

            // Step 1: Ask for user information
            Console.Write("Enter your name: ");
            string name = Console.ReadLine(); // store user's name

            Console.Write("How many projects would you like to enter? ");
            int projectCount = int.Parse(Console.ReadLine()); // convert input to integer

            // Initialize variables to track totals and highest income project
            double totalIncome = 0.0;
            double highestIncome = 0.0;
            string highestProject = "";

            // Step 2: Loop through each project entry
            for (int i = 1; i <= projectCount; i++)
            {
                Console.WriteLine($"\nProject #{i}:");

                // Prompt for project details
                Console.Write("Enter project name: ");
                string projectName = Console.ReadLine();

                Console.Write("Enter hours worked: ");
                double hours = double.Parse(Console.ReadLine()); // convert string to double

                Console.Write("Enter hourly rate: ");
                double rate = double.Parse(Console.ReadLine()); // convert string to double

                // Calculate income for this project
                double projectIncome = hours * rate;

                // Add this project’s income to the total
                totalIncome += projectIncome;

                // Check if this project earned the most
                if (projectIncome > highestIncome)
                {
                    highestIncome = projectIncome;
                    highestProject = projectName;
                }
            }

            // Step 3: Calculate average income
            double averageIncome = totalIncome / projectCount;

            // Step 4: Display final summary output
            Console.WriteLine("\n========== FREELANCE INCOME SUMMARY ==========");
            Console.WriteLine($"Freelancer Name: {name}");
            Console.WriteLine($"Projects Logged: {projectCount}");
            Console.WriteLine($"Total Income: ${totalIncome:F2}");
            Console.WriteLine($"Average Project Income: ${averageIncome:F2}");
            Console.WriteLine($"Highest-Earning Project: {highestProject} (${highestIncome:F2})");
            Console.WriteLine("==============================================");
            Console.WriteLine("Thank you for using the Income Tracker!");
        }
    }
}

