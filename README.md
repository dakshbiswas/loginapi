**Numerator Adlake collection Automation**

**Methodology and Framework**

Behavior-driven development (or BDD) is an agile software development technique that encourages collaboration between developers, QA and non-technical or business participants in a software project. We have a page further describing this philosophy.
Since behave is an opinionated framework, it has a very opinionated project structure. All code must be located under a directory named “features”. Gherkin feature files and the “environment.py” file for hooks must appear under “features”, and step definition modules must appear under “features/steps”. Configuration files can store common execution settings and even override the path to the “features” directory.
Note: Step definition module names do not need to be the same as feature file names. Any step definition can be used by any feature file within the same project.

**Project Structure**

[project root directory]<br>
|‐‐-- allure_reports<br>
|‐‐-- Drivers<br>
|   |---- *.exe<br>
|---- Features<br>
|   |---- environment.py<br>
|   |---- features<br>
|   |   |--*.feature<br>
|   |---- steps<br>
|   |   |--*steps.py<br>
|---- Locators<br>
|   |---- *_Locators.py<br>
|---- pageactions<br>
|   |---- functions.py<br>
|---- Logs<br>
|---- Screenshots<br>
|---- requirements.txt<br>
 
 **Project Structure explanation**
 
 
 - The reports generated from the command described below will generate the reports in the allure_reports directory.<br>
 - All the Drivers are kept in the drivers folder.<br>
 - The feature files and the step files are kept in the folders with the respective names under the Features directory which also consists of the file environment.py.<br>
 - All the locators of different web pages have been separated and kept inside the Locators directory for clear understanding and modularity.<br>
 - The all common functions which are being used for automation in the step files are kept in files inside the pageactions directory.
 - Everytime we run the tests, a log file will be generated in the Logs directory about the current test results and automatically the previous logs will be deleted.
 - When certain tests fail, the screenshot will be captured and stored in the Screenshots directory followed by the deletion of the previous screenshots.
 - The requirements.txt file contains all the dependencies for running the framework.

**Software Requirements**

- Pycharm
- Python3
- Selenium
- behave
- allure-behave


**Installation**

- pip install behave
- pip install allure-behave

**Running the test cases**

- behave                               (for running all the feature files in the project)
- behave Feature/feature/example.feature (to run a particular feature file)
- behave --tags=tagname Feature/feature/example.feature (To run particular scenarios with tags "@tagname")


**Generating allure reports in json format**

- behave -f allure_behave.formatter:AllureFormatter -o %allure_result_folder% ./features

**Opening the allure reports in browser**

- allure serve %allure_result_folder%

