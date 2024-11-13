# ooptask1
using System;

public partial class Program
{
    public static void Main()
    {
        Console.WriteLine("Welcome to the car simulation!");

        
        IEngine engine = new Engine();
        
   
        Car car = new Car(engine);

    
        car.StartCar();
    }
}

public interface IEngine
{
    void Start();
}


public class Engine : IEngine
{
    public void Start()
    {
        Console.WriteLine("Engine started.");
    }
}


public class Car
{
    private readonly IEngine _engine;


    public Car(IEngine engine)
    {
        _engine = engine;
    }


    public void StartCar()
    {
        Console.WriteLine("Car is starting.");
        _engine.Start();  
    }
}
