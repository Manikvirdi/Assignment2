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
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using ConsoleApp11;
using NUnit.Framework;

namespace TestClass
{
	[TestFixture]
	public class Class1
    {

		[Test]
		public void Analyse_Input10and10and10_ReturnEquilateral()
		{

			//Arrange 
			int sideFirst = 10;
			int sideSecond = 10;
			int sideThird = 10;

			string expectedResult = "This is an equilateral triangle";
		

			//Act 
			string actualResult = TriangleSolver.Analyse(sideFirst, sideSecond, sideThird);

			//Assert 
			Assert.AreEqual(expectedResult, actualResult);
		}


		[Test]
		public void Analyse_Input20and20and30_ReturnIsoceles()
		{

			//Arrange 
			int sideFirst = 20;
			int sideSecond = 20;
			int sideThird = 30;

			string expectedResult = "This is an Isoceles triangle";


			//Act 
			string actualResult = TriangleSolver.Analyse(sideFirst, sideSecond, sideThird);

			//Assert 
			Assert.AreEqual(expectedResult, actualResult);
		}

		[Test]
		public void Analyse_Input20and30and20_ReturnIsoceles()
		{

			//Arrange 
			int sideFirst = 20;
			int sideSecond = 30;
			int sideThird = 20;

			string expectedResult = "This is an Isoceles triangle";


			//Act 
			string actualResult = TriangleSolver.Analyse(sideFirst, sideSecond, sideThird);

			//Assert 
			Assert.AreEqual(expectedResult, actualResult);
		}

		[Test]
		public void Analyse_Input30and20and20_ReturnIsoceles()
		{

			//Arrange 
			int sideFirst = 30;
			int sideSecond = 20;
			int sideThird = 20;

			string expectedResult = "This is an Isoceles triangle";


			//Act 
			string actualResult = TriangleSolver.Analyse(sideFirst, sideSecond, sideThird);

			//Assert 
			Assert.AreEqual(expectedResult, actualResult);
		}

		[Test]
		public void Analyse_Input11and15and18_ReturnScalene()
		{
		
			//Arrange 
			int sideFirst = 11;
			int sideSecond = 15;
			int sideThird = 18;

			string expectedResult = "This is a Scalene triangle";

	
			//Act 
			string actualResult = TriangleSolver.Analyse(sideFirst, sideSecond, sideThird);

			//Assert 
			Assert.AreEqual(expectedResult, actualResult);
		}

		[Test]
		public void Analyse_Input0and3and5_ReturnInvalidTriangle()
		{

			//Arrange 
			int sideFirst = 0;
			int sideSecond = 3;
			int sideThird = 5;

			string expectedResult = "This is an Invalid Triangle";


			//Act 
			string actualResult = TriangleSolver.Analyse(sideFirst, sideSecond, sideThird);

			//Assert 
			Assert.AreEqual(expectedResult, actualResult);
		}

		[Test]
		public void Analyse_Input3and7and10_ReturnScalene()
		{

			//Arrange 
			int sideFirst = 3;
			int sideSecond = 7;
			int sideThird = 10;

			string expectedResult = "This is an Invalid Triangle";


			//Act 
			string actualResult = TriangleSolver.Analyse(sideFirst, sideSecond, sideThird);

			//Assert 
			Assert.AreEqual(expectedResult, actualResult);
		}

		[Test]
		public void Analyse_Input3and2and7_InvalidTriangle()
		{

			//Arrange 
			int sideFirst = 3;
			int sideSecond = 2;
			int sideThird = 7;

			string expectedResult = "This is an Invalid Triangle";


			//Act 
			string actualResult = TriangleSolver.Analyse(sideFirst, sideSecond, sideThird);

			//Assert 
			Assert.AreEqual(expectedResult, actualResult);
		}
	}
}
