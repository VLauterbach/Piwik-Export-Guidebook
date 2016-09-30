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

* looking at plugins presen
  * how to identify existing plugins
  * all about plugins and the dashboard
  * plugins and their API folders:
    * how to navigate the APi folders and find correct codesheets/files

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

* edit code to describe what is doing what






## About AML Metrics and Goals

The OZONE Platform activetly uses a metrics system to gather analytical data on how the project is being used. This analytical data is collected within the software called [Piwik](https://piwik.org/). Piwik is a free and open-source analytics platform that is flexible to meet the needs of the OZONE project while also maintaining the security of the users.

While Piwik collects the data of the events produced in the AppsMall marketplace, the current process of sharing the collection is through manual creation and redistribution of spreadsheets. The goal of the [Piwik-Export](https://github.com/aml-development/piwik-export) site is to replace this manual process with a more dynamic resource that displays all of the data in one place and with no extra effort. The Piwik-Export site is coded to gather the Piwik data and display it in neat and organized formats for users outside of the OZONE project to see the data, allow csv export functionality, and create reactive charts made from the data.


### Chain of Dependencies

When involving Piwik-Export, the repo has multiple dependecies on other repos. In order for Piwik-Export to run, Piwik itself must be installed and running on the machine, and for Piwik to run and gather data, the OZP-Ansible must also be configured. Reason being is that the Piwik-Export website (called Piwik-Charts on staging) is directly used to pull Piwik data over into a website that is easier to view and does not require as many permissions to access versus the actual Piwik website. Without both the ansible and the actual Piwik, the export site will have nothing to display. 

* insert picture here 

During the creation fo the Piwik software, there should be a prompt to create a mySQL database, or use one already created. Go through with either.

If there are any questions on or if the user still requires setting up the local metrics environment, please see [Developer Metrics Setup](https://github.com/aml-development/ozp-documentation/wiki/Developer_Metrics_Setup) page in the ozp-documentation wiki.



## Starting Out Development


## Navigating Piwik

Here explain the relation of Piwik and Piwik-Export. How does the Piwik-Export connect to Piwik and draw the information from it? Introduce the folder for the APIs in this section. Show the folder and how to find the correct API. To show the API, show the two ways to find the correct one: look in the modal in Piwik of the information that you want to transfer over and look at the end of the modal where the information lays (insert picture of the name of the modal and the bottom of the modal with arrow pointing to the location). After that selection, show the "widgets and dashboard" dropdown and explain how to look through that to find at first the "category" and then find the API. Show how to navigate that within the Atom folders. Once finding them, explain how this information is put into the Piwik-Stats.js form. Explain how the form is using "PiwikClient" as a means of extracting data directly from Piwik. Discuss more of the full chain process of Piwik to Piwik-Stats to stats.ejs within another section. Talk about instances of Piwik others may not know about, such as searchwords with open parentheses. 

## Putting it all together

Further explain the chain of process of Piwik to Piwik-Stats to stats.ejs here and how it all ties together.

## Adding plugins

In here, discuss how to find the plugin page. ~~Discuss how certain plugins can be APIs themselves (such as ClientCertificates) and how those can be used to collect and call information to the Piwik-Stats~~ How plugins are the APIs that are used to clal upon information pulled from Piwik and into the Export. Discuss about how to add them if the previous plugins repos did not discuss them enough. Also link to all the piwik plugins that we have available on our AppsMall project and state how instructions on installation on located there. Further eleborate if needed. Discuss how there may be a time where a plugin must be made. Link to the Piwik developer documentation where they teach how to make the plugins. Explain what information can be made into plugins (events that Piwik collects) and what cannot be tracked through Piwik (static information such as backend applications). Use appGrowth chart as an example to how a plugin could not be made to fit the information that it needs, but rather a request server call to get the information from the backend. Explain 

## All about Piwik-Stats.js

Here explain everything about Piwik-Stats. What does it do? What is it's purpose? Talk about how the purpose of Piwik-Stats is to tell Piwik what it wants from it and what it wants to show in stats.ejs. Explain further about the connection to Piwik and how it draws info from Piwik. Talk about the ```var period = 'range'``` and what this purpose is. Explain how the date-range-picker in the statsForm.ejs is what gives the range, the app.js sends that call to Piwik, Piwik sees from the Piwik-Stats what date object to look for, Piwik takes the range and find the data for said range, and then hands that data over to Piwik-Export to put into tables and charts. Discuss about PiwikClient and how that is pulling the data that is needed to the sever from Piwik itself. Explain how Piwik-Stats is connected to stats.ejs and how the information it gets is sent to stats.ejs and stylized. Explain how Piwik-Stats is the messenger that fetches the info and stats.ejs is the guy that works with the information. Explain what you need to do to get the info up. Discuss what else can be done in Piwik-Stats to further progress the Export project.

### Sections of Code You May Need to Know

In here, go over the Piwik-Stats form that must be filled out to import a section of data from Piwik over to the Piwik-Export. Also discuss about the config.json and to fill out the appropriate information if one has not done so. Talk about the groups.json and what it's purpose is, along with changing the url if need be (if url has changed). 

