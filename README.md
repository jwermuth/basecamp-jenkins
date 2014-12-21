basecamp-jenkins
================

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
    
and import the newly created project into eclipse

## Using ssh

If you want to use ssh for you own clone of the Jenkins configuration, put 

    git@github.com:jwermuth/basecamp-vagrant.git
    
into

    .git/config
    
e.g.

    [remote "origin"]
	url = git@github.com:jwermuth/basecamp-vagrant.git

