---
title: Validation
has_children: false
nav_order: 6
---

# Validation

## Testing
### Test Development Process
This chapter details the testing and validation processes conducted for the application to ensure its functional correctness and compliance with initial requirements. Due to the simplicity of the application, it was decided to carry out only manual testing, not integrating automting testing frameworks. 
The process was aimed at verifying two critical aspects:
- **User Interface (UI) Flow:** Checking that the application moves smoothly from the input page (homepage.html) to the results page (second_page.html) and back, with the plot generated correctly in between.
- **Model Logic (Calculation):** Calculating the financial scenarios using the tools available online, to ensure the Python logic in main.py produces mathematically correct results for compound interest, deposits, and inflation adjustment.

The manual testing confirmed that the application fulfills the core requirements: it accepts user inputs (capital, years, deposit, risk profile) and generates a visual representation of the projected portfolio value over time, successfully meeting the application's main functional requirement to help users visualise the effects of compound interest over a savings portfolio. 
The only issues that presented, was that when the first input provided by the user (related to the lenght in years of the investment), exceeded 100, the graphical representation would become less readable, due to the magnitude of the numbers that would need to be displayed.

### Acceptance tests
Acceptance testing was performed from the perspective of the end-user to ensure the application meets the functional, criteria defined for the application.
In the table below, some examples of how the tests were carried out.

| Acceptance Scenario (What the User Expects) | Test Input | Expected Outcome | Actual Outcome |
|---------------------------------------------|----------- | ---------------- |--------------- |
|The application can successfully run a full simulation and display the result plot. | Years: 10, Capital: 5000, Deposit: 100, Risk: Medium | A new page loads displaying a graph with four distinct lines (High, Avg, Low, Base Capital). | **PASS** The plot was successfully generated and displayed on second_page.html. |
| The application correctly handles the base case of an investment with zero monthly contributions. | Years: 5, Capital: 1000, Deposit: 0, Risk: Low | The graph shows portfolio growth only from initial capital. | **PASS** The final value was consistent with only initial capital compounding, confirming the deposit variable is correctly handled. |
| The core financial logic produces mathematically accurate results for a known simple scenario.| Years: 1, Capital: 1000, Deposit: 0, Risk: Low | Final Capital (Low Return) should be approximately €1040.82 (calculated as: €1000 * (1.04 / 0.98)). | **PASS** The plot and output data points matched the manual calculation, confirming the correct application of the formula and inflation adjustment (inflationrate = 0.98 and lowrate = 1.02 / inflationrate). |

The successful outcome of the Acceptance Tests demonstrates that the application meets all primary acceptance criteria:

- **Correct Calculation:** The financial model is validated and operates according to the specified compound interest and inflation-adjustment logic, providing reliable results.

- ** Usability and Flow:** The user interface is functional, intuitive, and allows the user to easily input their investment parameters and receive a clear, comprehensible visualization of the projections, fulfilling the requirement for a helpful tool.

- **Visualization Fidelity:** The Matplotlib generated plot correctly visualizes the different return scenarios (High, Avg, Low) relative to the base capital, allowing the user to correctly perceive the range of outcomes for their chosen risk profile.






