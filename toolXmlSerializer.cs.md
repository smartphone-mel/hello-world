#####Serialize-Deserialize Example with XmlSerializer!

```C#
using System;
using System.IO;
using System.Xml.Serialization;

[XmlRoot("City")]
public class City
{
	public string Name { get; set; }
	public string State { get; set; }
	public string County { get; set; }
	public bool IsCountyCenter { get; set; }
	public bool IsStateCapital { get; set; }
	public int Population { get; set; }
}

public class Program
{
	public static void Main()
	{
		MemoryStream msMain = new MemoryStream();
		XmlSerializer xmlsMain;
		City cMain, cResult;
		
		cMain = new City();
		cMain.Name = "Independence";
		cMain.State = "KS";
		cMain.County = "Montgomery";
		cMain.IsCountyCenter = true;
		cMain.IsStateCapital = false;
		cMain.Population = 10000;
		
		xmlsMain = new XmlSerializer(cMain.GetType());
		xmlsMain.Serialize(msMain, cMain);
		var vResult = System.Text.Encoding.Default.GetString(msMain.ToArray());
		// To Deserialize, in revision...
		//cResult = (City) xmlsMain.Deserialize(msMain);
		
		Console.WriteLine(vResult);
		//Console.WriteLine(cResult);
	}
}
```
