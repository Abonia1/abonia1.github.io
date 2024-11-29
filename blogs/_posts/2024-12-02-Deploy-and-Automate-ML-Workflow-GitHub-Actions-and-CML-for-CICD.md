---
layout: post
title: Automate ML and LLM Workflow with GitHub Actions & CML
image: 
  path: https://cdn-images-1.medium.com/max/2560/1*y0qMmXhAevudLX23NgvkuA.png
description: >
    MLOps On GitHub | Deploy and Automate ML Workflow |Using GitHub Actions and CML for CI & CD.
    Machine learning workflows are complex and time-consuming, involving tasks like data processing, model training, and evaluation. Integrating Continuous Integration (CI) and Continuous Deployment (CD) practices can automate these tasks, saving time, reducing errors, and improving collaboration.
sitemap: false
---

  **Reading_time:** 10 min\
  **Tags:** [GitHubActions, CML, MachineLearning, MLOps, DataScience, CICD, Automation, MLPipeline, AI, Scikitpipeline, MLModel
MachineLearning, GitHubActions, CML, MLAutomation, ChurnPrediction]
- Table of Contents
{:toc .large-only}


## Automate ML and LLM Workflow with GitHub Actions & CML

###  A Complete Guide to CI/CD for Machine Learning or LLM Projects

Machine learning workflows are complex and time-consuming, involving tasks like data processing, model training, and evaluation. Integrating Continuous Integration (CI) and Continuous Deployment (CD) practices can automate these tasks, saving time, reducing errors, and improving collaboration.I have prepared a tutorial into two major parts as follow:

**[Part 1 -  MLOps On GitHub - Deploy and Automate ML Workflow - Using GitHub Actions and CML for CI & CD](https://youtu.be/DQIX7p5xx7c)**.

**[Part 2: MLOps On GitHub - Deploy and Automate ML Workflow - Using GitHub Actions and CML for CI & CD](https://youtu.be/u_rCPdZY2g4)**.

Here is the link to the Part1 tutorial on 

In this comprehensive guide, we’ll explore how to automate ML workflow using GitHub Actions and Continuous Machine Learning (CML). We’ll focus on a churn prediction project and walk through the process of setting up an automated pipeline to handle training, evaluation, and reporting. By the end of this guide, you’ll have a fully automated CI/CD pipeline for ML project, enhancing workflow and making it easier to collaborate with team.

### What is CI/CD for Machine Learning?

CI/CD is a set of practices that involve continuously integrating code changes and deploying them into production systems. For ML projects, CI/CD can automate various tasks such as model training, evaluation, testing, and deployment. The goal is to ensure that changes to the project — whether new data, code changes, or model updates — are automatically tested and deployed without manual intervention.

Continuous Integration (CI) focuses on automatically testing and integrating code changes into the main branch. For ML projects, this involves testing the model’s accuracy, performance, and behavior with each update.

Continuous Deployment (CD) automates the deployment of the model to a production environment. This ensures that the most recent version of the model is available for use, and any issues are detected quickly.

For ML, CI/CD practices help ensure that models are continuously trained, tested, and deployed without manual intervention, allowing for faster iteration and a smoother workflow.

## Part 1: Automating ML Workflow with GitHub Actions & CML

**Introduction to GitHub Actions and CML**

GitHub Actions is a tool that allows you to automate software workflows directly within GitHub repository. It is ideal for CI/CD purposes, where you can define workflows that automatically trigger when specific events occur (e.g., a code push, a pull request).

Continuous Machine Learning (CML) is an open-source tool designed to help you incorporate continuous integration and delivery into ML projects. CML integrates seamlessly with GitHub Actions, allowing you to automate tasks such as model training, evaluation, and report generation.

### Step-by-Step Tutorial: Setting Up CI/CD for a Churn Prediction Project

**1. Setting Up the GitHub Repository**

To get started, you’ll need to create a GitHub repository for churn prediction project. This repository will store code, datasets, and results. You’ll also configure GitHub Actions to automate the ML pipeline.

- Create a GitHub repository for project.

- Add a basic folder structure to organize code, data, and models.

- Configure GitHub Actions in the repository by adding a workflow file (`.github/workflows`).

**2. Dataset Preparation**

The next step is preparing dataset. For this tutorial, we’ll use a churn prediction dataset. Since machine learning datasets can be large, Git LFS (Large File Storage) is essential for managing large files such as datasets and model weights.

- Upload the dataset to GitHub repository using Git LFS.

- If dataset is hosted elsewhere (e.g., cloud storage), make sure to automate the process of downloading the dataset within the workflow file.

**3. Building the ML Model Pipeline**

Here, we’ll build the machine learning pipeline for churn prediction. This includes tasks like data preprocessing, model training, and evaluation. With GitHub Actions, every time a change is pushed to the repository, the pipeline will automatically run to train the model and generate evaluation metrics.

- Create Python scripts for data preprocessing, model training, and testing.

- Define the machine learning algorithm (e.g., logistic regression, decision trees) for churn prediction.

**4. Testing the Model** 

Once the model is trained, we’ll evaluate its performance. Using GitHub Actions and CML, we can automate the testing of the model’s accuracy and other metrics (e.g., confusion matrix, ROC curve). This ensures that the model’s performance is continuously monitored and automatically updated with every commit.

- Use CML to generate detailed performance reports.

- Set up automated testing for every commit to ensure the model is performing as expected.

**5. Next Steps**

After completing Part 1, you’ll have a fully automated pipeline for training and testing churn prediction model. In the next part, we’ll enhance the pipeline with visualizations, advanced metrics, and automated reports.

## Part 2: Enhancing the ML Workflow with GitHub Actions & CML



**1. Reviewing Model Evaluation Metrics**

In this part of the tutorial, we’ll focus on enhancing our CI/CD pipeline by adding more advanced model evaluation metrics, such as confusion matrix and accuracy graphs. By integrating these into the workflow, we can automatically assess model performance after every update.

- Review the confusion matrix to understand how well our model is performing in terms of true positives, false positives, true negatives, and false negatives.

**2. Git LFS Setup**

Git LFS (Large File Storage) ensures that large files like datasets and model weights are efficiently handled in our GitHub repository. It’s important to revisit Git LFS setup to ensure that everything works smoothly when training models on large datasets.

- Install and configure Git LFS to handle large files in our project repository.

**3. Creating the Workflow File (YAML Workflow Steps)**

The heart of our automation is the YAML workflow file. In this file, you’ll define the steps for training the model, testing it, and generating reports. The workflow file also specifies when each task should run (e.g., on every push or pull request).

- Define jobs in the workflow file for each step: data preparation, training, testing, and reporting.

- Automate the process of checking the model’s performance with every commit or pull request.

 **4. Building the CI/CD Pipeline Job**

Now that the workflow file is set up, we’ll define the build job to automate the entire pipeline. The job will pull the latest code, prepare the environment, and run the necessary tasks (such as model training and testing) automatically.

- Automate testing to ensure that every commit passes the required checks before being merged into the main branch.

**5. Model Metrics and Visualizations with CML**

In this step, we’ll integrate CML to automatically generate performance visualizations (e.g., training accuracy, loss graphs) and display them directly within GitHub. These visualizations provide insights into model performance and can help track progress over time.

- Use CML to generate visualizations and save them as images or reports.

- Automatically upload and display these reports on GitHub.

**6. Automated Reports in Pull Requests**

Once the model is trained and tested, CML can be used to automatically generate a detailed report that is included in the pull request. This allows our team to review model performance directly from the GitHub interface without manually reviewing logs or results.

- Set up CML to generate and attach reports in pull requests, making it easy for our team to monitor changes in model performance.

**7. Conclusion and Next Steps**

By the end of Part 2, you’ll have a robust CI/CD pipeline that automates not only the training and testing of models but also the reporting of metrics and visualizations. This enables our team to track changes in model performance automatically and collaborate seamlessly on improvements.

Moving forward, you can scale this pipeline, integrate deployment workflows, and continuously improve the churn prediction model.

## What is GitHub Actions?

**GitHub Actions** is a powerful tool provided by GitHub that allows you to automate workflows directly in our GitHub repository. It enables to define custom workflows for software development processes, such as Continuous Integration (CI), Continuous Deployment (CD), and automation of various tasks like testing, building, and deployment.

With GitHub Actions, you can automate virtually any task, and the workflow can be triggered by different events such as pushing code to a repository, opening a pull request, creating a tag, or on a scheduled basis. GitHub Actions use **YAML configuration files** to define workflows and steps.

## Key Features of GitHub Actions:

* **Custom Workflows**: Create workflows that automatically trigger when events happen in repository.

* **Reusable Actions**: You can reuse pre-built actions from the GitHub marketplace or create our own.

* **Parallel Execution**: Workflows can run multiple jobs in parallel, improving efficiency.

* **Integration with Other Services**: GitHub Actions can integrate with external services for additional tasks like sending notifications or deploying models to cloud platforms.

## Sample GitHub Actions Workflow YAML:

Here’s a simple example of a GitHub Actions workflow file that runs tests on every push to the repository.

    name: Python CI
    on:
      push:
        branches:
          - main  # Trigger this workflow on push to the main branch
      pull_request:
        branches:
          - main  # Trigger on pull requests to the main branch
    jobs:
      test:
        runs-on: ubuntu-latest  # The machine that runs the workflow
        steps:
          - name: Checkout code
            uses: actions/checkout@v3  # This step checks out the repository
          - name: Set up Python
            uses: actions/setup-python@v4
            with:
              python-version: '3.8'  # Set up Python 3.8 environment
          - name: Install dependencies
            run: |
              python -m pip install --upgrade pip
              pip install -r requirements.txt  # Install dependencies from the requirements.txt
          - name: Run tests
            run: |
              pytest  # Run tests with pytest

## What is CML (Continuous Machine Learning)?

**Continuous Machine Learning (CML)** is an open-source framework built by **Iterative** to bring continuous integration practices to machine learning (ML) workflows. CML allows you to automate aspects of machine learning lifecycle, such as training models, evaluating them, and generating reports, and integrates seamlessly with GitHub Actions.

CML makes it easy to manage the often complex and resource-heavy ML workflows by automating tasks such as:

* Training machine learning models

* Generating visualizations and metrics

* Creating automated reports

* Storing and versioning large datasets

With CML, you can ensure that models are constantly updated, evaluated, and tracked in an efficient, automated manner. It integrates well with GitHub Actions to enhance automation in ML projects.

## Key Features of CML:

* **Track Metrics and Visualizations**: Automate the generation of charts, graphs, and other visualizations for model performance.

* **Model Experimentation**: Automatically manage and track different versions of machine learning models.

* **Run and Report Model Evaluations**: After training a model, automatically evaluate its performance and report metrics like accuracy, loss, confusion matrices, and more.

* **Integration with GitHub**: CML integrates directly into GitHub Actions workflows, allowing for seamless automation of model training, testing, and reporting.

## Sample CML Workflow with GitHub Actions:

Below is an example of how you can integrate **CML** with **GitHub Actions** to automate ML workflows, including training a model, evaluating it, and generating a performance report.

**Define the CML Workflow in GitHub Actions**:

    name: ML CI/CD Workflow
    on:
      push:
        branches:
          - main  # Trigger workflow on push to main branch
      pull_request:
        branches:
          - main  # Trigger workflow for pull requests to the main branch
    jobs:
      train:
        runs-on: ubuntu-latest  # Set the environment
        steps:
          - name: Checkout repository
            uses: actions/checkout@v3  # Checkout code repository
          - name: Set up Python
            uses: actions/setup-python@v4
            with:
              python-version: '3.8'  # Define the Python version
          - name: Install dependencies
            run: |
              python -m pip install --upgrade pip
              pip install -r requirements.txt  # Install Python dependencies
          - name: Set up Git LFS
            run: |
              git lfs install  # Enable Git LFS to manage large files
          - name: Train model and log metrics with CML
            run: |
              python train_model.py  # Train model 
              cml run -T "Training Results" --report metrics.json  # Run CML to log metrics
          - name: Commit metrics and model results
            run: |
              git add metrics.json model.pkl  # Add metrics and model to Git
              git commit -m "Update model and metrics"
              git push

## Explanation of the Workflow:

* **on:**: Defines the trigger for the workflow. Here, the workflow runs on push to the main branch or when a pull request is opened.

* **jobs:**: Defines the steps that run in the workflow. In this case, it includes:

 1. **Checkout code**: It checks out repository’s code.

 2. **Set up Python**: It sets up the Python environment for the workflow.

 3. **Install dependencies**: It installs the necessary Python packages listed in the requirements.txt file.

 4. **Train the model**: It runs the train_model.py script to train the model.

 5. **CML integration**: The cml run command trains the model and logs metrics in metrics.json. The metrics and results are then committed back to the repository.

 6. **Push results**: After the model is trained and metrics are generated, the results are committed and pushed to the repository.

### Key Benefits of Automating ML Workflows with GitHub Actions & CML

1. Improved Efficiency: Automating repetitive tasks like model training, testing, and reporting saves valuable time and reduces the chances of human error.

2. Real-Time Feedback: Automated reporting provides real-time insights into model performance, allowing team to quickly identify issues and improve the model.

3. Collaborative Workflow: With GitHub Actions and CML, collaboration becomes seamless. Team members can contribute to the project, and every change is automatically tested and reviewed.

4. Scalability: As project grows, you can easily scale the pipeline to handle more models, larger datasets, and more complex workflows.

### Conclusion

Automating machine learning workflow with GitHub Actions and CML is a game-changer for data scientists, machine learning engineers, and developers. By following this guide, you’ll have a fully automated CI/CD pipeline that handles training, evaluation, and reporting for churn prediction model.

Incorporating CI/CD into ML workflow ensures that team can work more efficiently, reduce errors, and stay up to date with the latest model improvements. So, what are you waiting for? Start automating ML projects today and enjoy the benefits of streamlined workflows and better collaboration. Happy coding!


>  **Connect with me on [Linkedin](https://www.linkedin.com/in/aboniasojasingarayar/)**

>  **Find me on [Github](https://github.com/Abonia1)**

>  **Visit my technical channel on [Youtube](https://www.youtube.com/@AboniaSojasingarayar)**

>  **Support: [Buy me a Cofee/Chai](https://www.buymeacoffee.com/abonia)**

> # *Thanks for Reading!*
