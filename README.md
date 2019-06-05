# Assignment2
Triangle
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp11
{
	class Program
	{
		// this code has been taken from assignment 1 of Software Testing Methodologies dated 29th May 2019 and from AwesomeCalculator
		public static int ValidationMenuSelection()
		{
			string userInput = "";
			bool validMenuSelect = false;


/*			while (validMenuSelect == false)
			{
				Console.WriteLine("1 = Enter the Dimensions for the Triangle ");
				Console.WriteLine("2 = Exit\n");

				userInput = Console.ReadLine();

				if (userInput != "1" &&
					userInput != "2")
				{
					Console.WriteLine("Please Try again, as it is not a valid menu option: \n");
				}
				else
				{
					validMenuSelect = true;
				}
			}
*/			Console.WriteLine();
			return int.Parse(userInput);
		}

		public static int ValidateUserInput(string TriangleSide)
		{
			int number = 1;
			bool isValid = false;

			while (isValid == false)
			{
				Console.WriteLine($"Please enter the {TriangleSide} of the Triangle :");
				string userInput = Console.ReadLine();
				Console.WriteLine();
				bool result = int.TryParse(userInput, out number);
				if (result == false)
				{
					Console.WriteLine("Please try again, as it is not a valid input.\n");
				}
				else if (number <= 0)
				{
					Console.WriteLine("Number need to be greater than zero");
				}
				else if (number > 0)
				{
					isValid = true;
				}
			}
			return number;
		}


		static void Main(string[] args)
		{
			Program p = new Program();
			p.TriSides();
			Console.ReadKey();
		}
		/*TriangleSolver t = new TriangleSolver();


		Console.ReadKey();
		selection = ValidationMenuSelection();
		TriangleSolver.Analyse(int sideone, int sidetwo, int sidethree);
		*/

		public void TriSides()
		{
			bool validTriangleSelect = false;
			string TriangleSelection;


			while (validTriangleSelect == false)
			{
				do
				{
					Console.WriteLine("1 = Enter the Dimensions for the Triangle ");
					Console.WriteLine("2 = Exit\n");

					TriangleSelection = Console.ReadLine();
					Console.WriteLine();

					if (TriangleSelection != "1" && TriangleSelection != "2")
					{
						Console.WriteLine(" Please try again, as it is not a valid selection.\n");
					}
					else if (int.Parse(TriangleSelection) == 1)
					{
						validTriangleSelect = true;
						//Random random = new Random();
						int sideone;
						int sidetwo;
						int sidethree;

						sideone = ValidateUserInput("First Side");
						sidetwo = ValidateUserInput("Second Side");
						sidethree = ValidateUserInput("Third Side");

						Console.WriteLine($"Your default  first side is {sideone} and second side is {sidetwo} and third side is {sidethree}.\n");
						Console.WriteLine(TriangleSolver.Analyse(sideone, sidetwo, sidethree));
						TriangleSolver customTri = new TriangleSolver(sideone, sidetwo, sidethree);
						//p = customTri;

					}
					else if (int.Parse(TriangleSelection) == 2)
					{
						validTriangleSelect = true;

						int sideone;
						int sidetwo;
						int sidethree;

						sideone = ValidateUserInput("sideone");
						sidetwo = ValidateUserInput("sidetwo");
						sidethree = ValidateUserInput("sidethree");


						Console.WriteLine($"Triangle's custom first side is {sideone} and second side is {sidetwo} and third side{sidethree}.\n");
						TriangleSolver customTri = new TriangleSolver(sideone, sidetwo, sidethree);
						//p = customTri;
					}
					
					{



						int selection;
						selection = ValidationMenuSelection();
						{
							if (selection != 2)
							{
								int sideone;
								int sidetwo;
								int sidethree;

								sideone = ValidateUserInput("sideone");
								sidetwo = ValidateUserInput("sidetwo");
								sidethree = ValidateUserInput("sidethree");
								Console.WriteLine($"Triangle's custom first side is {sideone} and second side is {sidetwo} and third side is {sidethree}.\n");

							}
							else

							{
								return;
							}
						}
						selection = ValidationMenuSelection();

					}
				} while ();
				}
		}
		}
	}
