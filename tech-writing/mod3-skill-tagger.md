<a name = "top"></a> A technical writing sample 
#Mod3 Skill Tagger
###A guide to running Mod3 Skill Tagger

####Overview
The following instructions introduce you to Mod3 Skill Tagger, a program that enables you to add job and course skills on the Metal and Iron listings. This skill tagger lives in experimental on Mod3. It is configured to read from Metal’s DBstore directly. Run this script to get a csv output of all currently active postings, with skills applied by the script’s logic emailed to you. Only postings with a blank skill field will be populated. A new column (“auto-tagged”) indicates whether it has already been manually tagged or not, and if so, populates the field with what the skill tagger would have tagged the listing with. 

To understand these instructions, you need an uquity instance and basic familiarity with Mac/UNIX terminal.

####Best use
Export data from Metal and analyze manually tagged skills vs. auto-tagged skills. Autotag for manual bulk uploads by Metal team until new feature is ready. Play with logic in code to try new job tagging strategies against current Metal data. 

###How to Use Mod3 Skill Tagger
* Click on your Finder icon, select Applications, select Utilities, then Terminal.
**How to Connect to your uquity instance.** To access the skill tagger on Mod3, first connect to your uquity instance.

* ssh into your uquity instance 

	`$ ssh username-uquity.dls`

* Call prodaccess to access and run the script and access DBstore in Mod3.

   `$ prodaccess`   

* Create CitC, client in the cloud (See CitC for instructions)

   This creates a local directory tree at `/mod/src/cloud/<ldap>/<yourclient>/mod3` and goes to this directory

* From your browser, navigate to the mod3 cloud IDE:

   `go/ide`  or  `cider.corp.mod.com`

* Create a new workspace

* Search for ‘mod_skill_tagging’ and navigate to ‘skill_tagging.py’

* Edit the sender and recipient flags in this script on lines 39 and 41, and replace the email text on line 63 with your own email.

* From Terminal, change directory to the script on mod3/experimental

   enter:	
   
   `$ cd /mod/src/cloud/<username>/<citc_client>/mod3/experimental/mod_skill_tagging`

* Enter your username and name of citc client in place of ‘username’ and ‘citc_client’

* Run script:

  * enter:

   `$ blaze build //experimental/mod_skill_tagging/skill_tagging`

  * then enter: 

   `$ blaze run //experimental/mod_skill_tagging/skill_tagging`

* An email containing the csv output of all currently active postings, with skills applied by the script’s logic has now been sent to you.
