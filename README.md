**Numerator Adlake collection Automation**

**Methodology and Framework**

Behavior-driven development (or BDD) is an agile software development technique that encourages collaboration between developers, QA and non-technical or business participants in a software project. We have a page further describing this philosophy.
Project structure
Since behave is an opinionated framework, it has a very opinionated project structure. All code must be located under a directory named “features”. Gherkin feature files and the “environment.py” file for hooks must appear under “features”, and step definition modules must appear under “features/steps”. Configuration files can store common execution settings and even override the path to the “features” directory.
Note: Step definition module names do not need to be the same as feature file names. Any step definition can be used by any feature file within the same project.


[project root directory]
|‐‐ [product code packages]
|-- features
|   |-- environment.py
|   |-- *.feature
|   `-- steps
|       `-- *_steps.py
`-- [behave.ini|.behaverc|tox.ini|setup.cfg]


**Software requirements**

-Pycharm
-Python3
-Selenium
-behave
-allure-behave

**Installation**

pip install behave
pip install allure-behave

**How to run the test cases**

behave (for running all the feature files in the project)
behave “path/of/feature/file/to/run” (to run a particular feature file)

**How to generate allure reports**

behave -f allure_behave.formatter:AllureFormatter -o %allure_result_folder% ./features
 allure serve %allure_result_folder%

