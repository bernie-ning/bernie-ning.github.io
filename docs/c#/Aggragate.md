           ```
           var numbers = new List<int> { 1, 2, 3, 4, 5 };
            var students1 = new List<Student>() {
                new Student{ Name="nxg1",Age = 1 },
                new Student{ Name="nxg2",Age = 3 },
                new Student{ Name="nxg3",Age = 3 },
                new Student{ Name="nxg4",Age = 14 },
                new Student{ Name="nxg5",Age = 5 }
            };

            foreach (var num in numbers)
            {
                var a = students1.Where(x => x.Age == num);
                Console.WriteLine($"{string.Join(",",a.Select(x=>x.Name))}");
            }


            int totalAge = students1.Aggregate(50,(total, st) => total += st.Age);
            Console.WriteLine($"totalAge: {totalAge}");

            Student maxAge = students1.Aggregate((st1, st2) => 
            {
                Console.WriteLine($"st1: {st1.Name} -- st2:{st2.Name}");
                return st1.Age > st2.Age ? st1 : st2;
            });

            Console.WriteLine($"maxAge: {maxAge.Age}");
            ```
            
