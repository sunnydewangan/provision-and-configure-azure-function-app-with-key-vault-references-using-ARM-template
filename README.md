# Provision and Configure Azure Function App with Key Vault References using ARM Template

**Important: for detailed information, please use https://docs.microsoft.com/en-us/azure/app-service/app-service-key-vault-references**

This template creates an azure function app, storage account, key vault with an access policy and a key vault secret. It then configures key vault reference to an application setting.

Key Vault references can be used as values for Application Settings, allowing you to keep secrets in Key Vault instead of the site config. Application Settings are securely encrypted at rest, but if you need secret management capabilities, they should go into Key Vault.
To use a Key Vault reference for an application setting, set the reference as the value of the setting. Your app can reference the secret through its key as normal. No code changes are required.

When automating resource deployments through Azure Resource Manager templates, you may need to sequence your dependencies in a particular order to make this feature work. Of note, you will need to define your application settings as their own resource, rather than using a siteConfig property in the site definition. This is because the site needs to be defined first so that the system-assigned identity is created with it and can be used in the access policy.

Tags: Azure Key Vault, Key Vault, Secrets, Resource Manager, Resource Manager templates, ARM templates, Azure Function App

