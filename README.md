# Azure-DevOps-Agile-Dev - Build a CI / CD Pipeline

## Overview

In this project, you will build a Github repository from scratch and create a scaffolding that will assist you in performing both Continuous Integration and Continuous Delivery. You'll use Github Actions along with a Makefile, requirements.txt and application code to perform an initial lint, test, and install cycle. Next, you'll integrate this project with Azure Pipelines to enable Continuous Delivery to Azure App Service.

## Planning

***Project Plan***

    See the included Project Management .xlsx file

***Trello Board***

## Preparation

### SSH-Key

Create ssh key in Azure and upload it to Github

### Scaffolding

***Create a Makefile with this commands:***

    install:
        pip install --upgrade pip &&\
            pip install -r requirements.txt

    test:
        python -m pytest -vv test_hello.py

    lint:
        pylint --disable=R,C hello.py

    all: install lint test

***Create a requirements.txt file***

It should contain:

    pylint
    pytest

***Create the Python Virtual Environment***

In Azure Cloud Shell environment create a Python virtual env
    virtualenv ~/.devops-project2
    source ~/.devops-project2/bin/activate

***Create the script file and test file***

Create a file hello.py

    def toyou(x):
        return "hi %s" % x


    def add(x):
        return x + 1


    def subtract(x):
        return x - 1

Create a test_hello.py file

    from hello import toyou, add, subtract


    def setup_function(function):
        print("Running Setup: %s" % function.__name__)
        function.x = 10


    def teardown_function(function):
        print("Running Teardown: %s" % function.__name__)
        del function.x


    ### Run to see failed test
    #def test_hello_add():
    #    assert add(test_hello_add.x) == 12

    def test_hello_subtract():
        assert subtract(test_hello_subtract.x) == 9    