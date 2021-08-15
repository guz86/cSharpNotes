# cSharpNotes

Function
========================
How to advance conventional data as advanced arrays

	static void Main(string[] args)
	{
          Console.WriteLine("Hi");
        // Pass on the argument - "Pay the service"  '!'
		WriteError("Error. No Internet", symbol: '!');
		Console.WriteLine("");
        // Pass on the argument - "Pay the service"  Yellow
        WriteError("Pay the service", ConsoleColor.Yellow);
		}
    // ConsoleColor.Red  '#' - default
	static void WriteError(string text, ConsoleColor color = ConsoleColor.Red, char symbol = '#')
        {
            // remember the current text color in the console in the variable
            ConsoleColor defaulColor = Console.ForegroundColor;
            Console.ForegroundColor = color;
            Console.WriteLine(symbol + text);

            // returns the current color
            Console.ForegroundColor = defaulColor;
        }

ref и out

        static void Main(string[] args)
        {
            int uSum, uX = 2, uY = 3;

            // ref uSum - NEED int uSum = 0  

            MySum(out uSum, uX, uY);
			Console.WriteLine(uSum);
        }
  
        // ref out -  when you want to return more than 1 value
        //static void MySum(ref int sum, int x, int y)
        static void MySum(out int sum, int x, int y)
        {
            sum = x + y;
        }





