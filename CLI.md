Dotnet cli
    dotnet new sln
    dotnet new webapi -n API
    dotnet new classlib -n Application
    dotnet new classlib -n Domain
    dotnet new classlib -n Presistence

    sln add API
    sln add Application
    sln add Domain
    sln add Presistence

    cd API -> dotnet add reference ..\Application\
    cd Application -> dotnet add reference ..\Presistence\ -> dotnet add reference ..\Domain\
    cd Presistence -> dotnet add reference ..\Domain\

    Migration
        Enable-Migrations -ProjectName .\Presistence -StartUpProjectName .\API
        add-migration InitialDB 