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

    Create a Makefile with this commands:

    install:
        pip install --upgrade pip &&\
            pip install -r requirements.txt

    test:
        python -m pytest -vv test_hello.py

    lint:
        pylint --disable=R,C hello.py

    all: install lint test
