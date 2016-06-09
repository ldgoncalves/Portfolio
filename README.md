# Portfolio

This is a rough draft of my portfolio website at Full Sail University.

##Server Architecture

* Ubuntu 12.04.5 LTS
* Apache/2.2.22 (Ubuntu)
* MySQL Ver 14.14
* PHP 5.3.10

##Deployment Plan

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


  
  
