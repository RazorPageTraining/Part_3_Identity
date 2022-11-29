## Identity

- What is [Identity](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/identity?view=aspnetcore-5.0&tabs=visual-studio)?
- What is [Migrations](https://www.entityframeworktutorial.net/efcore/cli-commands-for-ef-core-migration.aspx)?

</BR>

| NO. | TITLE |
| ----------- | ----------- |
| 1 | [Introduction](https://github.com/RazorPageTraining/Part_1_Introduction) |
| 2 | [Installation](https://github.com/RazorPageTraining/Part_2_Installation) |
| 3 | [Net 5 CRUD](https://github.com/muhamaddarulhadi/RazorPage) |
| 4 | [How to run this project](#how-to-run-this-project) |
| 5 | [How to create RazorPage project](#how-to-create-razorpage-project) |
| 6 | [Packages](#packages)  |
| 7 | [Create Database](#create-database)  |
| 8 | [Create Identity](#create-identity)  |
| 9 | [Create Entity Models](#create-entity-models)  |
| 10 | [Setup DB connection on project](#setup-db-connection-on-project)  |
| 11 | [Database Migration](#database-migration)  |
| 12 | [Change caling](#change-calling)  |
| 13 | [Test login](#test-login)  |
| 14 | [Other Resources](https://github.com/muhamaddarulhadi/Training-RazorPage)  |


</BR>

***

#### How to run this project

1. Download this project and open your terminal or VS Code.
2. On your terminal type this command, but first you need to make sure you know where your project folder is. For my case, I put it on my desktop
   
   > ![image](https://user-images.githubusercontent.com/47632993/146669384-e9b4b021-077d-4de5-acc3-e8aced9863b2.png)
    
   ```console 
   code -r TrainingRazor
   ``` 
   > ![image](https://user-images.githubusercontent.com/47632993/204572344-4005b6a9-2cdc-468c-804a-6338a70b0972.png)

3. "TrainingRazor" name on this command is the folder name of the project. The name is depends on you.
4. System will open the project on your Code Editor.
5. Other than that, by using VS Code, you can just drag project folder on VS Code and and trust the author.     
6. If VS Code authorize you to insert some assets, just click ***Yes/Accept***    
7. [Back to Menu](#identity)
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
#### Packages

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
#### Create Database

1. Before we start to code, you need to create a database (DB).
2. You just need to create DB using SSMS that we install earlier.
3. Open your SSMS and create a new DB. ([How to use SSMS](https://docs.microsoft.com/en-us/sql/ssms/quickstarts/ssms-connect-query-sql-server?view=sql-server-ver15))
   > ![image](https://user-images.githubusercontent.com/47632993/146315651-d7d8889c-9e2a-4773-bbc7-33c091e8141a.png)

4. You will get your result like this after you finished create your DB

   > ![image](https://user-images.githubusercontent.com/47632993/204594174-6bb8fd43-56c6-4b60-8f99-f9212fa67642.png)

5. [Back to Menu](#identity)

***
#### Create Identity

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
#### Create Entity Models

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
       public class ApplicationUser : IdentityUser
       {
           [StringLength(500)]
           public string Name { get; set; }
       }

       public class CustPurchased
       {
           [Key]
           public int Id { get; set; }

           [ForeignKey("ApplicationUser")]
           public ApplicationUser Creator { get; set; }

           [ForeignKey("Product")]
           public int? ProductId { get; set; }
           public int? Quantity { get; set; }
           public Product Product { get; set; }
       }

       public class Product
       {
           [Key]
           public int Id { get; set; }

           [StringLength(500)]
           public string Name { get; set; }

           [Column(TypeName = "decimal(18, 2)")]
           public decimal Price { get; set; }
       }
   }
   ```

7. [Back to menu](#identity)

***
#### Setup DB Connection On Project

1. We gonna use local db server that we installed before.
2. On your project, open appsettings.json file and insert this ***(If your server name have slash " \ " , you need to insert double slash like this  " \\ " )***:

   ```JSON        
   "ConnectionStrings": {
       "DefaultConnection": "Server=YOUR_SERVER_NAME; Database=YOUR_DB_NAME; Trusted_Connection=True; MultipleActiveResultSets=True;"
    }
   ```    
    
   > ![image](https://user-images.githubusercontent.com/47632993/204600700-29dc36f6-0748-4ed5-ae83-39058cc62b21.png)

3. Save the file.

4. [Back to Menu](#identity)
</BR>

***
#### Database Migration

1. Before we create identity schema, we need to edit ApplicationDbContext.cs. This is what we call Code First and Not DB First
2. Open ApplicationDbContext.cs inside Data folder, and paste this source code :
   
   Insert this. ***Include Package***:
   
   ```C#
   using System;
   using Microsoft.AspNetCore.Identity;
   using TrainingRazor.Models;
   ```

   > ![image](https://user-images.githubusercontent.com/47632993/204602829-3c901ce2-e8c3-409d-877e-054eb8da5a2f.png)

   </BR>
   
   Edit this :
   > ![image](https://user-images.githubusercontent.com/47632993/204606138-75c0e4b2-5497-409a-be29-51aabc94edd5.png)

   </BR>
   
   Insert this. ***Declare variable***:
   
   ```C#
   private ApplicationUser saUserAdmin { get; set; }
   private ApplicationUser saUserCustomer { get; set; }
   private IdentityRole role1 { get; set; }
   private IdentityRole role2 { get; set;}
   private IdentityUserRole<string> userAdmin { get; set; }
   private IdentityUserRole<string> userCustomer { get; set; }
   private PasswordHasher<ApplicationUser> passwordHasher { get; set; }
   ```
   
   > ![image](https://user-images.githubusercontent.com/47632993/204606608-fe246d34-7fa7-40e9-806b-37812e2c02cb.png)
   
   </BR>
   
   Insert this. ***Call Data from Database***
   ```C#
   public DbSet<CustPurchased> CustPurchaseds { get; set; }
   public DbSet<Product> Products { get; set; }
   ```
   
   >![image](https://user-images.githubusercontent.com/47632993/204623373-b05bdf07-f032-4f54-90f5-f52c6db24453.png)

   </BR>
   
   Paste this code like this. ***Call method***
   ```C#
   protected override void OnModelCreating(ModelBuilder builder)  
   {  
       base.OnModelCreating(builder);
       this.SeedUsers(builder);
       this.SeedProducts(builder);
   }  
   ```
   
   > ![image](https://user-images.githubusercontent.com/47632993/204606727-6e5b7d59-3b62-4011-928c-7e05e0d67eeb.png)

   </BR>
   
   Paste this code below OnModelCreating method (NOT INSIDE). ***Method to create user.*** This is just to show to create user by using Code First concept. You Can add user by Page or Registration, but, I just want to show Migrations process.
   ```C#
   private void SeedUsers(ModelBuilder builder)  
   {
        string saUsernameAdmin = "YOUR EMAIL";
        string saUsernameCustomer = "YOUR EMAIL";

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
            Name = "Customer", 
            ConcurrencyStamp = Guid.NewGuid().ToString(), 
            NormalizedName = "CUSTOMER" 
        };

        //ADD USER ADMIN
        saUserAdmin = new ApplicationUser()  
        {  
            Id = Guid.NewGuid().ToString(),
            UserName = saUsernameAdmin,  
            Email = saUsernameAdmin,
            NormalizedEmail = saUsernameAdmin.ToUpper(),
            NormalizedUserName = saUsernameAdmin.ToUpper(),
            Name = "System Admin",
            LockoutEnabled = false,  
            ConcurrencyStamp = Guid.NewGuid().ToString(),
            EmailConfirmed = true,
        };

        //ADD USER CUSTOMER
        saUserCustomer = new ApplicationUser()  
        {  
            Id = Guid.NewGuid().ToString(),
            UserName = saUsernameCustomer,  
            Email = saUsernameCustomer,
            NormalizedEmail = saUsernameCustomer.ToUpper(),
            NormalizedUserName = saUsernameCustomer.ToUpper(),
            Name = "Customer 1",
            LockoutEnabled = false,  
            ConcurrencyStamp = Guid.NewGuid().ToString(),
            EmailConfirmed = true,
        };
        
        passwordHasher = new PasswordHasher<ApplicationUser>(); 

        var saPwdHashed1 = passwordHasher.HashPassword(saUserAdmin, "YOUR PASSWORD");  
        saUserAdmin.PasswordHash = saPwdHashed1;

        var saPwdHashed2 = passwordHasher.HashPassword(saUserCustomer, "YOUR PASSWORD");  
        saUserCustomer.PasswordHash = saPwdHashed2;
        
        userAdmin = new IdentityUserRole<string>() 
        { 
            RoleId = role1.Id,
            UserId = saUserAdmin.Id
        };

        userCustomer = new IdentityUserRole<string>() 
        { 
            RoleId = role1.Id,
            UserId = saUserCustomer.Id
        };


        //BUT MAKE SURE ADD THE ROLE INSIDE IDENTITY ROLE LIKE THIS IF YOU WANT TO ADD MORE ROLE
        builder.Entity<IdentityRole>().HasData(role1);
        builder.Entity<IdentityRole>().HasData(role2);
        builder.Entity<ApplicationUser>().HasData(saUserAdmin);
        builder.Entity<ApplicationUser>().HasData(saUserCustomer);  
        builder.Entity<IdentityUserRole<string>>().HasData(userAdmin);
        builder.Entity<IdentityUserRole<string>>().HasData(userCustomer);
   } 
   ```
   
   </BR>
   
   Paste this code below SeedUsers class method (NOT INSIDE). ***Method to create product***
   ```C#
   private void SeedProducts(ModelBuilder builder)  
    {
        builder.Entity<Product>().HasData( 
                new Product() { Id = 1, Name = "Logitech MX Mouse", Price = 345.12M },
                new Product() { Id = 2, Name = "Keycron Keyboard", Price = 295.23M },
                new Product() { Id = 3, Name = "Razer Lapotop", Price = 7345.69M },
                new Product() { Id = 4, Name = "Iphone 14 Pro Max", Price = 8798.12M },
                new Product() { Id = 5, Name = "Xiaomi Ear Buds", Price = 45.46M }
            );
    }
   ```

3. Delete all cs file inside Migrations folder.

4. Now, we gonna create migration schema. You need to type this command on your terminal and click enter :
   
   ```console
   dotnet ef migrations add CreateScheme
   ```
   
   > ![image](https://user-images.githubusercontent.com/47632993/204614790-218166ed-16a7-48d8-8d24-8769949b77e8.png)

   
5. After the command has finished, you can see that a new file called CreateScheme created inside the Migrations folder
   
   > ![image](https://user-images.githubusercontent.com/47632993/204617810-81c8f735-8221-4ce4-9879-b52dd8f9d2bd.png)
   
   It's okay if you have Multiple Migrations folder, but you can also cut the migrations file scheme with cs extension and paste into Migrations folder inside Data folder and delete the Migrations folder outside Data folder if you finished cut and paste.

6. After that, we gonna use this command for migrate Models that we created inside database :

   ```console
   dotnet ef database update
   ```
   
   > ![image](https://user-images.githubusercontent.com/47632993/204620690-f59b084f-689e-40da-90f8-45646cd404ea.png)
   
7. You can see that your database has been update.
   
   Before :
   > ![image](https://user-images.githubusercontent.com/47632993/204615739-b32339ab-26f2-456b-b7e8-d273d0c5c2eb.png)

   </BR>
   
   After :
   > ![image](https://user-images.githubusercontent.com/47632993/204620747-e92c0b45-c1e7-41b2-a30b-765f749f1b85.png)
   > ![image](https://user-images.githubusercontent.com/47632993/204620813-3741e2e5-220f-44b0-be5a-6313da5deb90.png)

</BR>

NOTE :

To drop database :

IT IS RECOMMENDED THAT YOU CREATE IDENTITY BEFORE CREATE OTHER DATABASE TABLE BECAUSE ONCE YOU USE THIS COMMAND, YOUR DATABASE WILL BE DELETED. ONLY USE THIS CODE ON ***DEVELOPMENT ENVIRONMENT*** AND NOT ***PRODUCTION ENVIRONMENT***

   ```console
   dotnet ef database drop
   ```
   
If there is prompt, you just need to insert Y and click enter.

</BR>

8. [Back to Menu](#identity)

</BR>

***
#### Change Calling

1. After migrations finished, don't run the project yet.
2. We need to change the calling IdentityUser to ApplicationUser each of every file that consist of IdenitityUser inside folder Account because we created a custom Identity entity class.
3. On your VS Code, click icon search 

   > ![image](https://user-images.githubusercontent.com/47632993/204628707-702d8cb0-a2d6-4ab0-8b25-a3a27019d259.png)

4. And put this word inside the input that the placeholder are ***Search***

   ```C#
   <IdentityUser>
   ```
   
   > ![image](https://user-images.githubusercontent.com/47632993/204629109-b2a1b117-edb1-421b-840e-c1c420fa3569.png)

5. As you can see, there's a lot of need to be changed.
6. But, don't worry, you just need to put this word inside the input that the placeholder are ***Replace***

   ```C#
   <ApplicationUser>
   ```
   
   > ![image](https://user-images.githubusercontent.com/47632993/204629579-9c8f1127-b7ff-4c7c-833b-1b507d6ddb7a.png)

7. After that, you just click this icon.
   
   > ![image](https://user-images.githubusercontent.com/47632993/204629725-7ced0bd1-1b49-420e-83ec-38eee3b72fd1.png)

8. Click the button Replace, and VS Code will do the replace part.

   > ![image](https://user-images.githubusercontent.com/47632993/204630019-6c8ef8be-9d56-4e19-a3a9-177cb603db76.png)

9. You will see all the file that have the word will be error, but dont worry, you just need to include this code on each and every file that has error.
   
   ```C#
   using TrainingRazor.Models;
   ```
   
   For example :
   > ![image](https://user-images.githubusercontent.com/47632993/204630629-fbfb0c4c-daad-4c0c-bd0d-84d0b18aeeed.png)

10. For file that have extension .cshtml , you need to put it like this :

    ```C#
    @using TrainingRazor.Models;
    ```
   
    For example :
    > ![image](https://user-images.githubusercontent.com/47632993/204631563-5ffbc597-cd9f-4b78-b6f8-81af1ef115f1.png)

11. If you still got a file that have error, don't worry, you can do it like this
   
     For example, you have a situation like this
     
     > ![image](https://user-images.githubusercontent.com/47632993/204632089-3e8fc530-cbef-4930-af78-a49313f0f68f.png)
      
     You can just change the IdentityUser to ApplicationUser 
     
     The Solution (No more errors because we change the variable declaration of IdentityUser to ApplicationUser) :
     
     ![image](https://user-images.githubusercontent.com/47632993/204632230-ef61c815-7dcf-4c8c-91a1-d57f6356be8c.png)
     
     </BR>

     Another example if you have a situation like this
     
     > ![image](https://user-images.githubusercontent.com/47632993/204633687-9542617e-9e10-4e42-a07b-56591c00af4a.png)


     Just change IdentityUser to ApplicationUser like this
     
     > ![image](https://user-images.githubusercontent.com/47632993/204633931-a5614a6a-2c63-44c2-a3f4-68a11c3c7159.png)


12. [Back to Menu](#identity)

</BR>

***
#### Test login

1. After finished everything, run this project by click F5 or click Run > Start Debugging
   
   > ![image](https://user-images.githubusercontent.com/47632993/204634746-ab622a2a-2c4b-4db8-ab0f-6a5b877e0e5e.png)

2. Your project will run on your browser
   
   > ![image](https://user-images.githubusercontent.com/47632993/204634990-e58e727a-5170-4f8b-94fb-f550e9304b64.png)

3. Insert your credentials ***(Login Email and Username that you set on migrations)*** and click the "Log in" button
4. When you succeed to login, you will be brought to this page.
   
   > ![image](https://user-images.githubusercontent.com/47632993/204635666-ec28e970-32cc-4499-bdcc-03675b0ec6ea.png)

5. [Back to Menu](#identity)
