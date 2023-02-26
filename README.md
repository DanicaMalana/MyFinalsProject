# MyFinalsProject

using System;
using System.Collections.Generic;

namespace program
{
    internal class Program
    {
        static List<string> registeredPersons = new List<string>() { "Dan_Ams", "Nica_Hermosa", "Ica_Gomez" }; //camelCasing
        
        static void Main(string[] args)
        {
			// DANICA M. MALANA
            // THE EVENTS INFORMATION SYSTEM
			Console.WriteLine("\n\nMABUHAY KA BIÑANENSE!");

            Console.WriteLine("\n\nThrough this program you will see the dates of fiesta in all barangays that covered by Biñan City Of Laguna");
            Console.WriteLine("But please kindly input your Name or Full Name to access this application!");
            Console.WriteLine("*********************************************************************************************************************\n");

            ShowMainMenu(); //This is the method call

            string userInput = GetUserInput();

            while (userInput != "x") //looping statement 
            {
                switch (userInput) //conditional statement

                {

                    case "1":
                        RegisterPerson();
                        ShowMainMenu();
                        userInput = GetUserInput();
                        break;

                    case "2":
					    // This part is for Login Part to access the application
                        Console.WriteLine("\n_________LOGIN PART__________");

                        Console.Write("Enter your Name or Full name to see the dates of fiesta in all barangays that covered by Biñan City of Laguna: ");
                        var person = Console.ReadLine();

                        if (IsPersonExists(person))
                        {
                            Console.WriteLine("\nWELCOME TO THE SYSTEM!\n");

              // For the List of Dates of Feast in all barangays that covered by Biñan City Of Laguna
              ShowListOfDates(); 
                            
                            ShowMainMenu();
                            userInput = GetUserInput();
                        }
                        else
                        {
                            Console.WriteLine("\nThis Name is invalid, please try again or proceed to registration part if you're not already registered!\n");

                            ShowMainMenu();
                            userInput = GetUserInput();
                        }
                        break;

                    case "3":
                        Console.WriteLine("\n________________ADDING EVENTS INFORMATION________________");

                        Console.WriteLine("\n\nFOLLOWING ARE SOME EXAMPLES OF EVENTS THAT YOU CAN ADD.");
                        Console.WriteLine("\n- Tupad Program");
                        Console.WriteLine("- Sangguniang Kabataan City Wide Clean Up Drive");
                        Console.WriteLine("- Mr. & Ms. Biñan Events");
                        Console.WriteLine("- Inter-High Sports Tournament");
                        Console.WriteLine("- Puto Latik Festival");


                    // This is for the Users input for Adding Events Information
                        Console.WriteLine("\n\nTake note: If you are adding some events information, make sure that event is covered by the Biñan City Of Laguna only and you can also include the Date, Place and Time.");
                        Console.WriteLine("(Example: On the 15th of May the Biñan City Of Laguna will start celebrating the Puto Latik Festival in Biñan Plaza at 08:00 am)");
                        Console.Write("\n\nWhats your Additional Events information: ");
                        string comments = Console.ReadLine();
                        Console.WriteLine("\n\nTHIS IS THE LIST'S OF DATE'S OF THE FEAST DAY IN ALL BARANGAY THAT COVERED BY BIÑAN CITY OF LAGUNA");

                        Console.WriteLine("\nThe day of the feast on Brgy, Biñan is on May 16");
                        Console.WriteLine("The day of the feast on Brgy, Bungahan is on May 14");
                        Console.WriteLine("The day of the feast on Brgy, Canlalay is on October 6");
                        Console.WriteLine("The day of the feast on Brgy, Casile is on February 11");
                        Console.WriteLine("The day of the feast on Brgy, De Lapaz is on January 24");
                        Console.WriteLine("The day of the feast on Brgy, Ganado is on January 19");
                        Console.WriteLine("The day of the feast on Brgy, Mamplasan is on September 29");
                        Console.WriteLine("The day of the feast on Brgy, Malaban is on August 01");
                        Console.WriteLine("The day of the feast on Brgy, Malamig is on February 11");
                        Console.WriteLine("The day of the feast on Brgy, Langkiwa is on August 28");
                        Console.WriteLine("The day of the feast on Brgy, Loma is on December 08");
                        Console.WriteLine("The day of the feast on Brgy, Platero is on August 16");
                        Console.WriteLine("The day of the feast on Brgy, Poblacion is on May 15");
                        Console.WriteLine("The day of the feast on Brgy, San Antonio is on June 13");
                        Console.WriteLine("The day of the feast on Brgy, San Francisco is on October 4");
                        Console.WriteLine("The day of the feast on Brgy, San Jose is on March 19");
                        Console.WriteLine("The day of the feast on Brgy, San Vicente is on April 05");
                        Console.WriteLine("The day of the feast on Brgy, Santo Domingo is on August 08");
                        Console.WriteLine("The day of the feast on Brgy, Santo Niño is on January 31");
                        Console.WriteLine("The day of the feast on Brgy, Santo Tomas is on March 07");
                        Console.WriteLine("The day of the feast on Brgy, Soro-Soro is on January 17");
                        Console.WriteLine("The day of the feast on Brgy, Timbao is on August 16");
                        Console.WriteLine("The day of the feast on Brgy, Tubigan is on September 28");
                        Console.WriteLine("The day of the feast on Brgy, Zapote is on February 26");
                        Console.WriteLine("\nYour Additional Events information is: " + comments);

                        Console.WriteLine("\n\nTHANK YOU FOR ADDING SOME INFORMATION KABIÑENSE!\n");
                        Console.WriteLine("------------------------------------------------------------------------------------------------");
                        Console.WriteLine("\nSelect Enter to Continue...\n");
                        Console.ReadLine();
                        ShowMainMenu();
                        userInput = GetUserInput();
                        break;

                    case "4":
                        Console.WriteLine("\n_________REMOVE ACCOUNT__________");
                        Console.Write("Enter your Name or Full name to be removed: ");
                        var personRemove = Console.ReadLine();

                        if (IsPersonExists(personRemove))
                        {
                            registeredPersons.Remove(personRemove);
                            Console.WriteLine("\nSuccessfully removed the account!\n");
                            Console.WriteLine("\nTHANK YOU !\n\n");

                            ShowMainMenu();

                            userInput = GetUserInput();
                        }
                        else
                        {
                            Console.WriteLine("\nThis Name is invalid, please try again!\n\n");

                            ShowMainMenu();

                            userInput = GetUserInput();
                        }
                        break;
                    default:
                        break;
                }
            }
        }

        static void ShowMainMenu() //method signature
        {
            Console.WriteLine("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ MAIN MENU ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n\n");
            
            Console.WriteLine("Enter 1 to Input your Name or Full Name (ex. Dan or Crisostomo_Ibarra)");
            Console.WriteLine("Enter 2 to Login (if you already input your Name or Full Name)");
            Console.WriteLine("Enter 3 if you want to add some events information that covered by Biñan City Of Laguna");
            Console.WriteLine("Enter 4 to Remove your account (if you already input your Full Name)");
            Console.WriteLine("Enter x to exit application");
            Console.WriteLine("_______________________________________________________________________");
        }

        static string GetUserInput() //method signature
        {
            Console.Write("User input: ");
            string input = Console.ReadLine();

            //return statement
            return input;
        }
    
    static void ShowListOfDates()
    {
        
      Console.WriteLine("THIS IS THE LIST'S OF DATE'S OF THE FEAST DAY IN ALL BARANGAY THAT COVERED BY BIÑAN CITY OF LAGUNA\n");
	  
                            Console.WriteLine("The day of the feast on Brgy, Biñan is on May 16");
                            Console.WriteLine("The day of the feast on Brgy, Bungahan is on May 14");
                            Console.WriteLine("The day of the feast on Brgy, Canlalay is on October 6");
                            Console.WriteLine("The day of the feast on Brgy, Casile is on February 11");
                            Console.WriteLine("The day of the feast on Brgy, De Lapaz is on January 24");
                            Console.WriteLine("The day of the feast on Brgy, Ganado is on January 19");
                            Console.WriteLine("The day of the feast on Brgy, Mamplasan is on September 29");
                            Console.WriteLine("The day of the feast on Brgy, Malaban is on August 01");
                            Console.WriteLine("The day of the feast on Brgy, Malamig is on February 11");
                            Console.WriteLine("The day of the feast on Brgy, Langkiwa is on August 28");
                            Console.WriteLine("The day of the feast on Brgy, Loma is on December 08");
                            Console.WriteLine("The day of the feast on Brgy, Platero is on August 16");
                            Console.WriteLine("The day of the feast on Brgy, Poblacion is on May 15");
                            Console.WriteLine("The day of the feast on Brgy, San Antonio is on June 13");
                            Console.WriteLine("The day of the feast on Brgy, San Francisco is on October 4");
                            Console.WriteLine("The day of the feast on Brgy, San Jose is on March 19");
                            Console.WriteLine("The day of the feast on Brgy, San Vicente is on April 05");
                            Console.WriteLine("The day of the feast on Brgy, Santo Domingo is on August 08");
                            Console.WriteLine("The day of the feast on Brgy, Santo Niño is on January 31");
                            Console.WriteLine("The day of the feast on Brgy, Santo Tomas is on March 07");
                            Console.WriteLine("The day of the feast on Brgy, Soro-Soro is on January 17");
                            Console.WriteLine("The day of the feast on Brgy, Timbao is on August 16");
                            Console.WriteLine("The day of the feast on Brgy, Tubigan is on September 28");
                            Console.WriteLine("The day of the feast on Brgy, Zapote is on February 26");
    }

        static bool IsPersonExists(string personNumber) //parameters
        {
            int found = registeredPersons.IndexOf(personNumber);

            if (found == -1)
            {
                return false;
            }
            else
            {
                return true;
            }
        }

        static void RegisterPerson()
        {

            Console.WriteLine("\n_________REGISTRATION PART__________");
            Console.Write("Your Name or Full Name please (ex. Dan or Crisostomo_Ibarra): ");
            registeredPersons.Add(Console.ReadLine());
            Console.WriteLine("\nThank you for inputting your Name! ");
            Console.WriteLine("\n\nKindly proceed to Login part\n");

        }
    }
}
