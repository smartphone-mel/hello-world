##### String Format!

```C#
using System;

public class Program
{
	/* ...! */
	public static void Main()
	{
		int[] aYears = { 2013, 2014, 2015 };
		int[] aPopulation = { 1025632, 1105967, 1148203 };
		var sbAux = new System.Text.StringBuilder();
		sbAux.Append(String.Format("{0,6} {1,15}\n\n", "Year", "Population"));
		
		for (int iIndex = 0; iIndex < aYears.Length; iIndex++)
			sbAux.Append(String.Format("{0,6} {1,15:N0}\n", aYears[iIndex], aPopulation[iIndex]));
		
		Console.WriteLine(sbAux);
	}
}
```
