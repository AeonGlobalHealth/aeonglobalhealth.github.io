# DIA-Core Package

![Tests](https://github.com/AeonGlobalHealth/dia-core/actions/workflows/tests.yml/badge.svg)

[dia](https://github.com/AeonGlobalHealth/dia) > [dia-core](https://github.com/AeonGlobalHealth/dia-core)

The DIA package is designed to assist whatever LIS or LIMS a laboratory or organization is using. It is not explicitly designed to replace the LIS or LIMS currently in use, but it may be capable of doing so in the future. DIA also serves to automate typical tasks performed at a laboratory in terms of generating reports and sending files to Public Health Departments of various states.

The ultimate target of DIA is to have a means of browsing internal data through the web browser and integrating related data in a way that allows users to logically get from one object to another related object, almost like the focus can be shifted from one item to another if there is a connection between the nodes. Certain automations should also be available to the user depending on where their focus is at the moment. Interfaces with specific external software and instruments opens more automation features to the user.

To use the web app, an account must first be created. Accounts may have more than one user associated with them, and each account can "subscribe" to various other "apps" or subgroups of functionality. Users may be admins or members and may have different user roles if they are part of an organization. Users, depending on their user roles and specific user settings, may be able to subscribe to any of the apps to which the associated account is subscribed.

For the moment, DIA shall be locally hosted to provide a user with access to a Flask front-end web app to browse and manipulate data with a SQLAlchemy and Postgres back-end. An API is also exposed to the user for terminal execution for more custom data exploration and manipulation. Once all features are fully tested and security is fleshed out better, and also once a subscription plan is fully developed, the app may be hosted on the internet for broader use.

DIA is broken down into various separate packages for separate version control on the different components. See below for links to the associated repositories.

Associated Packages:
1. [DIA](https://github.com/AeonGlobalHealth/dia)
2. [DIA-Core](https://github.com/AeonGlobalHealth/dia-core)
3. [DIA-Assets](https://github.com/AeonGlobalHealth/dia-assets)
4. [DIA-Blogs](https://github.com/AeonGlobalHealth/dia-blogs)
5. [DIA-Business](https://github.com/AeonGlobalHealth/dia-business)
6. [DIA-Chemistry](https://github.com/AeonGlobalHealth/dia-chemistry)
7. [DIA-Documents](https://github.com/AeonGlobalHealth/dia-documents)
8. [DIA-Forums](https://github.com/AeonGlobalHealth/dia-forums)
9. [DIA-Healthcare](https://github.com/AeonGlobalHealth/dia-healthcare)
10. [DIA-Instruments](https://github.com/AeonGlobalHealth/dia-instruments)
11. [DIA-Interfaces](https://github.com/AeonGlobalHealth/dia-interfaces)
    * [DIA-Interfaces-Access2](https://github.com/AeonGlobalHealth/dia-interfaces-access2)
    * [DIA-Interfaces-Analyst](https://github.com/AeonGlobalHealth/dia-interfaces-analyst)
    * [DIA-Interfaces-AU640](https://github.com/AeonGlobalHealth/dia-interfaces-au640)
    * [DIA-Interfaces-DPH](https://github.com/AeonGlobalHealth/dia-interfaces-dph)
    * [DIA-Interfaces-HL7](https://github.com/AeonGlobalHealth/dia-interfaces-hl7)
    * [DIA-Interfaces-LabGen](https://github.com/AeonGlobalHealth/dia-interfaces-labgen)
    * [DIA-Interfaces-MultiQuant](https://github.com/AeonGlobalHealth/dia-interfaces-multiquant)
    * [DIA-Interfaces-NextGen](https://github.com/AeonGlobalHealth/dia-interfaces-nextgen)
    * [DIA-Interfaces-OpenArray](https://github.com/AeonGlobalHealth/dia-interfaces-openarray)
    * [DIA-Interfaces-QuantStudio](https://github.com/AeonGlobalHealth/dia-interfaces-quantstudio)
    * [DIA-Interfaces-Quartzy](https://github.com/AeonGlobalHealth/dia-interfaces-quartzy)
    * [DIA-Interfaces-Senaite](https://github.com/AeonGlobalHealth/dia-interfaces-senaite)
    * [DIA-Interfaces-Tecan](https://github.com/AeonGlobalHealth/dia-interfaces-tecan)
12. [DIA-LIMS](https://github.com/AeonGlobalHealth/dia-lims)
13. [DIA-Reports](https://github.com/AeonGlobalHealth/dia-reports)
14. [DIA-Tasks](https://github.com/AeonGlobalHealth/dia-tasks)

* For the GitHub repository, click [here](https://github.com/AeonGlobalHealth/dia).
* For the DIA Trello board, click [here](https://trello.com/b/i6iBsLLe/limsassistant-board).
* For helpful DIA Lucid Charts, click [here](https://lucid.app/documents#/documents?folder_id=289539324).

For whatever Aeon's needs, DIA is meant to Do. It. All.

## Requirements

In order to use the DIA, you will need to download and install the following:

* Python (3.8+ (3.8 preferred, later versions of Python are acceptable only for Windows 10 and above))

Python will need to be added to the system path.

Please see the "requirements.txt" file for all required dependencies.

Certain features, especially interfaces, will require other software, mostly proprietary software, for full functionality.

NOTE: At the moment, certain data must be pre-loaded into the primary database in order for the Flask application to function correctly. This will be changed in the future to allow for greater portability.

## Installation

NOTE: You will need to first install any version of Python 3.8 along with git to use DIA. You will also need to create a GitHub account and be invited to the AeonGlobalHealth GitHub organization to be granted access.

You can download Python version 3.8.10 [here](https://www.python.org/downloads/release/python-3810/).

You can download the latest version of git [here](https://git-scm.com/downloads).

1. In the folder where you want to download a copy of DIA, run a terminal window.
2. Type: ```git clone https://github.com/AeonGlobalHealth/dia-core.git DIA-Core``` to clone a copy of the DIA repository. You may need to provide login credentials. The repository must be shared with your GitHub account in order to be granted access.
3. Type: ```cd .\DIA-Core``` to change to the newly created folder.
4. Type: ```python -m venv env``` to create a virtual environment.
5. Type: ```.\env\Scripts\activate``` to activate the virtual environment.
6. Type: ```python -m pip install --upgrade pip``` to ensure that pip is up to date.
7. Type: ```pip install -r requirements.txt``` to install all dependencies.
8. Type: ```python flask_app.py``` to run the flask application.
9. By default, the flask_app is hosted only locally on 127.0.0.1 port 2225. In a web browser (preferably Google Chrome), visit https://127.0.0.1:2225/ while the flask application is being hosted and follow the configuration outlined there. To access a flask application that is hosted over a shared network, use the IP address hosting the app on port 443.

You can press "CTRL+C" to stop hosting the flask application. Type ```deactivate``` to deactivate the virtual environment.

## Development

For git version control and branching, please follow the guidelines outlined [here](https://nvie.com/posts/a-successful-git-branching-model/). Development must occur on a branch that has branched off from develop. Certain larger projects may branch off develop and then each subfeature may branch from the primary feature branch. Upon submission for review, a feature branch may be merged into the develop branch.

Once the bulk of the features are present for any given version, a release branch is created, e.g. release-1.0.0, as a staging area to be tested and updated for version information. Additional development at this point must be merged back into the develop branch and then edited on a new feature or hotfix branch, e.g. hotfix-1.0.1. Once all features for a release have been reviewed, tested, and approved, upon final review, the release may be merged to main. The develop branch must also be updated with the new release. The release branches shall be kept for archival purposes, but hotfix branches and feature branches are to be deleted upon merging to a core branch.

Development will incorporate Github's [Milestones](https://github.com/AeonGlobalHealth/dia-core/milestones), [Issues](https://github.com/AeonGlobalHealth/dia-core/issues), and [Projects](https://github.com/AeonGlobalHealth/dia-core/projects) features to aid in planning, tracking, and guiding the workflow. Ideally, commits will be fine-grained and specific and should contain the issue number relating to the changes in the commit message.

To incorporate DIA-Core into a current project, you can install it using ```pip install -e git+https://github.com/AeonGlobalHealth/dia-core.git#egg=dia-core``` while in a virtual environment. This will install the package into the .\env\src directory. To install it as a regular package, within a virtual environment use ```pip install git+https://github.com/AeonGlobalHealth/dia-core.git#egg=dia-core```. To install a particular branch, use ```pip install git+http://github.com/AeonGlobalHealth/dia-core.git@{branch-name}#egg=dia-core```. You can also install a particular release or tag by using ```pip install git+https://github.com/AeonGlobalHealth/dia-core.git@{tag-name}#egg=dia-core```.

## Authors

* Mark Hoover (mhoover@aeonglobalhealth.com)

## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/AeonGlobalHealth/dia-core/blob/main/LICENSE) file for details.
