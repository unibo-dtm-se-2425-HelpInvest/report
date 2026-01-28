---
title: CI/CD
has_children: false
nav_order: 9
---

# Continuos Integration and Continuous Development overview
CI/CD (Continuous Integration and Continuous Deployment) is a development practice that automates the process of integrating code changes, testing them, and delivering the application to a runnable environment.
The project combines:
- A **Pthon backend** (Flask, NumPy, Maptplotlib)
- **HTML Tempplates** (Homepage and results page)
- **CSS Styling**
- Generation of **static plot images**

Because the application has multiple interacting parts (backend logic, templates, static files, plotting libraries), CI/CD is used to automatically verify that the system remains functional every time the code changes.

## Continuous integration (CI)
Continuous integration ensures that every update to the project is automatically tested in a clean environment. 
### When CI runs
The CI workflow is triggered automatically when:
- Code is pushed to the repository
- A pull request is created or updated

This is esèecially important because small changes (for example in the plotting logic or form handling) can easily break the application.

### What is automated in CI
CI focusses on making sure that the FLask application can be built and started correctly.
#### Dependency installation
All Python libraries required by the porject ar einstalled automatially, such as:
- Flask
- NumPy
- Matplotlib
This verifies that:
- The *requirements.txt* file is correct
- All dependencies are compatible
If a library is missing or misconfigured, the pipeline fails immediately.

#### Backend validation
The CI pipeline checks that the FLask application code is valid:
- The main file can be imported without errors
- There are no syntax or module import issues
- THe plotting logic does not crash at import time
This is important becasue the app performs several operations:
- Numerical calculations for portfolio growth
- Creation of arrays with numpy
- Dynamic generation and saving of plots

A small mistake (for instance, wrong variable name, missing import) would break teh web app. With CI it is possible to catch this early.

## Continuous deployment (CD)
Continuous Deployment ensures that once the application passes all CI checks, it is autmatically prepared and delivederd to a hosting enviroment.




## What is automated in CD
### Application packaging

After CI succeeds, the exact version of the project is prepared for deployment. This includes:
- Flask application file
- Templates (homepage.html, result page)
- Static files (CSS, images folder)

This guarantees that the same code that was tested is the one being deployed.

### Deployment to a web hosting platform
GitHub Actions can automatically deploy the project to a platform that runs Python web apps (for example Render, Heroku, or a VPS).

This step includes:
- Uploading the code
- Installing dependencies on the server
- Starting the Flask application

### Handling static content

Since the app generates plots and saves them in the static/images folder, deployment ensures that:
- The static directory exists
- The server can correctly serve generated images
- This is essential for the result page where the plot is displayed.

### Why CD is important for this project

- Removes the need for manual uploads or server configuration
- Ensures the web app is always in a deployable state
- Reduces human errors during release
- Makes updates to calculations, styling, or templates available quickly

## Summary

In Helpinvest, CI/CD:
### Automates:
- Environment setup
- Dependency installation
- Backend validation
- Deployment

### Protects:
- Financial calculation logic
- Plot generation
- Flask routing and templates
- Static file handling

GitHub Actions connects version control with testing and deployment, ensuring that every change to the web application is automatically verified and safely delivered.


















