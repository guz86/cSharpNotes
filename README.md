# cSharpNotes

Function
========================
How to advance conventional data as advanced arrays

`static void Main(string[] args)
        {
        Console.WriteLine("Hi");
        // Pass on the argument - "Pay the service"  '!'
		WriteError("Error. No Internet", symbol: '!');
		Console.WriteLine("");
        // Pass on the argument - "Pay the service"  Yellow
        WriteError("Pay the service", ConsoleColor.Yellow);
		}
static void WriteError(string text, ConsoleColor color = ConsoleColor.Red, char symbol = '#')
        {
            // remember the current text color in the console in the variable
            ConsoleColor defaulColor = Console.ForegroundColor;
            Console.ForegroundColor = color;
            Console.WriteLine(symbol + text);

            // returns the current color
            Console.ForegroundColor = defaulColor;
        }
`




