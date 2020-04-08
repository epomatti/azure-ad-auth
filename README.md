# Azure AD Form-Based Auth

Form-based authentication with Azure AD.

### Steps to run this application

1. Create an Azure AD using the portal

2. Create a user:

```sh
az ad user create \
    --display-name "User 1" \
    --password "Str0ngP@ssw0rd" \
    --user-principal-name user1@<yourfulldomain>
```

3. Register your application:

```sh
az ad app create \
    --display-name mywebapp \
    --reply-urls http://localhost:5000/signin-oidc
    --oauth2-allow-implicit-flow true
```

4. Edit the `appsettings.json` and edit with the application paremeters:

```
    "Domain": "",
    "TenantId": "",
    "ClientId": "",
```

5. Install .NET Core SDK

6. Run the app

```sh
dotnet restore
dotnet run
```

### MVC App

Command used to create the MVC App:

```sh
dotnet new mvc --auth SingleOrg \
    --client-id <client_id> \
    --tenant-id <tenant_id> \
    --domain <domain>
```