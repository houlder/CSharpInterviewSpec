## ASP.NET

### Qu'est-ce que ASP.NET ? IIS ?

- ASP.Net est une spécification de Microsoft qui est utilisée pour créer des applications et des services Web. Il fait partie du ".Net framework". Vous pouvez créer des applications ASP.Net dans la plupart des langages compatibles .Net comme Visual Basic, C#, etc. ASP.Net offre de bien meilleures performances que les langages de script.

- IIS est l'abréviation de Internet Information Services. Il a été créé par Microsoft pour fournir des services Internet aux applications Web ASP.NET.

### Qu'est-ce que la section appSettings du fichier web.config ?

Le bloc appSettings du fichier web.config définit les valeurs définies par l'utilisateur pour l'ensemble de l'application.

Par exemple, dans l'extrait de code suivant, la section ConnectionString spécifiée est utilisée dans tout le projet pour la connexion à la base de données :

```xml
<configuration>
    <appSettings>
        <add key="ConnectionString" value="server=local ; pwd=password ; database=default" />
    </appSettings>
```

### Quelle est la différence entre un contrôle HtmlInputCheckBox et un contrôle HtmlInputRadioButton ?

Dans le contrôle HtmlInputCheckBox, la sélection de plusieurs éléments est possible, alors que dans les contrôles HtmlInputRadioButton, nous ne pouvons sélectionner qu'un seul élément dans le groupe d'éléments.

#### Quels espaces de noms sont nécessaires pour créer une application localisée ?

```csharp
    using System.Globalization
    using System.Resources
```

### Qu'est-ce qu'un cookie ? Listez les différents types de cookies en ASP.NET

Un cookie est un petit élément d'information qui est stocké côté client. Il existe deux types de cookies :
- Cookie de session/temporaire : valable pour une seule session (Réside sur la machine du client pour une seule session jusqu'à ce que l'utilisateur ne se déconnecte pas).
- Cookie persistant : valable pour plusieurs sessions (Réside sur la machine d'un utilisateur pendant une période spécifiée pour son expiration, comme 10 jours, un mois, et jamais.)

### Qu'est-ce que RedirectPermanent en ASP.Net ?

RedirectPermanent effectue une redirection permanente de l'URL demandée vers l'URL spécifiée. Une fois la redirection effectuée, il renvoie également des réponses 301 Moved Permanently.


### Expliquez la sécurité basée sur les rôles ?

La sécurité basée sur les rôles est utilisée pour mettre en œuvre une sécurité basée sur les rôles attribués aux groupes d'utilisateurs dans l'organisation.

Nous pouvons alors autoriser ou refuser des utilisateurs en fonction de leur rôle dans l'organisation. Windows définit plusieurs groupes intégrés, dont les Administrateurs, les Utilisateurs et les Invités.

```xml
<AUTORISATION>
    <autorisation>
        <allow roles="Domain_Name\Administrators"/> < !-- Autoriser les administrateurs dans le domaine. -- >
        <deny users="*"/> < !-- Interdire toute autre personne. -- >
    </authorization>
```

### Comment empêcher le navigateur de mettre en cache une page ASPX ?

Nous pouvons SetNoStore sur l'objet HttpCachePolicy exposé par la propriété Cache de l'objet Response :

```csharp
    Response.Cache.SetNoStore () ;
    Response.Write (DateTime.Now.ToLongTimeString ()) ;
```

### Qu'est-ce que ViewState ?

ViewState est une fonctionnalité d'ASP.NET permettant de stocker les valeurs d'une page avant qu'elle ne soit soumise au serveur. Après l'affichage de la page, les données de ViewState sont restaurées.


### Combien de temps les éléments de ViewState existent-ils ?

Ils existent pour la durée de vie de la page actuelle.


### Quelle est la différence entre Server.Transfer et Response.Redirect ?

Dans **Server.Transfer**, le traitement des pages est transféré d'une page à l'autre sans faire d'aller-retour vers le navigateur du client. Cela permet d'obtenir une réponse plus rapide avec un peu moins de surcharge pour le serveur. La liste de l'historique des url du client ou l'url actuelle du serveur ne sont pas mises à jour en cas de Server.Transfer.

**Response.Redirect** est utilisé pour rediriger le navigateur de l'utilisateur vers une autre page ou un autre site. Il effectue un aller-retour vers le client où le navigateur du client est redirigé vers la nouvelle page. La liste de l'historique du navigateur de l'utilisateur est mise à jour pour refléter la nouvelle adresse.

### Quelle est la différence entre l'authentification et l'autorisation ?

L'authentification est un processus d'identification de l'utilisateur alors que l'autorisation est utilisée pour vérifier les droits d'accès d'un utilisateur identifié.

### Quel objet encapsule l'état ou les données d'un utilisateur ?

- Session object ou l'objet de session.


## ASP.NET Core

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

### Décrire l'injection de dépendances.

L'injection de dépendances est un modèle de conception utilisé comme technique pour réaliser l'inversion de contrôle (IoC) entre les classes et leurs dépendances.
ASP.NET Core est livré avec un cadre intégré d'injection de dépendances qui rend les services configurés disponibles dans toute l'application. Vous pouvez configurer les services à l'intérieur de la méthode ConfigureServices comme ci-dessous.
    
```csharp
services.AddScoped() ;
```

Un service peut être résolu en utilisant l'injection de constructeur et le cadre DI est responsable de l'instance de ce service au moment de l'exécution. Pour en savoir plus, consultez le site ASP.NET Core Dependency Injection (en anglais).

### Comment lire les valeurs du fichier Appsettings.json ?

Vous pouvez lire les valeurs du fichier appsettings.json en utilisant le code ci-dessous.

```csharp
classe Test{
	// nécessite l'utilisation de Microsoft.Extensions.Configuration ;
 	private readonly IConfiguration Configuration ;
    public TestModel(IConfiguration configuration) {
        Configuration = configuration ;
    }
	/*public void ReadValues(){
		var val = Configuration["key"] ; // lecture des valeurs directes des clés
		var name = Configuration["Employee:Name"] ; // lecture des valeurs complexes
	}*/
}
```
Le fournisseur de configuration par défaut charge d'abord les valeurs de appsettings.json, puis celles du fichier appsettings.Environment.json.
Les valeurs spécifiques à l'environnement remplacent les valeurs du fichier appsettings.json. Dans l'environnement de développement, les valeurs du fichier appsettings.Development.json remplacent les valeurs du fichier appsettings.json, il en va de même pour l'environnement de production.
Vous pouvez également lire les valeurs du fichier appsettings.json en utilisant le modèle d'options décrit Lire les valeurs du fichier appsettings.json. 


### Comment ASP.NET Core sert-il les fichiers statiques ?

Dans ASP.NET Core, les fichiers statiques tels que les CSS, les images, les fichiers JavaScript, le HTML sont servis directement aux clients. Le modèle ASP.NET Core fournit un dossier racine appelé wwwroot qui contient tous ces fichiers statiques. La méthode UseStaticFiles() dans Startup.Configure permet de servir les fichiers statiques au client.
Vous pouvez servir des fichiers en dehors de ce dossier webroot en configurant le Static File Middleware comme suit.

```csharp
app.UseStaticFiles(new StaticFileOptions
    {
        FileProvider = new PhysicalFileProvider(
            Path.Combine(env.ContentRootPath, "MyStaticFiles")), // MyStaticFiles est un nouveau dossier
        RequestPath = "/StaticFiles" // Il s'agit du chemin demandé par le client.
    }) ;
// maintenant vous pouvez utiliser votre fichier comme ci-dessous
<img src="/StaticFiles/images/profile.jpg" class="img" alt="Une rose rouge" />
 // profile.jpg est une image dans le dossier MyStaticFiles/images.
```


### Explication de la gestion des sessions et des états dans ASP.NET Core

Comme nous le savons, HTTP est un protocole sans état. Les requêtes HTTP sont indépendantes et ne conservent pas les valeurs de l'utilisateur. 
Il existe différentes façons de conserver l'état de l'utilisateur entre plusieurs requêtes HTTP.

- Cookies
- État de la session
- Données temporaires
- Chaînes de requête
- Champs cachés
- Items de HttpContext
- Cache