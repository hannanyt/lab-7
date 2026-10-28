# Book Management System

A simple web application for managing a library of books. Built with **ASP.NET Core Razor Pages** (.NET 10) and **SQL Server**, it supports adding, viewing, editing and deleting book records.

## Features

- View all books in a list (newest first)
- Add a new book
- Edit an existing book
- Delete a book (with a confirmation page)
- Responsive layout using Bootstrap

## Book Fields

| Field       | Description                 | Max length |
|-------------|-----------------------------|------------|
| Title       | Name of the book            | 50         |
| Author      | Author of the book          | 50         |
| Description | Short description           | 50         |
| Publisher   | Publisher name              | 50         |
| Status      | e.g. Available / Issued     | 50         |
| Category    | e.g. Fiction, Science       | 50         |

## Tech Stack

- C# / ASP.NET Core Razor Pages (.NET 10)
- SQL Server (LocalDB by default) via `Microsoft.Data.SqlClient`
- Bootstrap, jQuery and jQuery Validation

## Prerequisites

- [.NET 10 SDK](https://dotnet.microsoft.com/download)
- SQL Server or SQL Server LocalDB (included with Visual Studio)
- Visual Studio 2022+ or VS Code (optional)

## Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR-USERNAME/Book_Management_System.git
   cd Book_Management_System
   ```

2. **Create the database and table** (run in SQL Server Management Studio or `sqlcmd`)
   ```sql
   CREATE DATABASE BMS_DB1;
   GO
   USE BMS_DB1;
   GO
   CREATE TABLE dbo.books (
       Id          INT IDENTITY(1,1) PRIMARY KEY,
       title       NVARCHAR(50) NULL,
       author      NVARCHAR(50) NULL,
       description NVARCHAR(50) NULL,
       publisher   NVARCHAR(50) NULL,
       status      NVARCHAR(50) NULL,
       category    NVARCHAR(50) NULL
   );
   ```

3. **Check the connection string** in `Book_Management_System/appsettings.json`:
   ```json
   "ConnectionStrings": {
     "DefaultConnection": "Data Source=(LocalDB)\\MSSQLLocalDB;Initial Catalog=BMS_DB1;Integrated Security=True;Pooling=False;Encrypt=True;Trust Server Certificate=False"
   }
   ```
   Change it if you use a different SQL Server instance.

4. **Run the app**
   ```bash
   cd Book_Management_System
   dotnet run
   ```
   Then open `http://localhost:5145` (or `https://localhost:7262`) in your browser.

## Project Structure

```
Book_Management_System/
├── Book_Management_System.slnx
└── Book_Management_System/
    ├── Models/            # Book model
    ├── Pages/
    │   ├── Books/         # Index, Create, Edit, Delete pages
    │   └── Shared/        # Layout and partials
    ├── wwwroot/           # CSS, JS and client libraries
    ├── appsettings.json   # Configuration and connection string
    └── Program.cs         # Application entry point
```

## Authors

- Abdul-Hannan (25-ST-056)
- Roshaan-Wazeer (25-ST-080)
