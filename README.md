# Portfolio

This is a rough draft of my portfolio website at Full Sail University.

##Server Architecture

* Ubuntu 12.04.5 LTS
* Apache/2.2.22 (Ubuntu)
* MySQL Ver 14.14
* PHP 5.3.10

##Deployment Plan

###Steps to deploy website

Create server live directory in */var/www/luanacodes.com*

Create server repository */var/repo/portfolio.git*

 **Create Repository**

 `cd /var
  mkdir repo && cd repo
  mkdir portfolio.git && portfolio.git
  git init --bare`

 **Hooks**

 `sudo su` in order to create the post-receive file using  `cat`.
 
  `cat > post-receive`
  
  And then type in the file to execute:
  
   `#!/bin/sh
    git --work-tree=/var/www/luanacodes.com --git-dir=/var/repo/portfolio.git checkout -f`
    
   To save press *control-d*, and in order to execute the file change permissions to:
    `chmod +x post-receive`
   
   Now check to see what user and group your repo is under. If portfolio.git is not under the correct user and/or group, change permissions using `chown` and `chgrp`.
    
 **Local Machine Setup**
 
 Now we are going to exit from the VPS `cd` into our project repo. From there we will configure the remote path to the portfolio.git repository.
 
 `git remote add live ssh://user@mydomain.com/var/repo/portfolio.git`
 
 Afterwards add and commit to Git and then:
 
 `git push live master`
 
 Congratulations! We have deployed the portfolio website! 
 
 For the final step, `sudo nano` into the server's virtual host file *000-default* and add the DocumentRoot to */var/www/luanacodes.com.*

Once initial deployment of the portfolio has been launched, here are the steps to continue adding additional features of the website. 

###Merge development branch into Master

One of the first steps of is to start merging the development branch into the master. Pull the remote master branch  to ensure the local master branch is up-to-date. Switch to the local master branch and from here pull the portfolio master branch to compare to the master on the remote deployment server.

If there is any inconsistencies and/or conflicts, resolve those issues in the branch. Save the modified files, commit and then pull the remote master branch. 

 Once conflicts are resolved, merge the new feature and resolve any issues by repeating the process in the second paragraph. 
  
  **Testing**
  
  Now it's to time to do some testing on the new feature! Make sure to test every aspect of the feature to ensure no errors are occurring. If it breaks, that means there is a flaw in the master and it's not ready to be pushed to the remote master on the server!
  
  Once tested and everything is running error free, it's time to push the new feature to the master.
  
###Version Numbering

When you commit for a new feature that is ready to merge into the master, it's important your message a version of the feature. So when discussing components or conflicts, it can be easily referred to it's version number. Numbering conventions should be as follows:
    * Version (dot) Production Release ++ (dot) Staged Release ++
    * Depending the new version, increase either the production release or the staged release by one.  
                
###Communicate with Team
Communicate with you team and notify them of the new release. If someone else is working with the code, collaborate how your new changes can merge with their new cheanges before promotion. 

###Staging

For staging, there needs to be a separate server to test new code and edits. Once we spin up the spin-up the staging server, we have complete the process of deployment and connected to our Github as shown in the instructions **Steps to deploy website**.

Once you're all set up, any branches you have been testing on, merge to master (follow steps in **Merge development branch into Master**) and push to the staging server to test if all code is functioning correctly. 

If all feature works and functionality hasn't been compromised, push to production/live server. 




  
  
