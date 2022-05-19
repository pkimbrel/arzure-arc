## Required files

Create file `service-principal.properties` to hold the automation principal credentials.

```
clientId=<client-id>
secret=<secret>
```

## Supporting tools

* **doctl** - Digital Ocean CLI - requires DO authentication
* **azure-cli** - Azure CLI - requires Azure authentication

## Scripts

* **create** - Builds a DO droplet with script that registers with Azure Arc
* **list-machines** - Lists registered machines and some convenient CLI options with the full ID baked in
* **ssh-do** - Direct Digital Ocean SSH (assuming DO private key exists) to the most recently created droplet
* **tear-down** - Destroys all DO resources (does not unregister devices, yet)
* **update** - Updates the 'azauth' script on the most rescently created droplet

## azauth

This is a script that is deployed to the machine to generate an access token.  It's currently hard coded for an Azure Key Vault audience.