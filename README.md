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
 
 **Project Structure explanation**
 
 
 - The reports generated from the command described below will generate the reports in the Allure_reports directory.<br>
 - All the Drivers are kept in the drivers folder.<br>
 - The feature files and the step files are kept in the folders with the respective names under the Features directory which also consists of the file environment.py.<br>
 - All the locators of different web pages have been separated and kept inside the Locators directory for clear understanding and modularity.<br>
 - The all common functions which are being used for automation in the step files are kept in files inside the pageactions directory.

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
- behave “Feature/feature/example.feature” (to run a particular feature file)


**Generating allure reports**

- behave -f allure_behave.formatter:AllureFormatter -o %allure_result_folder% ./features
- allure serve %allure_result_folder%


![ezgif com-gif-maker (1)](https://user-images.githubusercontent.com/42156397/122174608-7a7c7c80-cea0-11eb-9f22-ca71fe28198e.gif)

