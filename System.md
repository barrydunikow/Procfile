using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        List<string> inventory = new List<string>();
        
        while (true)
        {
            Console.WriteLine("1. Add item");
            Console.WriteLine("2. View inventory");
            Console.WriteLine("3. Exit");
            string choice = Console.ReadLine();

            if (choice == "1")
            {
                Console.WriteLine("Enter item name:");
                string item = Console.ReadLine();
                inventory.Add(item);
            }
            else if (choice == "2")
            {
                Console.WriteLine("Inventory:");
                foreach (var item in inventory)
                {
                    Console.WriteLine($"- {item}");
                }
            }
            else if (choice == "3")
            {
                break;
            }
            else
            {
                Console.WriteLine("Invalid choice.");
            }
        }
    }
}
