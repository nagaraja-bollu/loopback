# Create a simple API using Loopback framework

### Introduction
Currently, we will write more lines of code for CRUD operations, connections to datasources in Nodejs,  which usually take more time and it may effect on productivity. There are many Nodejs frameworks are available for API development to increase productivity and performance. Among the frameworks,  LoopBack from IBM is a highly extensible Node.js API framework . The team behind Express has created it and it has feature of Android, Angularjs SDKs integration for app creation. It also has database compatibility, supports relational and non-relational databases. Developers can create end-to-end REST APIs with less or no coding.

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
With LoopBack you can write less code, compared to Express.js. It eliminates the need to write handlers for every endpoint, supports filters for easy search and pagination, stores code in separate model JS files. It allows you to focus on application related problems and business logic, and therefore build secure, well-documented, and high-performance APIs which increase productivity as well.

### References
http://loopback.io/doc/en/lb3/Getting-started-with-LoopBack.html

