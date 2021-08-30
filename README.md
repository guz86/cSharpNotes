# cSharpNotes

NULL Integration  - Operator ??
========================

            string str = null;
            string result;

            if (str == null)
            {
                result = "нет данных в str";
            }
            else
            {
                result = str;
            }
            Console.WriteLine(result);

How to use
  string str = null;
  string resultNew = str ?? string.Empty;
  Console.WriteLine("number of characters in str " + resultNew.Length);


Operator ??=
========================

Operator ?.
========================


Function (and / or) method
========================

	<Access Specifier> <Return Type> <Method Name>(Parameter List) {
   	Method Body
	}

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

## ref и out

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
		
## Array
		        
        static void Main(string[] args)
		{
            int[]  myArray = new int [5];
            myArray = EditArray(myArray, 2, 10);
            Console.WriteLine(myArray[2]);
        }

        // function modifies the array
        static int[] EditArray(int[] array, int index, int value)
        {
            // recreating the array
            array = new int[6];
            array[index]= value;

            return array;
        }


## resize array - overload

		// two functions with the same name (ResizeArray) and different signature
        static void Main(string[] args)
        {
            int[] myArrayResize = new int[5];
            myArrayResize = ResizeArray(myArrayResize, 10);
            
            int[,] myArrayResizeTwo = new int[5, 5];
            myArrayResizeTwo = ResizeArray(myArrayResizeTwo, 10, 10);
            
        }

        // recreate an array with a new size
        /// <summary>
        /// Migrate data to a new array
        /// </summary>
        /// <param name="array">Array</param>
        /// <param name="size">Size new Array</param>
        /// <returns>New Size Array</returns>
        
        static int[] ResizeArray (int[] array, int size)
        {   
            int[] tempArray = new int[size];
            // migrate data to a new array
            for (int i = 0; i < array.Length; i++)
            {
                tempArray[i] = array[i];
            }
            array = tempArray;
            return array;
        }

       static int[,] ResizeArray (int[,] array, int x, int y)
        {
            int[,] tempArray = new int[x,y];
            // migrate data to a new array
            for (int i = 0; i < array.GetLength(0); i++)
            {
                for (int j = 0; j < array.GetLength(1); j++)
                {
                    tempArray[i,j] = array[i,j];
                }
            }
            array = tempArray;
            return array;
        }
        

-end
## English alphabet with 26 letters!
            // English alphabet with 26 letters!
            char[] letters = new char[26];
            sbyte k = 0;

            for (char c = 'a'; c <= 'z'; c++)
            {
                letters[k] = c;
                k++;
            }
