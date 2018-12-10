# AspNetCoreFundamentals  : 10-12-2018

ASP.NET Core
ASP.NET Core is an open-source and cross-platform framework for building modern cloud based internet connected applications, such as web apps, IoT apps and mobile backends. ASP.NET Core apps can run on .NET Core or on the full .NET Framework. It was architected to provide an optimized development framework for apps that are deployed to the cloud or run on-premises. It consists of modular components with minimal overhead, so you retain flexibility while constructing your solutions. You can develop and run your ASP.NET Core apps cross-platform on Windows, Mac and Linux.




Install the .NET Core SDK
1. Go to dot.net to download and install the .NET Core SDK for your OS

Introduction to the .NET CLI
  Test that you have you .NET installed by going to commandline or terminal and typing
     dotnet 
   Create and run your first console app Initialize code
   
      mkdir hello

      cd hello

      dotnet new console
   
Run app
      
    dotnet restore

    dotnet run
   
For this section it's a good idea to have Vs Code installed or you can open it in notepad. You can [download](https://code.visualstudio.com/) it here.   

**Edit Code** 

*Option 1: Consider updating program.cs to accept input*

      public static void Main(string[] args)
          {
            string name;
            
            Console.WriteLine("What's your name?");
            name = Console.ReadLine();

            Console.WriteLine($"Hello {name} thanks for using this material");
            
        }

*Option 2: Hello World Console to Hello World Web*

   Add package using dotnet cli
   
      - You can also add a package using the dotnet CLI *dotnet add package Microsoft.AspNetCore*
      - Restore the packages
  
          dotnet restore
     
   Add a Startup.cs file that defines the request handling logic:
    
      using System;
      using Microsoft.AspNetCore.Hosting;

      namespace movingtoweb
        {
      public class Program
         {
           public static void Main(string[] args)
               {
            var host = new WebHostBuilder()
                .UseKestrel()
                .UseStartup<Startup>()
                .Build();

               host.Run();
             }
         }
      }
      
  Run the app
  
    dotnet run
    
  Go to http://localhost:5000 in your browser

