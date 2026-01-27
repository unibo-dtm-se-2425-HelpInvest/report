---
title: Developer guide
has_children: false
nav_order: 11
---

# Developer Guide
This section describes how developers can understand, extend and reuse the Helpinvest software. It focuses on the internal structure of the application and how its components can be leveraged to build additional functionality. 

## Project architecture
Helpinvest is implemented as a lighteweight Flask web applicaiton following a clear separation of concerns:
- The **Backend logic** is handled in *main.py*, which defines the Flask application, routes and business logic.
-  The **presentation layer** is implemented using HTML templates located in the *templates/* directory.
-  The ** statica assets** such as CSS files and images are stored in the *static/* directory.

This structure allows developers to easily identify where to apply changes or add new features. 

## Applicaiton entry point 
The main entry point of the application is the *main.py* file. The Flask app is initialized and executerd here. Developers can modify the server configuration (e.g. host, port, debug mode) directly in this file if needed.

## Backend logic and data flow
The application exposes a single HTTP endpoint that handles user input through GET requests. Input parameters include:
- Initial capital
- Monthly deposit
- Invesment duration
- Risk profile

These paramenters are processed within the route handler, where the investment growth is calculated using prededined interest rates. The results are stored in  Python lists, converted to NumPy arrays and used to generate a plot via Matplotlib.

Developers can extend this logic by:
- Adding new risk profiles or interst rates.
- Introducing more investment strategies (bimontly, every semester...)
- Modifying the inflation model

## Using the applicaiton as an API
Although Helpinvest is primarly designed as a web application, its core logic can be used programmatically.
Developers can refractor the investment calculation logic into separate functions or modules, enabling:
- Programmatic access to porfolio projections.
- Integration with other applications or services.

## Extending the user interface 
The frontend can be extended by:
- Adding new HTM; templates for addicitonal pages.
- Enhancing visualisations with more dtailed charts
- Improving form validation or user feedback

CSS styles can be modified in the *static/files/* directory without affecting backend functionality. 

## Plot generation adn file handling 
Plots are generated in dynamically using Matplotlib and saved as image files in the *static/images/* directory. Developers should be aware that each new plot overwrites the previous one. 
Possible changes and improvements could be :
- Generating unique filenames per session or user
- Returning directly as HTTP responses instead of saving them to  disk
- Adding export options (for instance PDF)



























