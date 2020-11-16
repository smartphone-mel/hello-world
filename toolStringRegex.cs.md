##### Regex Examples!

```C#
/**************************/
/* Regex Capital Letters! */
/**************************/
using System;
using System.Text;
using System.Text.RegularExpressions;

public class Program
{
	public static void Main()
	{
		// Long string!
		string authors = "Mahesh Chand, Raj Kumar, Mike Gold, Allen O'Neill, Marshal Troll";
		
		// Create a pattern for a word that starts with letter "M":
		string pattern = @"\b[M]\w+";
		// Create a Regex (uppercase or lowercase):
		Regex rg = new Regex(pattern, RegexOptions.IgnoreCase);
		
		// Get all matches!
		MatchCollection matchedAuthors = rg.Matches(authors);
		
		// Print all matched authors!
		foreach (Match mAux in matchedAuthors)
			Console.WriteLine(mAux.ToString());
	}
}

/***********************/
/* Regex Phone Format! */
/***********************/
using System;  
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Text.RegularExpressions;

public class Program
{
	public static void Main(string[] args)
	{
		// Class Regex Repesents an immutable regular expression.
		// It can start with '+' char or a number, and have '-' (and number) chars!
		Regex r = new Regex(@"^\+?\d{0,2}\-?\d{4,5}\-?\d{5,6}");
		
		//Input strings for Match valid mobile number.
		string[] str = { "0xBA07EF", "+91-9678967101", "9678967101", "+91-9678-967101", "+91-96789-67101", "+919678967101" };
		
		foreach (string s in str)
			//The IsMatch method is used to validate a string or
			//to ensure that a string conforms to a particular pattern.
			Console.WriteLine("{0} {1} a valid mobile number.", s,
							  r.IsMatch(s) ? "is" : "is not");
	}
}
```
