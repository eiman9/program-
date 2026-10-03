# program-
class Person
{
    public string Name;
    public string Email;

    public Person(string name, string email)
    {
        Name = name;
        Email = email;
        Console.WriteLine("Person constructor");
    }

    public void DisplayBasicInfo()
    {
        Console.WriteLine(Name);
        Console.WriteLine(Email);
    }
}

class Student : Person
{
    public int StudentId;
    public double GPA;

    public Student(string name, string email, int studentId, double gpa)
        : base(name, email)
    {
        StudentId = studentId;
        GPA = gpa;
        Console.WriteLine("Student constructor");
    }
}

class Employee : Person
{
    public int EmployeeId;
    public double Salary;

    public Employee(string name, string email, int employeeId, double salary)
        : base(name, email)
    {
        EmployeeId = employeeId;
        Salary = salary;
        Console.WriteLine("Employee constructor");
    }
}

class Teacher : Employee
{
    public string CourseName;

    public Teacher(string name, string email, int employeeId,
                   double salary, string courseName)
        : base(name, email, employeeId, salary)
    {
        CourseName = courseName;
        Console.WriteLine("Teacher constructor");
    }

    public void Teach()
    {
        Console.WriteLine("Teacher teaches " + CourseName);
    }
}

class Program
{
    static void Main()
    {
        Student student = new Student(
            "Ahmed", "ahmed@gmail.com", 101, 3.5);

        student.DisplayBasicInfo();

        Teacher teacher = new Teacher(
            "Ali", "ali@gmail.com", 201, 1000, "Programming");

        teacher.DisplayBasicInfo();
        teacher.Teach();
    }
}