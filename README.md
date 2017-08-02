# Loopback/StrongLoop

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
? What's the name of your application? library
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


#### Lets add a model
`lb`
