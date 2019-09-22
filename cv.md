# Aleksei Lazarenko

### Contact
Email: [alan.thunderclap@mail.ru](mailto:alan.thunderclap@mail.ru)

### Summary
I have been programming since school. It all started with BASIC, then there was Pascal. At my first work, C++ was used, and in parallel I studied C#. C# is currently my main language, which I really like. But it's always important to learn something new. Therefore, I often try other technologies and programming languages. For example, I wrote a few applications for Android. Of the latter, I studied the functional programming language F#. Now I decided to try front-end development.

### Skills
★★★:
* .Net: C#, WinForms, WPF, WCF

★★☆:
* C++

★☆☆:
* Java (for Android)
* F#

### Code examples
```C#
using System;
using System.IO;
using System.Linq;
using System.Text.RegularExpressions;

namespace TextFileTrimmer
{
    class Program
    {
        static void Main(string[] args)
        {
            if (args.Length == 0)
            {
                Console.WriteLine("Не указан обязательный параметр - имя файла!");
            }
            else
                try
                {
                    string filename = args[0];

                    var trimmed = File.ReadLines(filename);

                    Console.Write("Начальное время (Enter для пропуска): ");
                    string str = Console.ReadLine();
                    if (DateTime.TryParse(str, out DateTime from))
                        trimmed = trimmed.SkipWhile(s => GetDate(s) < from);

                    Console.Write("Конечное время (Enter для пропуска): ");
                    str = Console.ReadLine();
                    if (DateTime.TryParse(str, out DateTime to))
                        trimmed = trimmed.TakeWhile(s => GetDate(s) <= to);

                    Console.Write("Фильтр (Enter для пропуска): ");
                    str = Console.ReadLine();
                    if (str != null)
                    {
                        var regex = new Regex(str);
                        trimmed = trimmed.Where(line => regex.IsMatch(line));
                    }

                    Console.WriteLine("\nВ работе...");
                    File.WriteAllLines(filename + ".trim", trimmed);
                }
                catch (Exception e)
                {
                    Console.WriteLine(e);
                }

            Console.WriteLine("Готово...");
            Console.ReadLine();
        }

        private static DateTime GetDate(string line)
        {
            DateTime dateTime = DateTime.MinValue;
            int pos = line.IndexOf('|');

            if (pos != -1)
                DateTime.TryParse(line.Substring(0, pos), out dateTime);

            return dateTime;
        }
    }
}

```

### Experience
I have experience in developing and supporting client-server applications, special software that works with navigation equipment, services for mobile content providers.

### Languages
* **Russian:** Native
* **English:** Pre-Intermediate
