:Author: Manuel Antonio Romero Caro
:License: Creative Commons Attribution-ShareAlike 3.0 Unported  (CC BY-SA 3.0)
:Thanks: 

@LOGO_ETF@
@OSGEO_KIND_ETF@
@VMDK_ETF@



.. |GS| replace:: GeoServer
.. |UG| replace:: uDig 


********************************************************************************
@NAME_ETF@ Quickstart
********************************************************************************

ETF is an open source testing framework for validating spatial data, metadata and web services in Spatial Data Infrastructures (SDIs). The design of ETF is driven by three goals: be user-friendly, consistent with the standards and capable of testing all resources in an SDI.

This Quick Start describes how to:

  * navigate through the web applicattion
  * start a test
  * monitor a test run
  * watch and manage test reports

.. contents:: Contents
   :local:
  
Introduction
===============

From the Start menu, select |osgeolive-appmenupath-ETF|. The application will take a few moments to start up and will open a web page at http://localhost:9090/ETF 
    
In the header, there is a menu with 4 options, representing each one differents views and functionalities: 

   .. image:: /images/projects/ETF/introduction.png
    :scale: 70 %
    
#. First one is Start test. In this section all available (respectively installed) Executable Test Suites are listed. Within this section, an Executable Test Suite can be selected and run against a Test Object..

#. Second one is Status. This one shows all tests that are currently executed on the system and enables to open a monitor view for single test runs. can check the status of any running test. Moreover, below the running tests appear the components currently loaded

#. Third one is Test reports. In this one the results any finished test can be checked, opened to see more details or downloaded.

#. Fourth one is Help. This one is a link to the documentation. Inside it, there are guides on how to use all functionalities of ETF.



Start test
===============
Test Suite Selection
----------------------------------
The landing view shows the available Executable Test Suites.


  
   .. image:: /images/projects/ETF/geoserver-layerpreview.png
    :scale: 70 %

Additional information about a Test Suite can be shown by clicking on the plus button. 

   .. image:: /images/projects/geoserver/geoserver-preview.png
    :scale: 70 %
    
This information includes:

        * A description of the Test Suite.

        * May include a link to the Abstract Test Suite from which the Executable Test Suite has been derived (Source).

        * May include Test Suite dependencies which are automatically executed with the Test Suite in a Test Run (Pre-requisite conformance classes).
        
        * May include the name of associated Tags which are used to group the Test Suites in the view.
        
        * The name of applicable Test Object Types (explained in the next section).
 
        * General information like the version, author and last editor, creation and change dates.


To start a Test Run, a Test Suite must be selected with a click on the use flip switch on the right-hand side.

A Start button appears once at least one Test Suite is selected.

A Test Suite is applicable to certain Test Object Types, that are listed in the description. Multiple Test Suites can be selected for one Test Run, but must be applicable to the same Test Object Type. Once one Test Suite is selected, the flip switch of all other Test Suites having different Test Object Types is disabled.

A Test Suite may depend on other Test Suites. The dependencies are also shown in the description of the Test Suites. These dependencies are also automatically executed during the test run.

A click on the Start button will open a new view that asks the user about the target to be tested.



Test Run configuration
----------------------------------

The Label field is mandatory but automatically preset with the current time and names of the selected Test Suites. The Label will be shown in the Test reports overview and can be changed in order to help find the report again after a test run.

The style of the view may depend on the selected Test Suites.

File-based Tests
----------------------------------
The following elements are shown when Test Suites have been selected that test one or multiple test data files.

If File upload is selected as Data source one or multiple local files can be selected and uploaded to the Validator. The Validator only accepts files with XML and GML file ending and ZIP files containing these two file types.

 .. note::	Other files, like schema definition files, can not be used and are silently ignored by the Validator!

   .. image:: /images/projects/ETF/file-based-tests-1.png
    :scale: 70 %

The maximum uploadable file size is displayed when the mouse is moved over the question mark.

If the data are available on the web they can be tested by providing one single URL. After Remote file (URL) has been selected as Data source, an URL to either one single XML, GML or a ZIP file can be entered.

   .. image:: /images/projects/ETF/file-based-tests-2.png
    :scale: 70 %


If the URL requires authentication, username and password can be provided by clicking on Credentials.

   .. image:: /images/projects/ETF/file-based-tests-3.png
    :scale: 70 %



Service Tests
----------------------------------

The following elements are shown when Test Suites have been selected that test one service.

The URL of a service must be entered beginning with http:// or https:// .

   .. image:: /images/projects/ETF/service-test-1.png
    :scale: 70 %

If the service requires authentication, username and password can be provided by clicking on Credentials.

Dependencies and Parameters
----------------------------------

The Test Suites button shows some basic information about the selected Test Suites and -if applicable- about the direct dependencies.

   .. image:: /images/projects/ETF/dependencies-and-parameters-1.png
    :scale: 70 %

If the Test accepts parameters, they are shown in the Test Suite Parameters section. Optional parameters can be displayed by clicking on the Optional Parameters button. A description of the parameters is displayed when the mouse is moved over the question mark.

 .. note::	In most cases the preset default values can be used.
 
    .. image:: /images/projects/ETF/dependencies-and-parameters-2.png
    :scale: 70 %

Finally the test can be started by clicking on the Start button. The view then changes automatically to the Monitor View.

Monitor test runs
============

After a Test Run has been started the Monitor View is shown.

The blue bar indicates the progress.

The console area shows information and result messages. The Test Run can be canceled with a click on the Cancel button.

The view can be left, for instance with the X Button in the upper left corner. Also when the browser is closed, the Test Run execution continues on the server.

To reopen the Monitor View after it has been closed, select in the menu bar the Status view. The Status view shows all running tests. A click on the Test Run opens the Monitor View of that Test Run.

When a Test Run finishes and the Monitor View is opened, the Test Report is displayed automatically.


Test Reports
============

The Test Reports view shows all reports that have been generated from Test Runs.

By clicking on the plus button information, about the start time, the test result status, the name of the Test Object and the used Test Suites is shown.

A Test Report can be opened again by clicking on Open report or can be downloaded as HTML file by clicking on the Download button.

The log file of the test run can be inspected with the Open log button. By clicking on Delete report button, the report will be deleted permanently.


Inspect test reports
============

The top of a Test Report shows general information including the overall test result Status, the start time, the duration and a statistical table, which summarizes the status of all tests on several levels.

The Test Reports are interactive. The Show switch can be used to filter Only failed or Only manual tests. All deactivates the filter.

The Level of detail switch is used to show additional technical information in the reports.

The test results are summarized hierarchically in a report. At the top level there are the Test Suites.

By clicking on one test suite a description and all lower level tests in that test suite are shown. Failures in a test suite can be immediately recognized by the red color. The number of failed tests is shown in the top-right corner.

The green color indicates a passed test. Passed tests which require additional manual test steps that could not be automated are colored orange. The orange color may also indicate a test that has been skipped because it depends on another test that has failed. The exact status can be found below the description.

The number of levels depends on the tested Test Object. If service tests have been executed the hierarchy is as follows:

        * Executable Test Suites

        * Test Modules (bundles Test Cases)

        * Test Cases (bundles Test Steps)

        * Test Steps (interactions with the service, bundles Test Assertions)

        * Test Assertions (atomar tests)

In a file-based test, Test Modules and Test Steps do not exist and are not shown in the report.

Each test provides a description on how aspects are tested and lists the requirements. The test may possess a link to an abstract test suite, from which the test has been derived (Source).

Assertions stand for atomic test queries on the lowest level. Failed, red colored assertions display error messages in the Messages section.

Helpful information may also be found on the next higher level, like for instance the response from a service on the Test Step level (note the Open saved response link in the report).


