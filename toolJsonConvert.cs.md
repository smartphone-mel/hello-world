##### DeserializeObject-SerializeObject Example with JsonConvert!

```C#
using System;
using Newtonsoft.Json;
					
public class Program
{
	/* DeserializeObject-SerializeObject Example with JsonConvert! */
	public static void Main()
	{
		object [] oArray;
		/* The JSON string! */
		string sJSON = "[ { \"id\":\"1\", \"name\":\"eMarketing\", \"result\": { \"totals\":\"5\" } }"
					 + ", { \"id\":\"2\", \"name\":\"Newspapers\", \"result\": { \"totals\":\"3\" } }"
					 + ", { \"id\":\"3\", \"name\":\"TV Programs\", \"result\": { \"totals\":\"4\" } }"
					 + ", { \"id\":\"4\", \"name\":\"Magazines\", \"result\": { \"totals\":\"1\" } } ]"
			, sNewJSON = string.Empty;
		
		Console.WriteLine(String.Format("JSON string: {0}\n", sJSON));
		
		/* DeserializeObject! */
		oArray = JsonConvert.DeserializeObject<object []>(sJSON);
		
		foreach (object oAux in oArray)
			Console.WriteLine(String.Format("DeserializeObject: {0}", oAux));
		
		/* SerializeObject! */
		sNewJSON = JsonConvert.SerializeObject(oArray, Formatting.Indented);
		
		Console.WriteLine(String.Format("\nSerializeObject: {0}", sNewJSON));
	}
}
```
