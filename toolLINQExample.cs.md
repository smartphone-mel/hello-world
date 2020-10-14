##### DeserializeObject-SerializeObject Example with JsonConvert!

```C#
using System;
using System.Collections.Generic;
using System.Linq;

public class Program
{
	public class StockLibros
	{
		public string Nombre { get; set; }
		public int Stock { get; set; }
	}
	
	public static void Main()
	{
		// Valores!
		var lValores = new List<int> {1,2,3,4,5,6,7,8,9};
		var nSuma = lValores.Sum();
		var nPares = lValores.Where(x => x % 2 == 0).ToList();
		
		Console.WriteLine("Valores:");
		foreach (var vInitAux in lValores)
			Console.WriteLine(" - " + vInitAux.ToString());
		
		Console.WriteLine("Suma: " + nSuma.ToString());
		
		Console.WriteLine("Pares:");
		foreach (var vAux in nPares)
			Console.WriteLine(" - " + vAux.ToString());
		
		// StockLibros!
		var aLibros = new List<StockLibros>
		{
			new StockLibros {Nombre = "Best C Methods", Stock = 5},
			new StockLibros {Nombre = "JAVA Devs", Stock = 8},
			new StockLibros {Nombre = "C# MultiPlatform", Stock = 3},
			new StockLibros {Nombre = "C++ Common Engines", Stock = 0}
		};
		
		var rSelect = aLibros.Select(x => x.Nombre).ToList();
		var rStock = aLibros.Where(x => x.Stock > 0).ToList();
		var rFirst = aLibros.First();
		var rLast = aLibros.Last();
		var rOrderBy = aLibros.OrderBy(x => x.Stock).ToList();
		var rOrderByTop = aLibros.OrderByDescending(x => x.Stock).ToList();
		var rStockList = aLibros.Sum(x => x.Stock);
		var rMax = aLibros.Max(x => x.Stock);
		var rMin = aLibros.Min(x => x.Stock);
		var rMedia = aLibros.Average(x => x.Stock);
		var rAllStock = aLibros.All(x => x.Stock > 0);
		var rSomeStock = aLibros.Any(x => x.Stock > 0);
		var rComplex = from vLibro in aLibros
			where vLibro.Stock > 3
			orderby vLibro.Stock
			select vLibro;
	}
}
```
