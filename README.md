# Assignment2
Triangle
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp11
{
	public class TriangleSolver
	{

		private int sideone;
		private int sidetwo;
		private int sidethree;


		public TriangleSolver()
		{
			sideone = 1;
			sidetwo = 1;
			sidethree = 1;
		}

		public TriangleSolver(int sideone, int sidetwo, int sidethree)
		{
			this.sideone = sideone;
			this.sidetwo = sidetwo;
			this.sidethree = sidethree;
		}

		public int Getsideone()
		{
			return sideone;
		}


		public int Getsidetwo()
		{
			return sidetwo;
		}


		public int Getsidethree()
		{
			return sidethree;
		}
		//https://www.w3resource.com/csharp-exercises/conditional-statement/csharp-conditional-statement-exercise-14.php dated 4th June 2019
		static string output;
	
		public static string Analyse(int sideone, int sidetwo, int sidethree)

		{
			/*int sideone, sidetwo, sidethree;
			Console.WriteLine("To determine whether the Triangle is Equilateral, Scalene, Isoceles:\n");

			Console.WriteLine("Enter side one of a triangle: ");
			sideone = Convert.ToInt32(Console.ReadLine());

			Console.WriteLine("Input side two of a triangle: ");
			sidetwo = Convert.ToInt32(Console.ReadLine());

			Console.WriteLine("Input side three of a triangle: ");
			sidethree = Convert.ToInt32(Console.ReadLine());*/

			if ((sideone + sidetwo) > sidethree && (sidetwo + sidethree) > sideone && (sideone + sidethree) > sidetwo)
			{
				Console.WriteLine("The given values are valid");
				Console.WriteLine("");
				if (sideone == sidetwo && sidetwo == sidethree && sidethree == sideone)
				{
					//Console.WriteLine("The Triangle is Equilateral.\n");
					output = "The Triangle is Equilateral.\n";
					return (output);
				}
				else if (sideone == sidetwo || sideone == sidethree || sidetwo == sidethree)
				{
					//Console.WriteLine("The Triangle is Isoceles.\n");
					output = "The Triangle is Isoceles.\n";
					return (output);
				}

				else
				{
					//Console.WriteLine("The Triangle is Scalene.\n");
					output = "The Triangle is Scalene.\n";
					return (output);
				}
			}
			else
			{
				output = "the given values are not valid";
			}
			return output;
		}
		
	}
}
