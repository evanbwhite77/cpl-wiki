## Introduction

At the California Policy Lab, much of our analytic work takes place on
our remote servers where three primary computing resources - RAM, disk
space, and processing cores - are shared simultaneously by numerous
people. This guide will detail how each of these three resources are
used during the course of an analyst's general workflow, and provide a
list of suggestions for how to minimize your use of each.

**Note**: A google doc version of this page with more detailed
walkthroughs of task scheduling and batch mode can be found
[here](https://docs.google.com/document/d/1DA06ZHr6MjrdPdL_4RkwAlZsDjlhvOFEWQkiy1GYlNs/edit?usp=sharing).

## Defining the Terms {#defining_the_terms}

**Random Access Memory,** or RAM, is where the server temporarily keeps
data currently in use by applications. It can be thought of as short
term memory, something in use only when needed and then either discarded
forever or saved to long term memory.

The server's long term memory is its **disk space** or **hard drive.**
The hard drive can be thought of as a stable storage space. The server's
capacity to save data to the hard drive is much greater than its
capacity to hold things in RAM, much like our own long term memory is
able to hold much more than our short term memory.

In a simple example, when you log on to our server and browse the files
there, you are looking at data saved on a hard drive. When you open a
file in any software package in order to check out the contents or
perform some data cleaning or analysis tasks the server allocates a
portion of its available RAM (short term memory) equivalent to the size
of the file while you do so. ***This memory remains held by you until
you close the file or software in use.***

In general, RAM is much faster than hard drives. Operating systems also
have a concept called **virtual memory,** which from the programmer's
and user's perspective operates in the same way as RAM, but is instead
implemented in a special area of the hard drive. The operating system
starts using virtual memory when it starts running out of RAM, which
explains why a computer tends to get much slower when RAM is fully
utilized, since it has to access the hard drive much more frequently.

Commands executed on the server while you have your data opened are
carried out by the **Central Processing Unit (CPU),** which is comprised
of one or more processing cores. The availability of multiple cores on
the server allows for multiple tasks to be completed simultaneously and
independently of each other. In order for multiple cores to be utilized,
the particular computational task needs to be something that can be
parallelized - i.e. divided between the multiple cores so that
processing can occur simultaneously without the subtasks 'stepping on
each other's toes'. As an analogy, thinking about cooking a meal with
others. It might be possible for someone to chop the garlic while
another peels the onions, but difficult or impossible for two people to
peel the onions simultaneously.

For independent programs or users that are using the computer at the
same time, the operating system will utilize multiple cores
automatically - for example, if you have both Excel and Stata open at
the same time, or if multiple users are using the server simultaneously.
Within a particular program or process, however, whether or not multiple
cores are utilized depends on the program and the particular task you're
trying to accomplish, since not every computationally intensive task can
be parallelized. In the world of statistics and data analysis, examples
of tasks that can be **parallelized** are the simultaneous evaluation of
multiple cross-validation folds, or the simultaneous estimation of a
model on multiple bootstrap resamples. Depending on the particular
software package or environment you are using, parallelization might
happen automatically, or it might need to be explicitly specified by the
user.

To illustrate how the concepts of RAM, disk space, and processing cores
work, it might be helpful to consider some examples of behavior that may
involve hogging these resources:

-   *Hogging RAM:* opening large files and leaving them open; using
    excessively wide datatypes (i.e. 64-bit integers when an 8-bit
    integer would do); inefficient coding practices, such as keeping
    live variables references to very large objects.
-   *Hogging disk space:* failing to clean up temporary files; in
    general, any practices that hog RAM will also hog disk space when
    the relevant file or data is saved to disk.
-   *Hogging CPU or processing cores:* executing long-running,
    computationally-intensive jobs when others are also using the
    computer; executing a job using multiple cores, when only a single
    core is required.

As you can see, as we add more users to the server the potential to
strain these three resources increases, and is in fact inevitable if
everyone treats the server as theirs and not ours. In order for us to do
our best work as efficiently as possible, we need to be cognizant of
each others' work flows and respectful of the shared resources on which
we all rely.

## General Guidance {#general_guidance}

-   Do not leave large files open or loaded into memory in Stata or
    Rstudio when you are not using them.

```{=html}
<!-- -->
```
-   **Regularly delete or archive files you have saved to long term
    storage, particularly "intermediate" or "temp" files, and files in a
    "scratch" folder.**

```{=html}
<!-- -->
```
-   It is worth repeating here that just having a file open so you can
    "see" the contents causes memory to be allocated to you whether or
    not you are actively "doing" something with it. If you are
    unfamiliar with a file and just need to see the contents, using data
    dictionaries (boy do we need more of these) can help you orient
    yourself to the data. You can also load a large file and then retain
    only a subset of the observations (best for "learning the data") or
    variables (best for when you've learned the data and know what you
    do and do not need for your analyses).

```{=html}
<!-- -->
```
-   Run code in batch mode.
    -   [Stata](https://www.stata.com/support/faqs/windows/batch-mode/)
    -   SAS: right click .sas file in explorer and select "batch submit"

```{=html}
<!-- -->
```
-   Check occasionally how much CPU and memory your program is taking to
    run. This can be easily done by opening the task manager
    **(ctrl+shift+esc),** clicking the "Users" tab, and finding your
    username. **If you are occupying more than 30% of the CPU for more
    than 30 minutes, consider rescheduling your program to run
    overnight, or letting other users know in advance.**

```{=html}
<!-- -->
```
-   Run computationally expensive code overnight/when not many other
    people are active on the server. The [Task
    Scheduler](https://www.stata.com/support/faqs/windows/batch-mode/)
    on the remote desktop server can be used for this.
    -   Click the windows icon in the bottom left corner of the remote
        desktop. Begin typing "task scheduler." Windows will suggest the
        correct program after a few letters.
    -   Once you've launched Task scheduler, click "Create Task." In the
        "General" tab, fill in the "Name" and "Description" fields.
    -   Click the "Triggers" tab and schedule a "One time" run at a date
        and time of your choosing.
    -   Click the "Actions" tab, then click "new" and enter the
        following

**Stata:**

1.  Enter `C:\Program Files (x86)\Stata15\StataMP-64.exe` into the
    "Program/Script" box (or browse to that folder & click the
    StataMP-64 icon).
2.  Enter `/b E:\Projects\YOURPROJECT\YOURCODE.do` into the "Add
    arguments" box.
3.  Leave the "start in" field blank.

**Sas:**

1.  Enter `C:\Program Files\SASHome\SASFoundation\9.4\sas.exe` into the
    "Program/Script" box (or browse to that folder & click the sas
    icon).
2.  Enter `E:\Projects\YOURPROJECT\YOURCODE.sas` into the "Add
    arguments" box.
3.  Enter `E:\Projects\YOURPROJECT\` into the "Start in" box.
4.  Click "ok" and your task will be added to the Task Scheduler
    Library. You can right click your task and edit, disable, or delete
    as need be.

## Program Specific Guidance {#program_specific_guidance}

### Stata

***The easiest way to increase Stata's processing speed when using very
large data is to subset the data when exploring data or writing code.***
This can be accomplished several different ways:

-   If you only need a small number of observations in order to learn
    the data or test out a loop, read in a limited subset of the data:

:

    :   `Use in 1/``<n>`{=html}` E:\FILEPATH\FILENAME.dta`
    :   Where `<n>`{=html} is the number of observations you'd like to
        read in.

-   If you only need a few variables from a large file, read in only
    those variables:

:

    :   `Use Var1 Var2 Var3 using E:\FILEPATH\FILENAME.dta`

-   If you only need observations meeting a certain condition, read in
    only those:

:

    :   `Use E:\FILEPATH\FILENAME.dta if (year == 2016)`

-   You can also combine the previous two methods as follows:

:

    :   `Use Var1 Var2 Var3 if (male == 1) using E:\FILEPATH\FILENAME.dta`

-   An easy way to avoid RAM hogging is to [set the maximum
    memory](https://www.stata.com/manuals13/u6.pdf) at the Stata command
    prompt, or at the top of your do-file, by issuing the command:

:

    :   `set max_memory ``<value>`{=html}

```{=html}
<!-- -->
```

:

    :   Where `<value>`{=html} is something reasonable - like 4g (i.e.,
        4 gigabytes).

**\'\'A slightly more involved method of increasing processing speed is
to run your code in [batch
mode.](https://www.stata.com/support/faqs/windows/batch-mode/)**\'\'
This is very useful when you know you have a large number of models to
run, or are running a large number of loops through a large dataset.
Displaying your output in the Stata window takes up a lot of resources,
and makes your job complete more slowly. **It is much more efficient to
let Stata run the do file and write the log file in plain text in the
background.** Batch mode also reduces RAM/CPU usage on the Vm you are
working on.

**To run in batch mode on the Remote Desktop:**

1.  Open Command Prompt (**win+R** then type "cmd")
2.  Change to the E:\\ directory

:

    :   `E`

1.  Batch mode will automatically write a logfile in the directory it is
    executed from. Accordingly, change directory to where you would like
    the logfile saved if separate from your code. CPL's Coding Handbook
    advises keeping code and logs together.

:

    :   `cd “E:\Projects\Yourproject\code"`

1.  Type the following line & hit enter:

:

    :   `StataMP-64 /b “code.do”`

```{=html}
<!-- -->
```

:

    :   Or, if you are trying to build a Stata project:
    :   `StataMP-64 -b project projname, build`

```{=html}
<!-- -->
```

:

    :   **/b** tells the shell to notify you that the code is done
        running

-   Even better than running computationally expensive code in batch
    mode is to run that code in batch mode overnight/when not many
    people are active on the server. The [Task
    Scheduler](https://www.stata.com/support/faqs/windows/batch-mode/)
    on the remote desktop server can be used for this.

1.  Click the windows icon in the bottom left corner of the remote
    desktop. Begin typing "task scheduler." Windows will suggest the
    correct program after a few letters.
2.  Once you've launched Task scheduler, click "Create Task." In the
    "General" tab, fill in the "Name" and "Description" fields.
3.  Click the "Triggers" tab and schedule a "One time" run at a date and
    time of your choosing.
4.  Enter `“C:\Program Files (x86)\Stata15\StataMP-64.exe”` into the
    "Program/Script" box (or browse to that folder and click the
    StataMP-64 icon).
5.  Enter `“/b E:\Projects\YOURPROJECT\YOURCODE.do”` into the "Add
    arguments box.
6.  Leave the "start in" field blank.

### Python

-   Be efficient with your use of Pandas datatypes. By default, all
    Pandas numeric types are 64-bit (float64 or int64). For the vast
    majority of data you will not need such wide datatypes - for
    example, the maximum value for an int64 is 263 − 1. Use the
    **pandas.to_numeric** function with the **downcast** parameter to
    convert to 8, 16, or 32-bit representation.

```{=html}
<!-- -->
```
-   Strings in Python are represented as objects and consume a lot of
    memory. If you have categorical data, try converting to an efficient
    numeric representation first, or use the **category** type in
    Pandas.

```{=html}
<!-- -->
```
-   A Python object such as a Pandas dataframe will be retained in
    memory so long as references to it exist in your code. Be sure to
    set any references to a dataframe you no longer need (including
    slices of the dataframe) to **None.** (This will be done
    automatically for local variables within a function).

```{=html}
<!-- -->
```
-   Be aware of the different performance profiles for different
    statistical libraries (statsmodels, scikit). Statsmodels tends to be
    slower on large datasets - if you don't need its inferential
    features consider using scikit models. Also, be aware of the
    performance profiles of different solvers for a particular model -
    e.g. stochastic gradient descent solvers tend to be faster but
    require more hyperparameter tuning.

### R and R-Studio {#r_and_r_studio}

When using R, don't forget to clean up your open dataframes now and
again, particularly if you have several large files open at once.
Further tips can be found using:

:   `§ help("Memory-limits")`
:   `§ help("Memory")`

You can also try using [sparse
matrices](http://www.johnmyleswhite.com/notebook/2011/10/31/using-sparse-matrices-in-r/)
in R to greatly reduce the amount of memory that an object takes up. The
two main packages to do this are Matrix and Slam.

The basic idea, which becomes more important with bigger datasets is
that it's likely that for any particular variable, the number of rows
where the values are non-zero is relatively small. So sparse matrices
only keep track of indices where the value is non-zero, which in some
applications (particularly text), means that only information from about
5% (very roughly) of the total number of possible indices in a matrix
are actually kept in memory.

The caveat is that when you convert a data.frame or data.table or
regular matrix to a sparse matrix, each column has to be the same type.
But if you do, it'll clear up a lot of RAM on the server.

### SAS

SAS handles memory in a way that assumes there will never be enough RAM
and always be plentiful disk space. This makes sense from the
perspective of SAS being developed years ago when RAM was expensive and
in short supply. SAS does not automatically reserve or allocate memory,
even when you specify a specific amount with the MEMSIZE system option.
SAS will use only as much memory as it needs to complete a process, and
then release it. For example, a DATA step might require 20M of memory
and even if MEMSIZE is set to 500M, SAS will use only 20M of memory to
complete the job.

That said, you should still schedule large jobs to run at night or over
the weekend. Running in batch mode is also more computationally
efficient than running code in interactive sessions.