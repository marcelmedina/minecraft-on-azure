This is a repository teaching how to run Minecraft on Azure
===========================================================

Initially there is only a sample, for running Vanilla Minecraft on Azure Container Instances. If enough people like it, I will create a few more samples, for running modded versions, and maybe running it on AKS as well.

Huge thanks to itzg for the great container he publishes for running minecraft servers: [itzg/docker-minecraft-server](https://github.com/itzg/docker-minecraft-server)

To run it, just create a deployment on azure from a template, pointing it to the compiled arm template available, tweak the parameters, and you are done! Don't forget to accept the EULA, as it will crash the server if you don't.

To deploy the servers:

Vanilla: [![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmarcelmedina%2Fminecraft-on-azure%2Fmaster%2Fvanilla-aci.json)
