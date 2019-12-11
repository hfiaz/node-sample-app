# Sparta Node Sample App

## Description

This app is intended for use with the Sparta Global Devops Stream as a sample app. You can clone the repo and use it as is but no changes will be accepted on this branch.

To use the repo within your course you should fork it.

The app is a node app with three pages.

### Homepage

``localhost:3000``

Displays a simple homepage displaying a Sparta logo and message. This page should return a 200 response.

### Blog

``localhost:3000/posts``

This page displays a logo and 100 randomly generated blog posts. The posts are generated during the seeding step.

This page and the seeding is only accessible when a database is available and the DB_HOST environment variable has been set with it's location.

### A fibonacci number generator

``localhost:3000/fibonacci/{index}``

This page has be implemented poorly on purpose to produce a slow running function. This can be used for performance testing and crash recovery testing.

The higher the fibonacci number requested the longer the request will take. A very large number can crash or block the process.


### Hackable code

``localhost:3000/hack/{code}``

There is a commented route that opens a serious security vulnerability. This should only be enabled when looking at user security and then disabled immediately afterwards

## Usage

Clone the app

```
npm install
npm start
```

You can then access the app on port 3000 at one of the urls given above.

## Tests

There is a basic test framework available that uses the Mocha/Chai framework

```
npm test
```

The test for posts will fail ( as expected ) if the database has not been correctly setup.

## vagrant

To create the environment you need to follow these steps:

1. Install Oracle VM VirtualBox (https://www.virtualbox.org/wiki/Download_Old_Builds_5_2)

2. Install Vagrant (https://releases.hashicorp.com/vagrant/) Version 2.2.5 / vagrant_2.2.5_x86_64.msi

3. Install Git Bash (https://git-scm.com/downloads)

4. Navigate to the git repository you have cloned in Git Bash

5. type "vagrant up"

6. If you get this error:

    Stderr: VBoxManage.exe: error: VT-x is not available (VERR_VMX_NO_VMX)

   You have to stop Hyper-V process in Windows

   Run command prompt as administrator and type

    bcdedit /set hypervisorlaunchtype off

  7. type "vagrant ssh"

  8. You are now in the Ubuntu environment

  9. 
