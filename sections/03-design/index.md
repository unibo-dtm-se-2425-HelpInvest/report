---
title: Design
has_children: false
nav_order: 4
---

# Design

This chapter illustrates the architectural, modelling, interactional, behavioural, and data-related strategies adopted to implement the system described in the analysis. The objective is to clarify how the software’s structure and behaviour derive from the identified requirements and how the chosen design solves the domain problems.

## Architecture
The implemented system follows a three-layered web application architecture, aligned with a classical Model–View–Controller (MVC) pattern:

### 1. Presentation layer:
- Implemented through HTML templates.
- Responsible for rendering views, presenting forms to the user, and displaying results.
  
### 2. Application layer:
- Defines the Flask application.
- Manages routing, orchestrates input processing, and coordinates the interaction between the presentation and domain layers.
  
### 3. Domain layer:
- Business logic functions modelling the investment-risk evaluation domain.
- Responsible for applying decision rules, computing outputs, and enforcing domain invariants.
  
## Technologies
### Front-end:
For what concerns the front end, Heplinvest was built using the main web application technologies: HTML and CSS. HTML defines the structure and organization of a webpage, while CSS controls its visual appearance and layout. The front end is composed by two pages: a homepage where the User can input the data and access relevant information, and a second page, where the resulting diagram is displayed. 
### Back-end:
Considering the back-end, the main technology used was Python, in particualr Flask, a lightweight web framework for Python that allows users to build web applications and APIs. This decision was taken because of the simple nature of the project, which did not require any more complex technologies. Additional Python libraries, such as Numpy and Matplotlib were used in order to create the diagrams to be displayed.

## Modelling

- This section explains how the domain has been modelled
- This section should contains some class diagrams
    - The application's most relevant design aspects are highlighted, showcasing how they solve the problems described in the analysis
    - Diagrams do not show implementation aspects that are not relevant, such as private fields
- This section describe how the tactical patterns and other aspects of DDD seen in class were applied


## Interaction
### User inputs data
While browsing the homepage of Helpinvest, the user can input the data they want to create their diagram. They need to input numerical data for the first three fields and select a pre-determined value for the last one. Then they can click on "Go" to generate their diagram.
### Diagram is generated and displayed
Once the values are entered, they are sent to the application layer, where the business logic is applied and the diagram is generated, using the Matplotlib library. The graph will be saved in a local folder (static>images) as a .png image, for easy access from the presentation layer. Then, a new page is loaded for the user, which will access the "images" folder and display the .png image saveed inside. Once in this page, the user also has the possibility to redirect to the main page in order to generate a new diagram, which will be saved over the old one in the "images" folder.

![Sequence Diagram](Sequence_Diagram_Helpinvest.png)

## Behaviour
The flowchart below shows what are the activities performed when using the application.
- User inputs data
- Data is sent to the Application Layer
- Diagram is generated
- Diagram is saved
- A new page is loaded, displaying the diagram
- User can go back to main page to generate a new one

  
  ![Flowchart](Flowchart_Helpinvest.png)
  
## Data-related aspects
The application is designed to be stateless and therefore it does not use any persistence technologies, such as SQL or NoSQL databases.
### Data handling
- User input values are sent via an HTTP POST request and exist in memory only for the duration of the request.
- No data is stored, logged, or persisted.
- Only validated data is passed to domain logic functions.
