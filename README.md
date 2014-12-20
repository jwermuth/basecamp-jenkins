basecamp-jenkins
================

This repository contains the parts of a local Jenkins installation that are under version control.

In the hour of writing, some of the things under version control are the plugins installed and a job that scans this repository for changes, installs them and restarts Jenkins. This allows central configuration of multiple installations



#User Stories:
As an Administrator I want to change Jenkins configuration and have those changes pushed to all clients 

Backlog:
As a Developer I want to synchronize my configuration with the central repository without killing running Jobs
