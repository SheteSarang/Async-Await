# Async-Await
using System;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        Console.WriteLine("Starting tasks...");
        
        Task boilEggTask = BoilEggAsync();
        Task heatMilkTask = HeatMilkAsync();
        Task heatWaterTask = HeatWaterAsync();
        
        await Task.WhenAll(boilEggTask, heatMilkTask, heatWaterTask);
        
        Console.WriteLine("All tasks completed.");
    }

    static async Task BoilEggAsync()
    {
        Console.WriteLine("Boiling egg...");
        await Task.Delay(3000); // Simulates boiling egg for 3 seconds
        Console.WriteLine("Egg boiled.");
    }

    static async Task HeatMilkAsync()
    {
        Console.WriteLine("Heating milk...");
        await Task.Delay(2000); // Simulates heating milk for 2 seconds
        Console.WriteLine("Milk heated.");
    }

    static async Task HeatWaterAsync()
    {
        Console.WriteLine("Heating water...");
        await Task.Delay(1000); // Simulates heating water for 1 second
        Console.WriteLine("Water heated.");
    }
}

//Starting tasks...
//Boiling egg...
//Heating milk...
//Heating water...
//Water heated.
//Milk heated.
//Egg boiled.
//All tasks completed.
