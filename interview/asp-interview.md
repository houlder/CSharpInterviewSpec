
## ASP.NET

### What is ASP.NET? IIS ?

- ASP.Net is a specification by Microsoft which is used to create web applications and web services. It is a part of ".Net framework". You can create ASP.Net applications in most of the .Net compatible languages like Visual Basic, C#, etc. ASP.Net provides much better performance than scripting languages.

- IIS stands for Internet Information Services. It is created by Microsoft to provide Internet-based services to ASP.NET Web applications.

### What is the appSettings Section in the web.config file?

The appSettings block in web config file sets the user-defined values for the whole application.

For example, in the following code snippet, the specified ConnectionString section is used throughout the project for database connection:

```xml
<configuration>
    <appSettings>
        <add key="ConnectionString" value="server=local; pwd=password; database=default" />
    </appSettings>
```

### What is the difference between an HtmlInputCheckBox control and an HtmlInputRadioButton control?

In HtmlInputCheckBoxcontrol, multiple item selection is possible whereas in HtmlInputRadioButton controls, we can select only single item from the group of items.

### Which namespaces are necessary to create a localized application?

```csharp
    using System.Globalization
    using System.Resources
```

### What is a cookie? Liste the different types in ASP.NET

A Cookie is a small piece of information which is stored at the client side. There are two types of cookie:
- Session/Temporary Cookie: valid for a single session (Resides on the client machine for a single session until the user does not log out.)
- Persistent Cookie: valid for multiple session (Resides on a user’s machine for a period specified for its expiry, such as 10 days, one month, and never.)

### What is RedirectPermanent in ASP.Net?

RedirectPermanent Performs a permanent redirection from the requested URL to the specified URL. Once the redirection is done, it also returns 301 Moved Permanently responses.


### Explain role based security?

Role Based Security used to implement security based on roles assigned to user groups in the organization.

Then we can allow or deny users based on their role in the organization. Windows defines several built-in groups, including Administrators, Users, and Guests.

```xml
<AUTHORIZATION>
    <authorization>
        <allow roles="Domain_Name\Administrators"/>  < !-- Allow Administrators in domain. -- >
        <deny users="*"/>                            < !-- Deny anyone else. -- >
    </authorization>
```

### How can we prevent browser from caching an ASPX page?

We can SetNoStore on HttpCachePolicy object exposed by the Response object’s Cache property:

```csharp
    Response.Cache.SetNoStore ();
    Response.Write (DateTime.Now.ToLongTimeString ());
```

### What is ViewState?

ViewState is a feature of ASP.NET to store the values of a page before it is submitted to the server. After posting the page, data from is ViewState is restored.


### How long the items in ViewState exists?

They exist for the life of the current page.


### What is the difference between Server.Transfer and Response.Redirect?

In **Server.Transfer** page processing transfers from one page to the other page without making a round-trip back to the client’s browser. This provides a faster response with a little less overhead on the server. The clients url history list or current url Server does not update in case of Server.Transfer.

**Response.Redirect** is used to redirect the user’s browser to another page or site. It performs trip back to the client where the client’s browser is redirected to the new page. The user’s browser history list is updated to reflect the new address.

### What is the difference between authentication and authorization?

Authentication is a process of identifying user whereas authorization is used to check the access rights of an identified user.

### Which object encapsulates state or data of a user?

- Session object.


## ASP.NET Nore

1. Qu'est-ce que l'ASP.NET Core ? (1pt)
2. Quelles sont les fonctionnalités fournies par ASP.NET Core ? (2pt)
3. Quels sont les avantages d'ASP.NET Core par rapport à ASP.NET ? (2pt)
4. Qu'est-ce que la classe de démarrage dans ASP.NET Core ? (1pt)