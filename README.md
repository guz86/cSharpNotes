# cSharpNotes

Function
========================
using System;

namespace Junior
{
    class Program
    {
        // Функции - как передовать обычные данные как передовать массивы
        static void Main(string[] args)
        {
            Console.WriteLine("Привет");

            // WriteError("Ошибка. Нет интернета.", ConsoleColor.Red);
            WriteError("Ошибка. Нет интернета.", symbol: '!');

            Console.WriteLine("Не может быть");
            // в функцию из программы передается аргумент "Оплати интернет"
            // WriteError("Оплати интернет", ConsoleColor.Red);
            WriteError("Оплати интернет", ConsoleColor.Yellow);

            // функция с возвращаемыми значениями
            //Console.WriteLine(Sum(4, 5) );
            int l = 5, u = 3, sum;
            sum = Sum(l, u) + l + u;
            Console.WriteLine(sum + " " + Sum(u, l));

            Console.WriteLine("-------------");

            //int uSum = 0, uX = 2, uY = 3;

            // если мы оставляем uSum без инициализации используем out
            int uSum, uX = 2, uY = 3;

            // при !ref uSum! требуется обязательно проинициализировать переменную  int uSum = 0  

            // MySum(uSum, uX, uY);
            // 0

            //MySum(ref uSum, uX, uY);

            //out - обязует самостоятельно проиниализировать переменную

            MySum(out uSum, uX, uY);

            Console.WriteLine(uSum);

            Console.WriteLine("-------------");

            int[]  myArray = new int [5];
            // передаем ссылку на область памяти
            // EditArray(myArray, 2, 5);

            myArray = EditArray(myArray, 2, 10);
            Console.WriteLine(myArray[2]);


        }