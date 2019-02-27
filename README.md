# ARM Templates

## How to

Test deploy a linked template with a loop

```powershell

$templateUri='https://raw.githubusercontent.com/yooakim/arm-templates/master/templates/three-public-ips.json'

az group create -n testip -l westeurope
az group deployment create --resource-group testip --template-uri $templateUri

az network public-ip list -o table

az group delete --name testip --yes --no-wait
```

## Useful links

* [Azure Resources](https://docs.microsoft.com/azure/templates/)
