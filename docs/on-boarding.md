# On-boarding a new customer

1. Create new Azure subscription (ask Basefarm to do this as it is a new CSP subscription)
1. Setup access
    1. Add AD groups _June Azure Admins_ to role _Owner_
    1. Add AD groups _June Developers_ to role _Contributor_
1. Create a resource group for the customer
    ```bash
    az group create --name <customershortname> --location westeurope
    ```
    
1. Deploy Comet
    ```bash
    az group deployment create --resourcegroup <customershortname> --template-file .\comet.json 
    ```

## Azure setup

1. Create _Service Prinicpal_ for Octopus Deploy

```bash
az ad sp create-for-rbac -n 'https://<customershortname>.junecomet.com'
Retrying role assignment creation: 1/36
Retrying role assignment creation: 2/36
Retrying role assignment creation: 3/36
Retrying role assignment creation: 4/36
Retrying role assignment creation: 5/36
{
  "appId": "fdab87e2-5434-4af1-8d34-76a371674b77",
  "displayName": "hayu.junecomet.com",
  "name": "https://hayu.junecomet.com",
  "password": "8297138e-f281-407e-a9cf-9511beb4c522",
  "tenant": "juneab.onmicrosoft.com"
}
```
