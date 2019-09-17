# LINQ-To-C-Sharp-Search-City
//a LINQ to C# Code that allows user to enter a first character and end character to get the city that agrees with those litters 

class Program
    {
        static void Main(string[] args)
        {
            int text;
            int textEnd;
            List<string> MyCountries = new List<string> { "cairo", "aswan", "londen", "luxor", "vienna", "boland", "islamabad" };
            var start = "";
            do
            {
                Console.WriteLine("Enter start litter");
                start = Console.ReadLine().ToLower();

            }
            while (int.TryParse(start, out text));

            var end = "";
            do
            {
                Console.WriteLine("Enter End litter");
                end = Console.ReadLine().ToLower();
                Console.WriteLine("Not a String, please try again.");
            }
            while (int.TryParse(end, out textEnd));

            var result = MyCountries.Where(x => x.StartsWith(start) && x.EndsWith(end));      
            foreach (var item in result)
            {
                Console.WriteLine(item);
            }
            Console.ReadLine();
        }
    }
