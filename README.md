# Copado Integrations
Easily integrate your external project management system with Copado.  This repository will hold the base layer of the integration code that may be extended by the community.

The latest version supports JIRA, VersionOne and Rally.

# How does it work?
Copado Solutions has built the authentication module as well as the framework for retrieving user stories and inserting these into the Copado sObject called, "User Story".  The mapping is also handled by the integration.  Both the data being queried from the data source as well as the mapping can be modified.  We have commented the code with instructions to help with the customisation process.

The code & all the components are contained in an unmanaged package and available within this repository as a backup.

Installation instructions can be found below.

# What gets imported into Copado?
By default the following fields get imported:
- User Story Title (User_Story_Title__c)
- Status (Status__c)
- Project (Project__c)
- Functional Specifications (Functional_Specifications__c)

# Installation instructions
To install the application use one of the below URLs.
- Production/Developer orgs: https://login.salesforce.com/packaging/installPackage.apexp?p0=04t240000009XQb
- Sandbox orgs: https://test.salesforce.com/packaging/installPackage.apexp?p0=04t240000009XQb

# Customisation
In order to customise the the mappings for the fields being retrieved, you will need to search for the section in the code labelled, "FIELD MAPPINGS"

# Getting started
Once the package is installed, you will need to setup a Change Management Integration Credential.
This is done from the "Change Management Integrations" tab.
- A Jira endpoint might look as follows: https://<COMPANAY DOMAIN NAME>.atlassian.net/rest/api/2/
- A VersionOne endpoint might look as follows: https://www9.v1host.com/<COMPANDY NAME>/
- A Rally endpoint might look as follows: https://rally1.rallydev.com/slm/webservice/v2.0/

Once the integration credentials have been setup, you will need to create a new project or edit an existing project and complete the following two fields. NOTE if they are not in the page layout you will need to add them to the layout(s).
- Change Management Integration - This lookup field looks up the credential you just created.
- External Id - This external Id field needs the Id of the project for which we will import the User Stories.

Once everything is setup, you can press the "Sync External User Stories" button.

We recommend that the User Story Status picklist values match that of your external system.


