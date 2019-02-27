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

## Useful links and inspiration

* [Azure Resource Manager template best practices](https://docs.microsoft.com/en-us/azure/azure-resource-manager/template-best-practices)
* [Azure Resource Manager Templates - Best Practices Guide](https://github.com/Azure/azure-quickstart-templates/blob/master/1-CONTRIBUTION-GUIDE/best-practices.md#best-practices)
* [Azure Resources](https://docs.microsoft.com/azure/templates/)
* [Creating a T-shirt size ARM template](https://thinkrethink.net/2016/09/06/creating-a-t-shirt-size-arm-template/)
* [5 Simple Steps to Get a Clean ARM Template ](http://www.frankysnotes.com/2018/05/5-simple-steps-to-get-clean-arm-template.html)
