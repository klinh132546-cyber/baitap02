using System;
using System.Collections.Generic;
using System.Linq;

class Student
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
}

class Program
{
    static void Show(Student s)
    {
        Console.WriteLine("ID: " + s.Id + ", Name: " + s.Name + ", Age: " + s.Age);
    }

    static void Main(string[] args)
    {
        List<Student> list = new List<Student>
        {
            new Student { Id = 11, Name = "Nam", Age = 16 },
            new Student { Id = 12, Name = "An", Age = 17 },
            new Student { Id = 13, Name = "Minh", Age = 15 },
            new Student { Id = 14, Name = "Anh", Age = 18 },
            new Student { Id = 15, Name = "Long", Age = 19 }
        };

        Console.WriteLine("a. Danh sach hoc sinh:");
        foreach (var s in list) Show(s);
        Console.WriteLine();

        Console.WriteLine("b. Hoc sinh tu 15 den 18 tuoi:");
        var group1 = list.Where(x => x.Age >= 15 && x.Age <= 18);
        foreach (var s in group1) Show(s);
        Console.WriteLine();

        Console.WriteLine("c. Hoc sinh co ten bat dau bang A:");
        var group2 = list.Where(x => x.Name.StartsWith("A"));
        foreach (var s in group2) Show(s);
        Console.WriteLine();

        Console.WriteLine("d. Tong tuoi:");
        int total = list.Sum(x => x.Age);
        Console.WriteLine(total);
        Console.WriteLine();

        Console.WriteLine("e. Hoc sinh lon tuoi nhat:");
        int max = list.Max(x => x.Age);
        var group3 = list.Where(x => x.Age == max);
        foreach (var s in group3) Show(s);
        Console.WriteLine();

        Console.WriteLine("f. Sap xep theo tuoi tang dan:");
        var sorted = list.OrderBy(x => x.Age);
        foreach (var s in sorted) Show(s);
    }
}
