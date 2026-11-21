# STAT 184 HW 4.3 Plan

## Part 1: Calcium Plan
### Goals:
Get, understand, and tidy the calcium dataset, and create a visualization comparing calcium measurements over time between the two treatment groups.

SG1: Have the original calcium dataset containing measurements from all 31 women in the two treatment groups.

SG2: Understand the structure of the original dataset, including its 16 rows, 8 columns, four measurement times (Initial, Year 1, Year 2, and Year 3), and missing values caused by the different group sizes.

SG3: Have a tidy dataset with 124 rows and 4 columns (Group, Woman_ID, Time, and Calcium), containing all valid calcium measurements from both groups.

SG4: Have a summary dataset with 8 rows, containing the average calcium measurement for each treatment group at each of the four time points.

SG5: Have a line graph comparing calcium measurements over time between the null treatment group and the diet/exercise group, showing both individual measurements and group averages.

SG6: Understand the main patterns in calcium measurements over time and the differences between the two groups.


### Needs:
Nouns:
calcium.csv, RStudio, tidyverse, calcium dataset, data frame, 31 women, null treatment group (15 women), diet/exercise group (16 women), eight original columns, four measurement times (Initial, Year 1, Year 2, Year 3), calcium measurements, column names, missing values, row identifiers, Group, Woman_ID, Time, Calcium, tidy dataset, summary dataset, group averages, line graph, x-axis, y-axis, colors.

Verbs:
importing, viewing, examining, checking, identifying, counting, renaming, creating identifiers, reshaping, filtering, grouping, calculating, ordering, plotting, comparing, interpreting, and verifying.

Functions and Operators:
`library()`, `read_csv()`, `View()`, `dim()`, `names()`, `str()`, `summary()`, `colSums()`, `is.na()`, `mutate()`, `row_number()`, `pivot_longer()`, `filter()`, `paste()`, `select()`, `group_by()`,
`summarise()`, `mean()`, `factor()`, `nrow()`, `n_distinct()`, `ggplot()`, `aes()`, `geom_line()`, `geom_point()`, `labs()`, `theme_bw()`, `!`, `=`, `==`, `|>`, `+`.

### Steps:

1. Set up the RStudio project.

A. Open RStudio and create an R script in the project.

B. Save the original calcium.csv file in the project folder without modifying it.

C. Load the tidyverse package using library().

2. Import and examine the original dataset.

A. Use read_csv() to import calcium.csv into a data frame named calcium.

B. Use View() to examine the dataset.

C. Use dim() to confirm that the dataset contains 16 rows and 8 columns.

D. Use names() and str() to examine the column names and check that the calcium measurements are numeric.

E. If any measurement columns are not numeric, investigate the problem before continuing.

3. Identify the two treatment groups and measurement times.

A. Identify the first four columns as the null treatment group with 15 women.

B. Identify the last four columns as the diet/exercise group with 16 women.

C. Confirm that each group has measurements for Initial, Year 1, Year 2, and Year 3.

D. Check how read_csv() handles the repeated column names in the original file.

4. Check for possible data issues.

A. Use summary() to examine the calcium measurements and identify any unusual values.

B. Use colSums(is.na(calcium)) to count missing values in each column.

C. Confirm that the four missing values are in the last row of the null treatment group.

D. Recognize that these missing values are expected because the null treatment group has 15 women while the diet/exercise group has 16.

E. Keep the last row because it contains valid measurements for the 16th woman in the diet/exercise group.

F. If any other missing values or unusual values are found, examine them before deciding whether they need to be corrected or excluded. Do not change valid numerical measurements.

5. Prepare the dataset for tidying.

A. Use names() to assign unique names to the eight measurement columns, identifying both treatment group and measurement time.

B. Use mutate() and row_number() to create a temporary row identifier for the original 16 rows.

C. Make sure the measurements are still associated with the correct treatment group, measurement time, and original row.

6. Create and verify the tidy dataset.

A. Use pivot_longer() to reshape the eight measurement columns into a long format, separating the treatment group and measurement time information.

B. Use mutate() and paste() to create a unique Woman_ID by combining the treatment group with the original row identifier. This prevents women from different groups from sharing the same identifier.

C. Use filter() and is.na() to exclude the four missing measurements while keeping all valid measurements.

D. Use select() to keep the four final columns: Group, Woman_ID, Time, and Calcium.

E. Use dim() to confirm that the tidy dataset has 124 rows and 4 columns.

F. Use n_distinct() to confirm that the dataset contains 31 unique women.

G. Check that the null treatment group has 60 valid measurements and the diet/exercise group has 64 valid measurements.

H. Verify that every valid measurement is associated with the correct woman, treatment group, and time point.

7. Calculate the average calcium measurements.

A. Use group_by() to group the tidy dataset by Group and Time.

B. Use summarise() and mean() to calculate the average calcium measurement for each treatment group at each time point.

C. Use nrow() to confirm that the summary dataset contains 8 rows, representing two treatment groups at four time points.

D. Check that the group averages were calculated from the correct measurements.

8. Create the calcium visualization.

A. Use factor() to order the time points as Initial, Year 1, Year 2, and Year 3.

B. Use ggplot() and aes() to create a graph with Time on the x-axis and Calcium on the y-axis.

C. Use geom_line() to show individual women's measurements over time, using Woman_ID to keep each woman's measurements connected correctly.

D. Use lighter, more transparent lines for individual measurements to reduce overplotting.

E. Add thicker lines using the summary dataset to show the average calcium measurements for the two groups.

F. Use geom_point() to show the group averages at each time point.

G. Use different colors to distinguish the null treatment group and the diet/exercise group.

H. Use labs() and theme_bw() to add clear titles, axis labels, and a readable appearance.

9. Verify and interpret the final results.
   
A. Confirm that the tidy dataset contains all 124 valid calcium measurements from 31 women.

B. Check that no valid numerical measurements were deleted or changed.

C. Confirm that the graph shows both treatment groups at all four time points.

D. Check that the individual lines and group average lines represent the correct measurements.

E. Compare how the average calcium measurements change over time in both groups.

F. Describe the main patterns and differences shown in the graph without assuming that the treatment caused the observed changes.


## Part 2: GitHub Repository Plan
### Goals:

Create and maintain a public GitHub repository for STAT 184 HW 4.3.

SG1: Have a public GitHub repository containing the HW 4.3 QMD and PDF files.

SG2: Have a main branch and a dev branch to manage changes.

SG3: Have at least two issues with appropriate labels and commit references.

SG4: Have a complete README and a separate plan document.

SG5: Have meaningful commit history and at least one completed pull request, with the main branch updated.

### Needs:
Nouns:
GitHub repository, GitHub Desktop, Main branch and dev branch, the HW4.3 QMD and PDF files, README.md and PLAN.md, Two issues and labels, Commits and commit messages, Pull request

Verbs:
Create and publish a repository, Add and organize files, Create and switch branches, Create and label issues, Edit documentation, Commit and push changes, Link commits to issues, Merge a pull request, Check the final repository

### Steps:

1. Create a new repository for STAT 184 HW 4.3 using GitHub Desktop.
   
2. Publish the repository to GitHub and make sure it is public.
   
3. Create a development branch named dev_QW while keeping main as the main branch.

4. Add the QMD source file and PDF report from HW 4.3 to the development branch.

5. Commit the files with a meaningful message and push the changes to GitHub.

6. Create at least two issues for the README and plan document, and add appropriate labels.

7. Update the README with the project description, data sources, current plan, file organization, and contact information.

8. Create a separate PLAN.md file containing the calcium dataset plan and GitHub repository plan.

9. Make additional commits with clear messages and reference the related issues.

10. Check the QMD file and make sure all necessary files are included in the repository.

11. Create a pull request to merge dev_QW into main, including a title and description.

12. Merge the pull request, close the resolved issues, and check that main is up to date.

13. Review the repository against the assignment rubric and submit the public repository URL.


    
