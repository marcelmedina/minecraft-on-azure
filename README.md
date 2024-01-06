This is a repository teaching how to run Minecraft on Azure
===========================================================

Initially there is only a sample, for running Vanilla Minecraft on Azure Container Instances. If enough people like it, I will create a few more samples, for running modded versions, and maybe running it on AKS as well.

Huge thanks to itzg for the great container he publishes for running minecraft servers: [itzg/docker-minecraft-server](https://github.com/itzg/docker-minecraft-server)

To run it, just create a deployment on azure from a template, pointing it to the compiled arm template available, tweak the parameters, and you are done! Don't forget to accept the EULA, as it will crash the server if you don't.

To deploy the servers:

Vanilla: [![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmarcelmedina%2Fminecraft-on-azure%2Fmaster%2Fvanilla-aci.json)

## How to make it compatible with Bedrock Edition

This Minecraft server is Java-based, so it is not compatible with Bedrock Edition by default. However, there is a way to make it compatible, by using a proxy.

After the ACI container starts, go to the Azure Storage Account created, under File shares, go to the SMB `minecraftdata` and then to the `plugins` folder.

Upload both Geyser and Floodgate plugins (they are `jar files`), available at [GeyserMC](https://geysermc.org/download).

Restart the server, wait for things to load up, and then you will be able to connect to it using Bedrock Edition. (No need for additional configuration, I have covered that with the bicep changes).

## Playing from iPhone, Xbox or PS4?

Download [Bedrocktogether](https://bedrocktogether.net/) app, which works as a proxy and creates a "LAN" for playing with your friends.

If playing remotely, make sure your friends also have the same app.