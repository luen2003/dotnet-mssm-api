## Install
```
dotnet new webapi -n ProductApi
cd ProductApi
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package Microsoft.EntityFrameworkCore.Tools
dotnet add package Swashbuckle.AspNetCore
```
## Database
```
CREATE DATABASE ProductDb;
GO

USE ProductDb;

CREATE TABLE Products (
    Id INT PRIMARY KEY IDENTITY(1,1),
    Name NVARCHAR(100),
    Price DECIMAL(18,2)
);
```
```
USE ProductDb;
GO

CREATE USER luong FOR LOGIN luong;

ALTER ROLE db_owner ADD MEMBER luong;
```
## Run
```
dotnet build
dotnet run
```
Swagger UI: http://localhost:5162/swagger/index.html
POST http://localhost:5162/api/products - {
  "name": "Laptop Dell",
  "price": 1200.00
}
GET http://localhost:5162/api/products