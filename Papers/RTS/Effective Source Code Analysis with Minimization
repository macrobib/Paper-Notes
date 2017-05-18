#### Effective Source Code Analysis with Minimization 
Reduce the cost of analysis and debugging of code by reducing the ineffective blocks of code(e.g. #ifdef).  
- A method to code minimization, while taking into account functional safety and real timeliness of the code.
- Tools exists with awareness for preprocessor directives during analysis. e.g. GNU cflow, Coccinelle etc.
- Compilers are increased effectiveness to the pre processing of the preprocessor directives and as such its better to include them as part of the analysis flow.
- Conditional code stripping to increase the effectiveness of code analysis similar to approach of cflow.
- Tries to address the difficulties with grep and gcc based approach, which required a complete build to trace through the build log to determine the appropriate gcc commands and the grep recipes.
- An OOPS approach to override the default linux make file and override the CHECK flag.
- The replace command being **make C=1 CHECK=minimize.py
CF="-mindir ../minimized-tree/"**
- Preprocess tweaks the gcc options with -E -fdirective-only to remove #ifdef and expansion of #include while preserving #define macros.
- Main implementation done through guided code removal in minimize.py.


##### Reference
[Minimize script for code refractoring](https://github.com/Hitachi-India-Pvt-Ltd-RD/minimization/blob/master/minimize.py)