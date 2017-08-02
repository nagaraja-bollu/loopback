# Create a simple API using Loopback/StrongLoop framework

### Introduction
 LoopBack is a highly extensible Node.js API framework from IBM. LoopBack APIs are capable of connecting devices, and integrate with Android and AngularJS SDKs for app creation. As for database compatibility, it supports Oracle, Mongo, and SQL. The team behind Express created it, so its built on the framework making it an easy API tool for Express pros.


##### It enables you to:

- Create dynamic end-to-end REST APIs with little or no coding.
- Access data from Oracle, MySQL, PostgreSQL, MS SQL Server, MongoDB, SOAP and other REST APIs.
- Incorporate model relationships and access controls for complex APIs.
- Use built-in push, geolocation, and file services for mobile apps.
- Easily create client apps using Android, iOS, and JavaScript SDKs.
- Run your application on-premises or in the cloud.

### Architecture
![](http://loopback.io/images/9830413.png)

### Create a Library API skeleton

Install the Loopback command line tools through npm:

`$ npm install -g loopback-cli`

This installs the lb command-line tool for scaffolding and modifying LoopBack applications. For more information, see [command-line tools](http://loopback.io/doc/en/lb2/Command-line-tools.html#commands "Loopback commands")

#### create a LoopBack application
```
$ lb
? What's the name of your application? ***library***
? Enter name of the directory to contain the project: library
   create library/
    info change the working directory to library
? Which version of LoopBack would you like to use? 3.x (current)
? What kind of application do you have in mind? empty-server (An empty LoopBack API, without any` `configured models or datasources)
Generating .yo-rc.json
```

After this node packages will installed by running `npm install`

Next steps:

  Change directory to your app
   ` $ cd library`

  Create a model in your app
   ` $ lb model`

  Run the app
   ` $ node .`


#### Lets add a datasource
```
lb datasource
? Enter the datasource name: library
? Select the connector for library: MongoDB (supported by StrongLoop)
? Connection String url to override other settings (eg: mongodb://username:password@hostname:port/database):
? host:
? port:
? user:
? password:
? database: library
? Install loopback-connector-mongodb@^1.4 Yes
```
You can [customize the mongodb datasource connection](https://loopback.io/doc/en/lb2/MongoDB-connector.html#customizing-mongodb-configuration-for-testsexamples "customize the mongodb datasource connection")

#### Lets add a model - "book"

```
lb model
? Enter the model name: book
? Select the datasource to attach book to: library (mongodb)
? Select model's base class PersistedModel
? Expose book via the REST API? Yes
? Custom plural form (used to build REST URL):
? Common model or server only? common
Let's add some book properties now.
```
#### Lets add the properties for the model

```
Enter an empty property name when done.
? Property name: title
   invoke   loopback:property
? Property type: string
? Required? No
? Default value[leave blank for none]:

Let's add another book property.
Enter an empty property name when done.
? Property name: author
   invoke   loopback:property
? Property type: string
? Required? No
? Default value[leave blank for none]:

Let's add another book property.
Enter an empty property name when done.
? Property name: genre
   invoke   loopback:property
? Property type: string
? Required? No
? Default value[leave blank for none]: 

Let's add another book property.
Enter an empty property name when done.
? Property name: price
   invoke   loopback:property
? Property type: number
? Required? No
? Default value[leave blank for none]:

Let's add another book property.
Enter an empty property name when done.
? Property name: isAvailable
   invoke   loopback:property
? Property type: boolean
? Required? No
? Default value[leave blank for none]:
```
Enter an empty property name to indicate you are done defining properties.

- The model generator will create two files which define the model in the application’s common/models: book.json and book.js.
- The JSON file specifies all metadata about the entity: properties, relations, validations, roles and method names.
- The JavaScript file is used to define additional behaviour, and to specify remote hooks to be called before or after certain operations (e.g., create, update, or delete). [Loopback documentation for simple api](http://loopback.io/doc/en/lb2/Create-a-simple-API.html "loopback documentation for simple api")

[![](https://raw.githubusercontent.com/nagaraja-bollu/loopback/master/Images/bookLoopbackProjectStructure.png)]()

The three main directories are:
- /server – Contains node application scripts and configuration files.
- /client – Contains .js, .html, .css, and all other static files.
- /common – This folder is common to both the server and the client. Model files go here.

#### Testing Your REST API in LoopBack GUI

API Explorer which is a built-in tool used as a client for the service.
In a separate window, start MongoDB with:
`$ mongod`

Run the application with:
`$ node .`

In your browser, go to http://localhost:3000/explorer/. You can see your entities with the list of operations available. 

[![](https://raw.githubusercontent.com/nagaraja-bollu/loopback/master/Images/apiexplorer.png)]()

### Conclusion
With LoopBack you are apt to write less code, compared to Express.js. It eliminates the need to write handlers for every endpoint, supports filters for easy search and pagination, stores code in separate model JS files, much more. Among the top advantages are prompt and easy generation, design and test of code for APIs. It allows you to focus on application-specific problems and business logic, and therefore build secure, well-documented, and high-performance APIs.

### References
http://loopback.io/doc/en/lb3/Getting-started-with-LoopBack.html

