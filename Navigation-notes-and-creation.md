## Links to include inside the book

* [OZP Ansible](https://github.com/aml-development/ozp-ansible)

* [Piwik-Export](https://github.com/aml-development/piwik-export)

* [Demo-Auth-Service repo](https://github.com/aml-development/demo-auth-service)

* [Piwik Software](https://github.com/aml-development/piwik)

* Piwik plugins
  * [UserCreatedWebsite](https://github.com/aml-development/piwik-plugin-UserCreatedWebsite)
  * [LoginPKI](https://github.com/aml-development/piwik-plugin-LoginPKI)
  * [ClientCertificates](https://github.com/aml-development/piwik-plugin-ClientCertificates)
  * [AppsMallTheme](https://github.com/aml-development/piwik-theme-AppsMallTheme)

* [Chart.js library docs](http://www.chartjs.org/docs/)

* [Actual Piwik Website](https://piwik.org/)

* [Piwik FAQ](https://piwik.org/faq/)






## Piwik Walkthrough

* connection to developer setup
  * add in "chmod" and "chown" for one of the steps

* pictures of developing setup
  * pictures of development & latest piwik
  * link to piwik docs and helpful websites

* steps to add plugins
  * ~~warnings for upgrading piwik and possible errors~~
  * ~~steps on how to downgrade piwik~~

* looking at plugins presen
  * how to add new plugins
  * how to make new plugins
    * links to documentation on how to create new plugins from terminal
  * how to identify existing plugins
  * all about plugins and the dashboard
  * plugins and their API folders:
    * how to navigate the APi folders and find correct codesheets/files
  * when to use plugins and when to hit the backend
    * piwik tracks events where as backend stores database data (dynamic vs static)

* ~~Map of how Piwik, mySQL, AML, and Piwik-Export are linked/chained together:~~
  * ~~Chain of dependencies~~

* Piwik-Stats.js, the in's ad out's
  * What is it for? diff between piwik-stats and app.js
  * API codes adn piwik-stats
  * piwik-stats to stats.ejs
  * piwik-stats connected to piwik
    * explain what is piwik
    * explain how the piwik-stats is pulling from piwik and how they are connected.
  * What can be done in piwik-stats

* explain the need for mock environment
  * explain piwik-charts/export
  * explain charts.js library
    * link to thier docs and how to use sample codes

* how to go about certain coded tasks
  * such as import some piwik table
  * where the charts are made (chartData)
    * actually, just explain each file and file purpose

* further update on each of necessary repos
  * explain in doc how each contribute to environments
  * explain AML backend for piwik
  * explain use of demoAuth in piwik
  * explain the certs for the piwik usage

* mentions common flaws
  * things being currently updated

* mention the current versions of Piwik, AppsMall, mySQL, Chart.js, other libraries, etc. and explain how they are in current recoding to incorporate the newer updated versions of each.

* ~~mention about seeing separate documentation for staging environment~~

* edit code to describe what is doing what

* explain the certian areas in piwik that others may not completely understand
  * such as: open paraentheses in the piwik search keywords and what they mean. 






## About AML Metrics and Goals

The OZONE Platform activetly uses a metrics system to gather analytical data on how the project is being used. This analytical data is collected within the software called [Piwik](https://piwik.org/). Piwik is a free and open-source analytics platform that is flexible to meet the needs of the OZONE project while also maintaining the security of the users.

While Piwik collects the data of the events produced in the AppsMall marketplace, the current process of sharing the collection is through manual creation and redistribution of spreadsheets. The goal of the [Piwik-Export](https://github.com/aml-development/piwik-export) site is to replace this manual process with a more dynamic resource that displays all of the data in one place and with no extra effort. The Piwik-Export site is coded to gather the Piwik data and display it in neat and organized formats for users outside of the OZONE project to see the data, allow csv export functionality, and create reactive charts made from the data.


### Chain of Dependencies

When involving Piwik-Export, the repo has multiple dependecies on other repos. In order for Piwik-Export to run, Piwik itself must be installed and running on the machine, and for Piwik to run and gather data, the OZP-Ansible must also be configured. Reason being is that the Piwik-Export website (called Piwik-Charts on staging) is directly used to pull Piwik data over into a website that is easier to view and does not require as many permissions to access versus the actual Piwik website. Without both the ansible and the actual Piwik, the export site will have nothing to display. 

* insert picture here 

During the creation fo the Piwik software, there should be a prompt to create a mySQL database, or use one already created. Go through with either.

If there are any questions on or if the user still requires setting up the local metrics environment, please see [Developer Metrics Setup](https://github.com/aml-development/ozp-documentation/wiki/Developer_Metrics_Setup) page in the ozp-documentation wiki.



## Starting Out Development


