
### Qu'est-ce que l'ASP.NET Core ?
[ASP.NET Core] (https://www.dotnettricks.com/training/masters-program/aspnet-core) n'est pas une version améliorée d'ASP.NET. ASP.NET Core est une réécriture complète qui fonctionne avec le cadre .net Core. Il est beaucoup plus rapide, configurable, modulaire, évolutif, extensible et prend en charge plusieurs plates-formes. Il peut fonctionner à la fois avec le cadre .NET Core et .net via le cadre standard .NET. Il est le mieux adapté pour développer des applications basées sur le cloud telles que les applications web, les applications mobiles et les applications IoT.
ASP.NET Core a été principalement conçu pour rendre la partie la plus importante des composants ASP.NET sous le concept apprendre et le cadre composer où les composants ASP.NET précédents ont été libérés sous une variété de licences différentes périodiquement, Le cadre ASP.NET Core est un cadre complètement open-sourced. En dehors des autres parties du cadre des bibliothèques du cadre .NET, l'ASP.NET Core est principalement conçu à partir de zéro pour être la plate-forme agnostique qui fonctionne de manière transparente. Il permettra aux applications ASP.NET Core d'être déployées sur diverses plates-formes ou systèmes d'exploitation tels que les serveurs basés sur macOS ou Linux ou certains appareils.

### Quelles sont les fonctionnalités fournies par ASP.NET Core ?

Voici les fonctionnalités de base fournies par ASP.NET Core
- Supports intégrés pour l'[injection de dépendances] (https://www.dotnettricks.com/learn/dependencyinjection)
- Supports intégrés pour le cadre de journalisation et il peut être extensible.
- Introduction d'un nouveau serveur web rapide et multiplateforme - Kestrel. Ainsi, une application web peut fonctionner sans IIS, Apache, et Nginx.
- Plusieurs méthodes d'hébergement sont supportées
- Il supporte la modularité, donc le développeur doit inclure le module requis par l'application. Cependant, le cadre [.NET Core fournit également le méta-paquet qui inclut les bibliothèques] (https://www.dotnettricks.com/learn/netcore).
- Supports de la ligne de commande pour la création, la construction et l'exécution de l'application
- Il n'y a pas de fichier web.config. Nous pouvons stocker la configuration personnalisée dans un fichier appsettings.json.
- Il n'y a pas de fichier Global.asax. Nous pouvons maintenant enregistrer et utiliser les services dans la classe de démarrage
- Il a un bon support pour la programmation asynchrone
- Supporte WebSocket et SignalR
- Fournit une protection contre CSRF (Cross-Site Request Forgery)

### Quels sont les avantages d'ASP.NET Core par rapport à ASP.NET ?
L'ASP.NET Core présente les avantages suivants par rapport à l'ASP.NET :

- Il est multiplateforme, il peut donc être exécuté sur Windows, Linux et Mac.
- Il n'y a pas de dépendance à l'installation du framework car toutes les dépendances requises sont livrées avec notre application
- ASP.NET Core peut traiter plus de demandes que l'ASP.NET.
- Plusieurs options de déploiement disponibles avecASP.NET Core

### Qu'est-ce que la classe de démarrage dans ASP.NET Core ?

La classe de démarrage est le point d'entrée de l'application ASP.NET Core. Chaque application .NET Core doit avoir cette classe. Cette classe contient les éléments liés à la configuration de l'application. Il n'est pas nécessaire que le nom de la classe soit "Startup", cela peut être n'importe quoi, nous pouvons configurer la classe de démarrage dans la classe Program.

```csharp
public class Program {
	public static void Main(string[] args) {
		CreateWebHostBuilder(args).Build().Run();
	}
	public static IWebHostBuilder CreateWebHostBuilder(string[] args) => WebHost.CreateDefaultBuilder(args).UseStartup<TestClass>();
}
```