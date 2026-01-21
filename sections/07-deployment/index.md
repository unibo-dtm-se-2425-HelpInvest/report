---
title: Deployment
has_children: false
nav_order: 8
---

# Deployment
This section describes the steps required to deploy the **Helpinvest** web application on a user's machine.
## System requirements
In order to run Helpinvest locally, the following software must be installed:
- Python 3.x
- pip
- Web browser

Optional but recommended:
 - Virtual environment
 - Git
## Running the application
These are the steps to follow in order to run the application locally:
- Start the Flask server from the project root directory.
- Open the Flask URL in a web browser to access the application.
- The user can now interact with the application.

## Notes on the Plot Generation
The application generates a new plot as a .png image in the static/images/ folder each time a user submits the form, if the folder does not exist it will be automatically created. The new plot image will therefore be overwritten over the previous (if any) plot image that was generated, and it will be displayed on the second page for visualisation.

 













