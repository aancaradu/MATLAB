# Amplifiers with Op-Amp — MATLAB GUI

Project Author: Radu Anca-Valentina
Subject: Computer Aided Graphics
University: Technical University of Cluj-Napoca, Faculty of Electronics, Telecommunications and Information Technology

## Task

Graphical User Interface (GUI)
Must include:
Mathematical Figures: 1-2 figures with modifiable parameters (e.g., edit boxes).
Interactive Elements: Buttons/menus linked to documentation.
Images (JPG): Relevant visuals within the interface.

Written Documentation
Should include:
Title Page: Faculty, project title, student/teacher names, year.
Contents: Clear navigation.
Introduction: Brief MATLAB history and project relevance.
Theoretical Presentation: Detailed explanation of the project and equations used.
Results: Numerical analysis, GUI screenshots with explanations, and code snippets.
Conclusion: Summary, evaluation, and suggestions for improvement.
References: Cited sources (books, articles, links).
Appendices (Optional): Supplementary visuals and full code.
I built my project on the theme of Inverting and Non-Inverting Amplifiers with Op-Amp and their functionality, showing their impact on signals.

## Menu Structure

| Menu Item | Action |
|---|---|
| Front Page | Opens the project's front page (built with HTML/CSS) |
| Non-inverting Amplifier | Shows the non-inverting amplifier circuit diagram |
| Non-inverting Amplifier → VTC | Shows the voltage transfer characteristic of the non-inverting amplifier |
| Inverting Amplifier | Shows the inverting amplifier circuit diagram |
| Inverting Amplifier → VTC | Shows the voltage transfer characteristic of the inverting amplifier |
| Documentation | Opens the project's PDF documentation |
| Close | Closes the GUI window |

## Approach

The `gainNoninverting` and `gainInverting` functions take four inputs, Vo, Vi, f, and N, and:
- Compute the period from the given frequency
- Compose the input and output signals as sine waves over N cycles
- Verify the polarity relationship required for a valid non-inverting (both signals same sign) or inverting (opposite sign) configuration before plotting
- Compute and display the gain, Av
- Plot the input voltage, output voltage, and both waveforms together, with edit boxes to modify Vi, Vo, f, and N live, and a button to reset to initial values

A separate front page, built with HTML and CSS, is linked from the GUI's "Front Page" menu item.

## Results

Verified against a manual test case (Vi = 5V, Vo = 20V, f = 2kHz, N = 2), producing the correct gain (Av = 4) and correct number of displayed cycles. The reset button and live edit boxes work as intended, and the plots update correctly across a range of test values.

Two known limitations:
- Due to a period-computation bug, `gainNoninverting` and `gainInverting` must be run directly from the MATLAB code rather than through their GUI callback, which doesn't currently work
- An attempt to clamp the output voltage to VOH/VOL limits (via a `limitAmplification` function) only holds on the first run; editing values through the GUI afterward bypasses the limit

## Tools

Developed in MATLAB using its native GUI-building functions (`uicontrol`, `uimenu`) rather than App Designer, with custom callback functions handling gain computation and interactive plotting.

## Documentation

Full write-up covering MATLAB and op-amp theory, equations, experimental results, and code: [Radu_Anca_Valentina_Gr_e_2023_Documentation_Matlab_Project.pdf](./Radu_Anca_Valentina_Gr_e_2023_Documentation_Matlab_Project.pdf)
