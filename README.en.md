# 📝 Simple Calculator Made for Studies (SCMS)

<div align="center">
    <a>✔️ English</a>
    <br>
    <a href="./README.md">Portuguese</a>
</div>

![.Net](https://img.shields.io/badge/.NET-5C2D91?style=for-the-badge&logo=.net&logoColor=white)
![Udemy](https://img.shields.io/badge/Udemy-A435F0?style=for-the-badge&logo=Udemy&logoColor=white)
![C#](https://img.shields.io/badge/c%23-%23239120.svg?style=for-the-badge&logo=csharp&logoColor=white)

Actually, i'm learning C# on Nélio Alves Course in Udemy. With knowledge accquired until class 22, i made this simple calculator to the apply all the learning provided.

### 🔎 Source Code

```C#
// Simple calculater made with my basics knowledge acquired :)
using System;

namespace UltraSimpleProgram
{
    class Program
    {
        // Main function from Program
        static void Main(string[] args)
        {
            // Operations avaliable
            var sum = (double x, double y) => (double)x + y;
            var sub = (double x, double y) => (double)x - y;
            var mul = (double x, double y) => (double)x * y;
            var div = (double x, double y) => (double)x / y;

            // User interaction
            Console.Write("[ + - x / ] Please Type operation: ");
            string? operation_type = Console.ReadLine();

            double x = GetNumber("[?] Please type value X: ");
            double y = GetNumber("[?] Please type number Y: ");

            // Switch case of operations
            switch (operation_type)
            {
                case "+":
                    // Res, n1, operation, n2
                    HandleOutput(sum(x, y), x, operation_type, y);
                    break;

                case "-":
                    HandleOutput(sub(x, y), x, operation_type, y);
                    break;

                case "x" or "*":
                    HandleOutput(mul(x, y), x, operation_type, y);
                    break;
                
                case "/":
                    HandleOutput(div(x, y), x, operation_type, y);
                    break;

                default:
                    Console.WriteLine("Please select an valid operation! >:(");
                    break;
            }

        }

        // An simple and dumb way to show result better
        static void HandleOutput(double result, double x, string? operation, double y)
        {
            Console.WriteLine($"{x} {operation} {y} = {result}");
        }

        // Responsable to get numbers(double) from user input
        static double GetNumber(string text)
        {
            Console.Write(text);
            string? raw_input = Console.ReadLine();

            return Convert.ToDouble((raw_input == null ? "0" : raw_input).Replace(".", ","));
        }
    }
}
```

---
