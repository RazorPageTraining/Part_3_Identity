## Identity

- What is [Identity](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/identity?view=aspnetcore-5.0&tabs=visual-studio)?
- What is [Migrations](https://www.entityframeworktutorial.net/efcore/cli-commands-for-ef-core-migration.aspx)?

</BR>

| NO. | TITLE |
| ----------- | ----------- |
| 1 | [Introduction](https://github.com/RazorPageTraining/Part_1_Introduction) |
| 2 | [Installation](https://github.com/RazorPageTraining/Part_2_Installation) |
| 3 | [How to create RazorPage project](#how-to-create-razorpage-project) |
| 4 | [Packages](#packages)  |
| 5 | [Create Database](#create-database)  |
| 6 | [Create Identity](#create-identity)  |
| 7 | [Create Entity Models](#create-entity-models)  |
| 8 | [Setup DB connection on project](#setup-db-connection-on-project)  |
| 9 | [Database Migration](#database-migration)  |


</BR>

***
#### How to create RazorPage project

1. Open your install VS Code and open VS Code terminal or any terminal that you have.
2. Change to the directory (cd) which will contain the project.
   
   ```console 
   cd desktop
   ```
    
   > ![image](https://user-images.githubusercontent.com/47632993/204571770-6e51bdab-c839-4477-bedd-ccae78ca7615.png)


3. Run the following commands :
   
   ```console 
   dotnet new webapp -o TrainingRazor -au individual        
   ```
   
   > ![image](https://user-images.githubusercontent.com/47632993/204572057-36ecae4f-51ce-4610-8218-476a2aad6e4f.png)

   
4. "TrainingRazor" is the projects name. Name depends on you.
5. After you finish create the project, you can type this commands on terminal to start code :

   ```console 
   code TrainingRazor
   ```
   
   > ![image](https://user-images.githubusercontent.com/47632993/204572344-4005b6a9-2cdc-468c-804a-6338a70b0972.png)

   
6. After VS Code appear, it will show like this on VS Code.

   > ![image](https://user-images.githubusercontent.com/47632993/204572924-60fc8b6a-89f2-4f09-90b8-a917a09da803.png)

7. Click Yes on this :
  
   > ![image](https://user-images.githubusercontent.com/47632993/204573142-690a540f-9689-4bc8-b8b9-f8b823765da1.png)


8. You need to trust the HTTPS development certificate by running the following command on the project terminal:

   - open Terminal on VS Code Menu:
   </BR>
   
   > ![image](https://user-images.githubusercontent.com/47632993/204573580-0d04cf40-309e-4981-be18-b34e53d2c19e.png)
   
   </BR>
   
   - After you click "New Terminal" Terminal will appear on bottom:
   </BR>
   
   > ![image](https://user-images.githubusercontent.com/47632993/204574157-a4e6e9fa-2906-4f19-b064-23c65e375445.png)
   
   </BR>
   - Type this console command on Terminal:
   
   </BR>
   
   ```console 
   dotnet dev-certs https --trust
   ```   
   
   </BR>
   
   > ![image](https://user-images.githubusercontent.com/47632993/204574445-4f306244-8468-4302-a8dc-7c004efe2640.png)
  
   </BR>
        
9. If you already has a valid HTTP Certificate like below image, you can skip no 10 and no 11.
   
   > ![image](https://user-images.githubusercontent.com/47632993/204575520-b37da3e4-1ebc-4a49-b1dd-e64a94d31dad.png)


10. The preceding command doesn't work on Linux. See your Linux distribution's documentation for trusting a certificate. The preceding command displays the following dialog, provided the certificate was not previously trusted :

    > ![image](https://user-images.githubusercontent.com/47632993/146311181-89c5eaaa-3aa3-4feb-8e79-a82059dc8456.png)

11. Select Yes if you agree to trust the development certificate.

12. [Back to Menu](#identity)

***
### Packages

1. For this project we gonna use 2 package that we need to install. On your terminal inside VS Code, you need to type this commands and click enter or just copy & paste :

   ```console
   dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design --version 6.0.5
   dotnet add package Microsoft.EntityFrameworkCore.SqlServer --version 6.0.5
   ```
   
   > ![image](https://user-images.githubusercontent.com/47632993/204577257-d3d1dadf-6413-4efc-9678-0de41d3229b1.png)

   
2. After this package has been installed, you can open your TrainingRazor.csproj and see whether those 2 package has been installed.

   > ![image](https://user-images.githubusercontent.com/47632993/204577516-9b3e51b7-e5f6-4577-9ad0-9c4061810f25.png)

3. Run your project to see whether there are errors. If there are errors, [remove](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-remove-package) the package and install it back or install with different version on [Nuget Gallery website](https://www.nuget.org/packages) as no 4. You can skip no 4 and no 5 if you already succeed.

4. You can find the package on search bar (Skip this if you already succeed):

  > ![image](https://user-images.githubusercontent.com/47632993/204578644-1835b999-3ca7-46b7-bb59-ca4014ba27b7.png)

5. Always click on the first link and you can view all the package version.

  > ![image](https://user-images.githubusercontent.com/47632993/204579322-54647c59-a000-421b-8b54-e85fbee5a830.png)  

6. [Back to menu](#identity)

***
## Create Database

1. Before we start to code, you need to create a database (DB).
2. You just need to create DB using SSMS that we install earlier.
3. Open your SSMS and create a new DB. ([How to use SSMS](https://docs.microsoft.com/en-us/sql/ssms/quickstarts/ssms-connect-query-sql-server?view=sql-server-ver15))
   > ![image](https://user-images.githubusercontent.com/47632993/146315651-d7d8889c-9e2a-4773-bbc7-33c091e8141a.png)

4. You will get your result like this after you finished create your DB

   > ![image](https://user-images.githubusercontent.com/47632993/204594174-6bb8fd43-56c6-4b60-8f99-f9212fa67642.png)

5. [Back to Menu](#identity)

***
## Create Identity

1. If your project already run, stop the project first by click the stop button :

   > ![image](https://user-images.githubusercontent.com/47632993/204580485-20ff349f-9b91-4cb6-9ca7-5c0b0f820306.png)

2. To create identity page on RazorPage, you can type this command on your project terminal via VS Code and click enter :

   ```console
   dotnet aspnet-codegenerator identity
   ```
   
   > ![image](https://user-images.githubusercontent.com/47632993/204581062-99423996-58e9-4212-ae67-44fe5d4ff38e.png)

3. After the command has build succesfully, you can see on your project that you have new folder such as ***Areas/Identity*** like this :

   > ![image](https://user-images.githubusercontent.com/47632993/204581605-0c4b5c6d-be41-4879-a56e-4c63c0e5c4d2.png)

4. Delete folder Data ONLY inside Areas/Identity
    
   > ![image](https://user-images.githubusercontent.com/47632993/204582279-61197db0-3aed-42c1-9522-495007071ae9.png)
 
5. Open Program.cs, and delete EXACT CODE AS FOLLOWS (Use exist folder Data):
   
   ```C#
   using TrainingRazor.Areas.Identity.Data;
   ```
   > ![image](https://user-images.githubusercontent.com/47632993/204583276-0cbe3106-fe95-47dc-8205-0ef17d24b65b.png)
   
   </BR>
    
   ```C#
   var connectionString = builder.Configuration.GetConnectionString("TrainingRazorIdentityDbContextConnection") ?? throw new 
    InvalidOperationException("Connection string 'TrainingRazorIdentityDbContextConnection' not found.");

   builder.Services.AddDbContext<TrainingRazorIdentityDbContext>(options =>
    options.UseSqlServer(connectionString));;

   builder.Services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
    .AddEntityFrameworkStores<TrainingRazorIdentityDbContext>();;
   ``` 
   > ![image](https://user-images.githubusercontent.com/47632993/204583178-bdd6a78c-a334-4a2a-9d27-65d29b19f2ff.png)

6. Edit UseSqlite to UseSqlServer (We gonna use Sql Express ***(Local Database Server for Development)*** for Database)

   FROM :
   > ![image](https://user-images.githubusercontent.com/47632993/204585562-edddcd49-db24-40ff-badc-55e333949d40.png)

   </BR> 
   
   TO :
   > ![image](https://user-images.githubusercontent.com/47632993/204585798-2b1a5074-e593-4bb5-b57b-1c7231a72b6b.png)
    
7. Edit this (Login preferences):

   FROM :
   > ![image](https://user-images.githubusercontent.com/47632993/204586349-7b8ed0bb-b31e-4ad3-b430-37725a231d3b.png)
    
   TO : 
   > ![image](https://user-images.githubusercontent.com/47632993/204587684-b781e49f-4633-4731-98f9-25d3d53c71e6.png)

   </BR>
    
   ```C#
   builder.Services.AddDefaultIdentity<IdentityUser>(options => 
        {
            options.SignIn.RequireConfirmedAccount = false;
            options.User.RequireUniqueEmail = true;
        }
    )
    .AddRoles<IdentityRole>()
    .AddEntityFrameworkStores<ApplicationDbContext>()
    .AddDefaultTokenProviders();
   ```   

8. Edit this (Set Web App  startup folder ***(Need to Login before accessing inside Page)***) :

   FROM :
   > ![image](https://user-images.githubusercontent.com/47632993/204588448-97298102-5e9e-488b-be9d-2527f8429553.png)
    
   TO :
   > ![image](https://user-images.githubusercontent.com/47632993/204588656-4bdab867-72f7-4977-b9a4-54b67e2e37d1.png)
    
   </BR>
   
   ```C#
   builder.Services.AddRazorPages((options =>
   {
       options.Conventions.AuthorizeFolder("/");
   }));
   ```
      
6. Open appsettings.json, and remove this code (Use DefaultConnection):

    ```JSON
    "TrainingRazorIdentityDbContextConnection": "Server=(localdb)\\mssqllocaldb;Database=TrainingRazor;Trusted_Connection=True;MultipleActiveResultSets=true"
    ``` 
    
7. Remove the comma on : 

   > ![image](https://user-images.githubusercontent.com/47632993/204584540-e529cfba-8ba8-48b0-a2a7-62a52a120e6a.png)

8. Will become like this : 

   > ![image](https://user-images.githubusercontent.com/47632993/204584736-77077e70-95c9-420e-a238-be85d6b0369e.png)

9. Now, try run the project. If there are no errors, that is mean you have succeed. When the project is running, you should see that it will run this page first on startup.

   > ![image](https://user-images.githubusercontent.com/47632993/204589210-ec2dd1be-c1ba-423b-acd6-3512ea5d4b76.png)

10. [Back to menu](#identity)

***
## Create Entity Models

1. Create new folder inside TrainingRazor folder :

   > ![image](https://user-images.githubusercontent.com/47632993/204591881-9975671c-6b96-4ba3-a89e-07f5c912844a.png)
   
2. Folder placing must be like this :

   > ![image](https://user-images.githubusercontent.com/47632993/204592065-be39aef4-4e09-4c14-9e63-043dede78b74.png)
   
3. Create a new Entity Model Class inside folder Models :
   
   > ![image](https://user-images.githubusercontent.com/47632993/204592390-d06db2cc-3197-4735-86de-300ca346b6b2.png)

4. This will popup and just insert the name that you wanted to :

   > ![image](https://user-images.githubusercontent.com/47632993/204594717-dd5bc4d6-62d8-4cf7-a2e5-c26f1f45afc9.png)

5. A new file will be created inside Models folder :

   > ![image](https://user-images.githubusercontent.com/47632993/204594940-ea582835-68ea-42da-b647-4a3764f38e76.png)

6. Copy this code and paste inside the file Table.cs ***(Overwrite all code inside)*** and save it.


   ```C#
   using System.ComponentModel.DataAnnotations;
   using System.ComponentModel.DataAnnotations.Schema;

   using Microsoft.AspNetCore.Identity;

   namespace TrainingRazor.Models
   {
       public class Customer : IdentityUser
       {
           [StringLength(500)]
           public string Name { get; set; }
       }

       public class CustPurchased
       {
           [Key]
           public int Id { get; set; }

           [ForeignKey("Customer")]
           public Customer Creator { get; set; }

           [ForeignKey("Product")]
           public int? ProductId { get; set; }
           public int? Quantity { get; set; }
           public Product Product { get; set; }
       }

       public class Product
       {
           [Key]
           public int ProductId { get; set; }

           [StringLength(500)]
           public string ProductName { get; set; }

           [Column(TypeName = "decimal(18, 2)")]
           public decimal Price { get; set; }
       }
   }
   ```

7. [Back to menu](#identity)

***
## Setup DB Connection On Project

1. On your project, open appsettings.json file and insert this ***(If your server name have slash " \ " , you need to insert double slash like this  " \\ " )***:

   ```JSON        
   "ConnectionStrings": {
       "DefaultConnection": "Server=YOUR_SERVER_NAME; Database=YOUR_DB_NAME; Trusted_Connection=True; MultipleActiveResultSets=True;"
    }
   ```    
    
   > ![image](https://user-images.githubusercontent.com/47632993/204600700-29dc36f6-0748-4ed5-ae83-39058cc62b21.png)

2. Save the file.

3. [Back to Menu](#identity)
</BR>

***
## Database Migration

1. Before we create identity schema, we need to edit ApplicationDbContext.cs
2. Open ApplicationDbContext.cs inside Data folder, and paste this source code :

   ```C#
   using System;
   using Microsoft.AspNetCore.Identity;
   ```

   > 
   
   </BR>

   ```C#
   private ApplicationUser saUser { get; set; }
   private IdentityRole role1 { get; set; }
   private IdentityRole role2 { get; set;}
   private IdentityUserRole<string> userAdmin { get; set; }
   private PasswordHasher<ApplicationUser> passwordHasher { get; set; }
   ```
   
   Paste this code inside OnModelCreating method
   ```C#
   base.OnModelCreating(modelBuilder);
   this.SeedUsers(modelBuilder);
   ```
   
   Paste this code below OnModelCreating method (NOT INSIDE)
   ```C#
   private void SeedUsers(ModelBuilder builder)  
   {
      string saUsername = "YOUR EMAIL";
      var curDate = DateTime.Now;


      //YOU CAN ADD MORE ROLE AS YOU WANT
      role1 = new IdentityRole() 
      { 
          Id = Guid.NewGuid().ToString(), 
          Name = "SystemAdmin", 
          ConcurrencyStamp = Guid.NewGuid().ToString(), 
          NormalizedName = "SYSTEMADMIN" 
      };

      role2 = new IdentityRole() 
      { 
          Id = Guid.NewGuid().ToString(), 
          Name = "User", 
          ConcurrencyStamp = Guid.NewGuid().ToString(), 
          NormalizedName = "USER" 
      };

      //ADD USER ADMIN
      saUser = new ApplicationUser()  
      {  
          Id = Guid.NewGuid().ToString(),
          UserName = saUsername,  
          Email = saUsername,
          NormalizedEmail = saUsername.ToUpper(),
          NormalizedUserName = saUsername.ToUpper(),
          FullName = "System Admin",
          LockoutEnabled = false,  
          ConcurrencyStamp = Guid.NewGuid().ToString(),
          EmailConfirmed = true,
          IsEnabled = true,
          CreatedDate = curDate,
          ModifiedDate = curDate
      };
      
      passwordHasher = new PasswordHasher<ApplicationUser>(); 
      var saPwdHashed = passwordHasher.HashPassword(saUser, "YOUR PASSWORD");  
      saUser.PasswordHash = saPwdHashed;

    
      userAdmin = new IdentityUserRole<string>() 
      { 
          RoleId = role1.Id,
          UserId = saUser.Id
      };


      //BUT MAKE SURE ADD THE ROLE INSIDE IDENTITY ROLE LIEK THIS IF YOU WANT TO ADD MORE ROLE
      builder.Entity<IdentityRole>().HasData(role1);
      builder.Entity<IdentityRole>().HasData(role2);
      builder.Entity<ApplicationUser>().HasData(saUser);  
      builder.Entity<IdentityUserRole<string>>().HasData(userAdmin);
   } 
   ```

3. Now, we gonna create migration schema. You need to type this command on your terminal and click enter :
   
   ```console
   dotnet ef migrations add CreateScheme
   ```
4. After the command has finished, you can see that a new folder has been created called Migrations
   
   > ![image](https://user-images.githubusercontent.com/47632993/148335992-f4301b00-ffb7-49c2-bf38-3596615fd149.png)

5. Then we gonna use this command to drop our database first (IT IS RECOMMENDED THAT YOU CREATE IDENTITY BEFORE CREATE OTHER DATABASE TABLE BECAUSE ONCE YOU USE THIS COMMAND, YOUR DATABASE WILL BE DELETED. ONLY USE THIS CODE ON ***DEVELOPMENT ENVIRONMENT*** AND NOT ***PRODUCTION ENVIRONMENT***)

   ```console
   dotnet ef database drop
   ```
   
   If there is prompt, you just need to insert Y and click enter.
   
6. You can see that your database has been dropped/deleted
7. After that, we gonna use this command for create back all the table :

   ```console
   dotnet ef database update
   ```
   
8. You can see that your database has been created back
