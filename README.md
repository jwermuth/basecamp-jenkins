#Basecamp-jenkins


## Setting up mail

Once your jenkins is up and running:

* Go to localhost:8080/configure. 
* Fill out
** 'System Admin e-mail address' under Jenkins Location
** The fields under the 'E-mail Notification' section
** To use your own gmail account (only works with 2-factor authentication), under the 'E-mail Notification' section:
*** SMTP server: smtp.gmail.com
*** Click 'Advanced'
*** Check 'Use SMTP Authentication'
*** User Name: your gmail username
*** Password: your gmail password (application-specific if you use 2-factor authentication)
*** Check 'Use SSL'
*** add '465' to the text box labelled 'SMTP Port'


Configuration for shared, local Jenkins instance..

## Reverse git strategy

To avoid checking in everything in Jenkins, I am using a reverse git strategy, like this:

- .gitignore has a "*" in it, ignoring everything
- if I want to have a file under version control, I force it in with
    
    git add -f file
    
This means you have to explicitly add a new job to version control, e.g.
    
    git add -f jobs/my_job/config.xml


## Using eclipse

If you want to use eclipse to edit the files, you can run
    
    ./gradlew eclipse
    
and import the newly created project into eclipse.

## Using ssh

If you want to use ssh for you own clone of the Jenkins configuration, put 

    git@github.com:jwermuth/basecamp-vagrant.git
    
into

    .git/config
    
e.g.

    [remote "origin"]
	url = git@github.com:jwermuth/basecamp-vagrant.git



#User Stories

A simple way of keeping track of whats implemented and whats not

## Implemented

* As an Administrator I want to change Jenkins configuration and have those changes pushed to all clients
* As a Developer I want to version control my CI so I can recreate my CI system

##Backlog

* As a Developer I want to synchronize my configuration with the central repository without killing running Jobs

