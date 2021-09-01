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
    
easy

    string str = null;
    Console.WriteLine(str ?? "no data in str");

Operator ??=
========================

    string str = null;
    str ??= string.Empty;
    Console.WriteLine("number of characters in str " + str.Length);

array

      int[] myArray = null;
      myArray ??= new int[0];
      Console.WriteLine(myArray.Length);

Operator ?.
========================

    using System.Linq;
    ...
    int [] myArray = null;
    Console.WriteLine("Sum of myArray elements " + (myArray?.Sum() ?? 0));

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

## ref


 		// ref out -  when you want to return more than 1 value
        static void Main(string[] args)
        {
            int uSum = 0, uX = 2, uY = 3;
            MySum(ref uSum, uX, uY);
        }
        static void MySum(ref int sum, int x, int y)
        {
            sum = x + y;
        }

        

## out
        
        static void Main(string[] args)
        {
            int uSum, uX = 2, uY = 3;
            MySum(out uSum, uX, uY);
        }
        static void MySum(out int sum, int x, int y)
        {
            sum = x + y;
        } 
       
		
## modifies the array
		//  you can only edit data in the array       
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
            array[index] = value;

            return array;
        }
        
## modifies link array
		
		// link array will not be changed
        static void Main(string[] args)
        {
            int[] myArray = { 1, 3, 5 };
            EditArray(myArray);
        }
        // myArray and arr - two labels that refer to the same memory region 
        // refer is copied
        static void EditArray(int[] arr)
        {
        // delete one reference
            arr = null;
        }
        
        
        // link array will be changed (ref)
        static void Main(string[] args)
        {
            int[] myArray = { 1, 3, 5 };
            EditArray(ref myArray);
        }
        //  in arr link passed to link
        //  refer is no copied
        static void EditArray(ref int[] arr)
        {
        // delete one reference
            arr = null;
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
