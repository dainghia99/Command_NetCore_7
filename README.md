# Package
dotnet add package System.Data.SqlClient
dotnet add package Microsoft.EntityFrameworkCore
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package Microsoft.EntityFrameworkCore.Tools
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.Extensions.DependencyInjection
dotnet add package Microsoft.Extensions.Logging.Console

dotnet tool install --global dotnet-ef
dotnet tool install -g Microsoft.Web.LibraryManager.Cli

dotnet add package Microsoft.AspNetCore.Identity
dotnet add package Microsoft.AspNetCore.Identity.EntityFrameworkCore
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
dotnet add package Microsoft.AspNetCore.Identity.UI
dotnet add package Microsoft.AspNetCore.Authentication
dotnet add package Microsoft.AspNetCore.Http.Abstractions
dotnet add package Microsoft.AspNetCore.Authentication.Cookies
dotnet add package Microsoft.AspNetCore.Authentication.Facebook
dotnet add package Microsoft.AspNetCore.Authentication.Google
dotnet add package Microsoft.AspNetCore.Authentication.JwtBearer
dotnet add package Microsoft.AspNetCore.Authentication.MicrosoftAccount
dotnet add package Microsoft.AspNetCore.Authentication.oAuth
dotnet add package Microsoft.AspNetCore.Authentication.OpenIDConnect
dotnet add package Microsoft.AspNetCore.Authentication.Twitter

# IdentityUser

donet aspnet-codegenerator identity -dc mydbcontext


# Scaffold (ConnectionString)
Scaffold-DbContext "Server=DESKTOP-GUQBECH;Database=QLDuAn;integrated security=true; Encrypt=false TrustServerCertificate=true;" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Models