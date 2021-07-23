## Introduction

This handbook coalesces decades of experience held by our directors and
colleagues into a set of principles to ground the work we do. Most of
these guidelines were born from hard lessons learned along the way,
which we hope to help you as an individual, and us as an organization,
avoid making in the future.

Since the majority of our staff are Stata users, Stata is used as the
default language for code examples in the handbook. Users of R, Python,
and SAS should be able to apply the concepts demonstrated in the
examples to their preferred language.

We accept that there are numerous ways to approach nearly every
analytical task, and that there is often personal satisfaction derived
from writing particularly elegant or dense code. As beauty is ultimately
in the eye of the beholder, and the beholder in this case is the
leadership of this organization, adhering to a shared set of coding
practices will help produce what we see as beautiful work.

In essence, following a set of common code standards at the California
Policy Lab helps us to:

-   write readable, understandable, and easy to maintain code
-   reduce errors in our work
-   improve portability / reuse of code
-   create work that is easily reviewed by colleagues and peers

Our expectation is that everyone at the California Policy Lab uses the
guidance in each section of this document when working on any of our
projects.

*A print version of this document is available
[here](https://drive.google.com/file/d/1khgfrwytyWGv6H64LvvC9Dh8n6yxbVp4/view?usp=sharing).*

**Jesse Rothstein\'s seminar on coding practices at CPL, which draws on
and expands upon the principles in this handbook should be reviewed by
every new CPL employee who will be working with our data, including
GSRs.** The video and deck can be found
[here](https://drive.google.com/drive/folders/1NZXLFdXS6esoYauhxcLaHGPknMtoXzI3?usp=sharing).

## Project Management Standards {#project_management_standards}

### Folder set up {#folder_set_up}

Within your project folder, create the following

-   **Code** - for all code files, as well as their associated log or
    output files. **Always create and save
    [log](https://www.stata.com/manuals13/rlog.pdf) files**
-   **Output** - for all tables, figures, and other output intentionally
    separated from the full log or output file.
-   **SourceData** - for raw data not governed by a data sharing
    agreement and stored in E:/OriginalData such as a file of calls for
    service to LAPD downloaded through an open data portal
-   **WorkingData** - for datasets created en route to your analysis, as
    well as the final analytic file. As a rule of thumb, remove
    intermediary files once they are no longer needed, and don't count
    on the persistence of files stored in this directory, which may be
    wiped out if a project consumes too many resources.

Create an **/archive** folder within each of the above subfolders to
reduce clutter while preserving a record of your previous work

**Archive regularly**: code, logs, output, datasets. Keep your folders
clean!

### Naming Conventions {#naming_conventions}

**Use a descriptive filename for your code and carry it through to its
outputs:** Anything your code creates - log files, output, datasets,
graphs - should include the name of the code that created it. For
example:

-   A program that cleans IDs and then creates and stores a data set
    should be named **\"cleanIDs.do\"** and the data set it creates
    should be named **\"cleanIDs.dta.\"**
-   If the program creates several data sets, use the filename as a
    prefix as in **\"cleanIDs_unique.dta\"** and
    **cleanIDs_duplicates.dta.\"**
-   The log would be called **\"cleanIDs.log\"** and a table of summary
    stats would be called **\"cleanIDs_summarystats.txt.\"**

**_V2, _final, _finalV2, _test and other similarly meaningless file
suffixes are NOT acceptable as version control methods and should never
be used at CPL**

-   Date suffixes, if they must be used, should **always** be in
    YYYYMMDD format so that the sort order remains chronological across
    years, and for consistency.

### Log Files {#log_files}

**Always create [log](https://www.stata.com/manuals13/rlog.pdf) and
output files for review purposes.** These are just as important - and
sometimes more so - than formatted exhibits.

-   Log and output files should be saved in the same directory as the
    program that creates them
-   **\'Remember to carry the code's filename through to the log!** In
    Stata use the command
    **'[log](https://www.stata.com/manuals13/rlog.pdf) using
    cleanIDs.log'**
-   Avoid
    **\"[quietly](https://www.stata.com/manuals13/pquietly.pdf)\"** in
    Stata and **\"noprint\"** in SAS. Your log file should **always**
    show the full results for things like regression models, not just
    the coefficients you retain for an exhibit.
-   When you are ready to report your results - for publication or to
    PIs - freeze your log and output files by copying them into a
    subdirectory with the date the program was run for future reference.
    Better still, have your code do this automatically by using macros
    that reference the system date: **\'c(current_date)**\' in Stata,
    **\'%sysdate**\' in SAS.
-   In R, use a combination of *[R
    Markdown](https://rmarkdown.rstudio.com/)* output with the packages
    `tidyverse` and `tidylog` to capture useful information similar to
    what is logged in Stata programs.

### Code Headers {#code_headers}

**Before you write a single command create a header** at the top of all
code files to accurately and thoroughly describe what the code is
intended to do. Include the following:

-   Your name, the date the file was created, and the date last updated
-   Provide a general outline of the code\'s \"steps.\" E.g., the code
    first pulls a sample of 25-30 year olds arrested in 2017, randomizes
    them into treatment (n=2000) and control groups (n=2000), and then
    tests balance on gender, ethnicity, and prior arrest history.
-   Filepaths for all source data at the top of your code, and a short
    description of data being used (ie, person level vs person-event
    level, unique record/person/event identifier)
-   Important variable definitions, equations, and analytic assumptions.
    For example, define any indices being created, and specify the
    endogenous / exogenous variables, baseline variables, fixed effects,
    and standard error clustering in an IV regression
-   Provide a "change log," detailing what changes were made to the
    code, when, and by who. This should be updated every time the code
    is edited. This to some extent duplicates the functionality of Git
    check-ins, but allows for more detail about what was done to
    individual programs than is possible with Git.
    -   For example, one entry might read \"4/1/2019, Rothstein:
        Adjusted county-district merge to exclude missing values that
        had previously been erroneously included.\"
-   **Verify that your header continues to accurately describe the code
    as changes are made.**

### Single vs Multiple Code Files {#single_vs_multiple_code_files}

**Use a single program for small projects**, especially TA requests from
agency partners. The code should produce all requested output from the
raw data.

-   The header for these should include a description of the request,
    who requested it, and when.

**Plan to use a code \"master file\" if writing in stand-alone sections
for large research projects.** The master file will call each
stand-alone section in sequence, without modification, in order to
create your final results from the raw data.

-   This is helped by using descriptive filenames for your code such as
    **01_clean.do** / **02_build.do** / **03_analysis.do**
-   Each section's output should be the next section's inputs. For
    example, **01_clean.do** creates **01_clean_students.dta** and
    **01_clean_schools.dta.** Those files are called by **02_build.do**
    which creates **02_build_graduation_rates.dta**, which is then
    called by **03_analysis.do**
-   Try to reduce the amount of duplicative code across sections. For
    example, if your master file calls three different scripts that each
    create a different table, but all three run the same pre-processing
    code before doing so, consider either consolidating those three
    scripts into one, moving the pre-processing to an earlier code
    section, or creating a function in a supplementary file that can be
    called repeatedly.
-   Verify that each "section" will run correctly when executed from
    start to finish. Don't rely on Stata or R facilities to run only
    segments of a program at a time for anything more than initial code
    testing.
-   Verify that master file will run, and will generate the expected
    results, even if you delete all of the intermediate files before
    running it.

## Coding Expectations for All Projects {#coding_expectations_for_all_projects}

**Annotate your code throughout,** referring back to the steps detailed
in the header

-   Explain what each section of your code is meant to accomplish, and
    as appropriate, what the expected results are.
-   Comments need to be updated at the same time your code is: outdated
    or simply wrong comments are worse than no comments.

**Code simply:** you will be less likely to make errors and someone
reviewing or adding to your code will have an easier time following your
work.

-   Use meaningful variable and function names (e.g., age_at_arrest
    instead of arrage).
-   **[Label](https://www.stata.com/manuals13/dlabel.pdf)** variables
    and values.
-   Do not overwrite existing variables.
-   Retain only the variables you need as you code.
-   Avoid nesting complex functions.
-   Define loops in comments and make sure they are coded to match the
    definition.

**Use common packages and functions** like
**[Dplyr](https://dplyr.tidyverse.org/)** in R or
**[Estout](http://repec.sowi.unibe.ch/stata/estout/help-estout.html)**
in Stata over lesser known packages with similar features. This is
particularly important when running models as the default assumptions
may not be what you or your PI expect.

-   Use comments to describe what user-written packages or functions do,
    and why you are choosing to use them.
-   Make sure that the Mercury shared package repository contains a copy
    of any package you use, so that others running the code can use it
    as well.

**Verify your results are reproducible** by comparing them from two
separate runs. "Nearly the same" is not sufficient --- they should be
identical, at least up to machine precision.

**Use the [checklist for self
review](https://drive.google.com/a/berkeley.edu/file/d/1FbSnvOgJTk-b8oUoCQ44L-l20ftxxICd/view?usp=sharing)**
before having your code reviewed by someone else.

**Read [Code and Data for the Social
Sciences](https://web.stanford.edu/~gentzkow/research/CodeAndData.pdf)**
and then read it again in six months. You'll be surprised what you pick
up the second (or third) time around.

## Task Specific Guidelines {#task_specific_guidelines}

### Data Management {#data_management}

-   Always use directory references or explicit file paths in your code
    rather than using \"change directory\" statements to load data from
    or store output to a particular location. It is easy to lose or
    overwrite data and more seriously to inadvertently expose data to
    unauthorized users.
-   Avoid the temptation to save new "in progress" datasets to disk at
    multiple points in your Stata code. These can quickly clutter up
    your /workingdata directory. Instead, save as many temporary files
    as you need
    (**[\"tempfile\"](https://www.cpc.unc.edu/research/tools/data_analysis/statatutorial/misc/temp_files)**
    in Stata) along the way, and permanently save only the final product
    to at the end of the program.
    -   Similarly, avoid using the Stata
        **[\"preserve\"](https://www.stata.com/manuals13/ppreserve.pdf)**
        and **\"restore\"** commands. This makes it difficult to debug,
        and can lead to irreproducibility when only sections of the code
        are run at a time. Again, use **\"tempfile\"** instead.
-   When a dataset is saved, it is useful to save a description to the
    log file. In Stata use
    **[\"describe\"](https://www.stata.com/manuals13/ddescribe.pdf)**
-   Retain only the variables you need as you code. For example, compare
    these two Stata methods of converting an individual-level dataset,
    containing a "Hispanic" indicator, to a county-level dataset with a
    variable representing the fraction Hispanic:

Option A:

`sort county individual_id`\
**[`isid`](https://www.stata.com/manuals13/disid.pdf)**` county individual_id`\
`by county: `[`egen`](https://www.stata.com/manuals13/degen.pdf)` county_percent_hispanic=mean(hispanic)`\
`by county: keep if _n==1`

Option B:

`sort county individual_id`\
`isid county individual_id`\
[`collapse`](https://www.stata.com/manuals13/dcollapse.pdf)` (mean) county_percent_hispanic=hispanic, by(county)`

The second option is preferable, as the resulting dataset will have only
the two desired variables, county and county_percent_hispanic. The first
option will also have all individual-level variables (including
"hispanic"), even though these have no meaning in the county-level
dataset. This leads to trouble.

-   Frequently check that your data contains the expected number of
    total observations and total unique observations. There are numerous
    ways to accomplish this, whichever you chose make sure you indicate
    in the comments before the check what your expectation is, and
    verify whether the expectation is satisfied after the check. Even if
    you already know what the checks will show, it is useful to have
    these results in the log or output files.
    -   Build these checks into the code! In Stata
        "**[assert](https://www.stata.com/manuals13/dassert.pdf)
        _N==153201**" will cause an error message if the sample size is
        not equal to 153,201. Even better for logging purposes is
        **["count"](https://www.stata.com/manuals13/dcount.pdf)**
        followed by **"assert r(N)==153201"**
-   ID variables / keys should be stored as text rather than numeric if
    at all possible
    -   In Stata if ID / keys must be stored as numeric fields, they
        should always be stored as doubles. Too-small variable types can
        lead to automatic rounding of ID variables, creating duplicates
        and mis-matches. For example 1122334456 and 1122334457 would
        become 1122334450. This rounding happens if the information is
        ever stored in too small a type; it isn't enough to generate a
        new double if you've previously had the information in a long.
    -   In other packages, the specific code differs but the idea is the
        same. For example, in SAS any numeric ID variable should be
        explicitly created as length 8 (though text IDs are preferred).
    -   Be consistent about how IDs are formatted \-- an SSN formatted
        as 012345678 will not successfully merge to one formatted as
        012-34-5678, even when both are strings.
-   **Never convert Social Security numbers to numeric format.** Valid
    SSNs can begin with \'0\' or \'00\' converting to numeric will cause
    information loss.
    -   Be consistent about how IDs are formatted \-- an SSN formatted
        as 012345678 will not successfully merge to one formatted as
        012-34-5678, even when both are strings.
-   **If random numbers are generated, always set a seed set so they can
    be recreated.** Use **[\"set
    seed\"](https://www.stata.com/manuals13/rsetseed.pdf)** in Stata.
-   Verify that variables created have the expected range (eg GPA on 0-4
    point scale) and amount of non-missingness

### Sorting Datasets {#sorting_datasets}

-   Stata breaks ties randomly and irreproducibly when it
    **[sorts](https://www.stata.com/manuals13/dgsort.pdf)**. This means
    that it is imperative to ensure that you never sort on a set of
    variables that does not uniquely identify observations.
    -   If your data does not have unique key before sorting, create one
        when you first read the data set (e.g., in Stata use "gen
        uniqueid=_n"). Once you have that, you can always add this
        variable to the end of the sort statement to ensure a unique
        sort order (i.e., "sort x1 x2 x3 uniqueid" rather than "sort x1
        x2 x3")
    -   Use **["isid"](https://www.stata.com/manuals13/disid.pdf)**
        frequently, ideally before any sort statement, to ensure that
        your sort variables uniquely identify observations.
-   When running any command that relies on the data sort order (e.g.,
    "**[duplicates](https://www.stata.com/manuals13/dduplicates.pdf)**
    drop" in Stata), be sure you have sorted the data on a unique key
    beforehand.
    -   In general, don't let the software make decisions; make them
        yourself. So, for example, rather than typing **"duplicates drop
        x1 x2 x3, force"**, which tells Stata to pick one observation
        from each unique combination of x1, x2, and x3, without guidance
        about how to pick it, instead use the following:

`sort x1 x2 x3 uniqueid`\
`isid x1 x2 x3 uniqueid`\
`by x1 x2 x3: drop if _n>1`

### Merging Datasets {#merging_datasets}

-   Never **[merge](https://www.stata.com/manuals13/dmerge.pdf)** when
    you mean to
    **[append](https://www.stata.com/manuals13/dappend.pdf)**
-   Never append when you mean to merge
-   Ensure that there is a primary key in each dataset before merging.
    -   If your data does not have unique key before merging, create one
        when you first read the data set. In Stata use **"gen
        uniqueid=_n"**
-   Always check for missing values on key variables before running
    merges. Do you want a missing key value on one dataset to merge to a
    missing value on the other dataset? Make sure your log or output
    file captures the checks you run.
-   Always sort your data on the primary key(s) before merging.
-   Be clear in your code whether your merge is 1-to-1, 1-to-many, or
    many-to-many.
-   After a merge always check that the resulting data set contains the
    number of observations expected. Capture this check in your log or
    output file
    -   Watch out for joins that inadvertently drop non-matching
        observations.
    -   If observations in one dataset do not have analogues in the
        other, your code and comments should make clear why, and what is
        to be done with these observations. For example, if linking a
        file containing LA residents in 2018 to California wage records
        in 2017, you would expect that not every LA resident in 2018
        would expect some people not to have wage records due to age,
        unemployment, or having worked outside of California in the
        prior year.
    -   Be careful when merging two files that have variables in common
        other than the merge keys (eg both sets have a \"gender\"
        variable). Most software programs will either overwrite the
        values in the primary data set with the values from the second,
        or will drop the information from the secondary data set. In
        either case, the software is unlikely to alert you to this
        information loss. Instead, either drop or rename the variable in
        question from the incoming data set and recode the variable in
        the master data set as needed after the merge.

### Regression and Hypothesis Testing Checks {#regression_and_hypothesis_testing_checks}

-   **Make sure that your log file contains the full regression
    output.**
    -   For large regressions with many covariates, or when many models
        are being considered, it is useful to generate a more compact
        table of results as well, with several models together and only
        a subset of the coefficients. In Stata,
        **[estout](https://www.ssc.wisc.edu/sscc/pubs/stata_tables.htm)**
        is a commonly used packaged for creating regression tables.
    -   In cases where you generate table output to read directly into
        another program (e.g., .csv to read into Excel, or a LaTeX
        formatted table), generate a human-readable version as well.
-   Ensure that numeric variables representing categories (e.g., school
    id, grade level) are properly specified as factor / class variables
    rather than continuous variables by placing an "**i.**" before the
    variable name in Stata.
    -   Use **[base level
        coding](https://www.stata.com/manuals13/u11.pdf#u11.4.3.2Baselevels)**
        to explicitly set the excluded category for each categorical
        variable in a regression or post-estimation test
-   **Make sure the models uses the expected number of observations.**
    -   A useful check before running your regression is to run summary
        stats on all covariates and outcomes just before your first
        model statement. **Write this into your log file.**
    -   **Never let software decide which variables to drop due to
        collinearity.** If any variables are being dropped due to
        collinearity that is a sign that something about the data
        configuration or model specification is different from what you
        expected and must be addressed.
    -   If the number of observations in your regression does not match
        the number of observations in your outcome measure, explain why
        in your code. If you can\'t explain why, you have a problem.
    -   It is best practice to use "if" on regression commands in Stata
        explicitly limit the sample to the one you want, rather than to
        allow the program to pick the sample based on observations with
        non-missing values. Equivalent subsetting capacities are
        available in other languages.

## Additional Resources {#additional_resources}

### Style Guides {#style_guides}

-   [Gentzkow and Shapiro: Code and Data for the Social
    Sciences](https://web.stanford.edu/~gentzkow/research/CodeAndData.pdf)
-   [Google's R guide](https://google.github.io/styleguide/Rguide.xml)
-   [Stata Coding
    Style](https://michaelshill.net/2015/07/31/in-stata-coding-style-is-the-essential/)
-   [Best Practice Programming Techniques for
    SAS](https://support.sas.com/resources/papers/proceedings17/0175-2017.pdf)
-   [CPL North\'s Frequently Used Stata Codes Google
    Doc](https://docs.google.com/document/d/1IUjJ-mZ8MTOfQjRM1-Gp-UNFZcNc_bMioNu8JBR7rv8/edit?usp=sharing)
-   [Causal Inference Workshop
    Materials](https://drive.google.com/drive/u/1/folders/1gyXA0wJNHgNOKgXWkfN_2WlyUjMi9WaU=sharing)

### Git Tutorials {#git_tutorials}

-   [CPL GIT presentation: Why and
    How](https://docs.google.com/presentation/d/1-qHZlbLASGAmcDRvSv82sbHs0EtpBNmqmwLhZ6G4ysE/edit?usp=sharing)
-   [GIT at
    CPL](https://docs.google.com/document/d/1C4qooM1kAtby-ok9GYBhwgI8Zrczlr-P_iaE4ZSBEz8/edit?usp=sharing)
-   [Coursera](https://www.coursera.org/learn/version-control-with-git)
-   [CodeAcademy](https://www.codecademy.com/learn/learn-git)
-   [Atlassian](https://www.atlassian.com/git/tutorials)

### Server Resources {#server_resources}

-   [Shared Resources Best
    Practices](https://docs.google.com/document/d/1DA06ZHr6MjrdPdL_4RkwAlZsDjlhvOFEWQkiy1GYlNs/edit?usp=sharing)