# Code-First Relational Database

## SQL elastic pool
A pool of databases. Allows a user to manage a single execution point for several databases. This is useful when managing several databases with the same schema.

## Pricing
Pricing is in terms of DTUs. DTU stands for Database Transaction Unit. You can [read](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-service-tiers-dtu) about DTUs to figure out how many DTUs you will likely need.

## Connecting server with web app
See the server page in the azure portal. Go under "Connection strings", and select ADO.NET, in this case. Copy-paste the authentication code. In visual studio, go to your app configuration file. Replace {password} with your password. Use Entity Framework.

Write the following classes: Orders, OrderId, and Details.

Go to the NuGut Package manager, and "enable-migrations" to connect code in VS to azure maps server.

By default, Azure is configured to modify the database using Azure Portal. To modify the database using Visual Studio, you need to go to the "Firewall settings" in azure portal, for your server. Add a client IP. Then, you will be able to run "update-database -verbose" in visual studio, NuGut package manager console.

In Visual Studio, go to the "View" menu. Right click, and select "Add SQL server". Use the same username and passwords, for your database. Find the Orders and Details tables under "SQL server" > server > "Databases" > "Tables". Right click on the tables, and select view data.

### Summary of general process, not strictly in order
- Make a server in azure
- Update configuration file in visual Studio
- Authenticate to the database
- migrate the database
- write code to manipulate the database
- test your code on the tables

## Needed package managers
- Entity Framework Core

# Blob storage

## Storage account
Store large amounts of unstructured data. Such as, texts and images. Access the data by HTTP.

Common applications of Blob Storage databases:
- Stream videos
- Serve images to a browser
- Store and restore data for backup
- Augment relational data with images

Key Points of Blob storage
- Start with a Storage Account
- A storage account can have any number of containers, but each container must be associated with a storage account. Containers must be labeled or named with all lower-case letters.
- A container can have any number of blobs, but each blob must be held in a container.

### Three Essential types of blobs:
1. Block blobs: usually for documents and media
2. Append blobs: log files
3. Page blobs: Operating systems within VMs

### Access tiers
1. Hot: For data you're accessing frequently
2. Cool: For data you're accessing less frequently

### Replication
- Local-redundant storage (LRS): replicate data a number of chosen times, but local to the chosen area of your storage Account
- Zone-redundant storage (ZRS): Same as LRS, but with a wide dispersion of the area
- Geo-redundant storage (GRS): Same as LRS and ZRS, but with dispersion over the entire world
- Read-access geo-redundant storage (RA-GRS): Same as GRS, but allows immediate access to the data. This is the safest option.

### Sample
Go [here](https://docs.microsoft.com/en-us/samples/azure-samples/storage-blob-dotnet-getting-started/storage-blob-dotnet-getting-started/) and download the zip file. Right click and select "Unlock" in the properties of the zip file, to tell Visual Studio that these files are safe to use. Walk through a sample of how to utilize blob storage in an application. In the config file, comment the connection to the emulator.

Uncomment the connection to an azure account, and use your blob storage account name and blob storage key. Look at how the storage account is created using the StorageConnectionString. Then, we can make a container and a blob.

Demo methods:
- PrintServiceClientProperties
- GetServiceStatsForSecondaryAsync
- ContainerListingDetails
- ListAllContainers
