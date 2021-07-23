# California Employment Development Department (EDD) {#california_employment_development_department_edd}

## Background

The California Employment Development Department manages the
Unemployment Insurance (UI) and State Disability Insurance (SDI)
programs for the State of California. EDD is headquartered in
Sacramento. They hold a variety of administrative datasets related to
the labor market.

## CPL Research Partnership {#cpl_research_partnership}

The California Policy Lab has partnered with EDD in multiple ways- We
have used EDD\'s wage and employment data for CPL\'s analysis of the Los
Angeles Minimum Wage increase, we are producing a recurring analysis of
new initial UI claims in the context of the COVID-19 crisis, and we have
merged income data with HMIS data to study the employment patterns of
individuals experiencing homelessness. CPL has 2 embedded researchers at
EDD, Geoff Schnorr and Roozbeh Moghadam. Geoff and Roozbeh work both on
EDD projects through the Labor Market Information Division (LMID) and on
CPL projects - they are able to access EDD data that is only available
by being physically at EDD headquarters on behalf of CPL.

## Data Holdings {#data_holdings}

CPL\'s embedded researchers have access to a number of files of
interest, which are pulled from a larger SCDB (Single Client Database).

-   Wage Data

```{=html}
<!-- -->
```
-   UI Claims Data

EDD\'s administrative UI claims data comes from a series of transaction
level datasets made available to LMID. The data is sourced from 4 files,
and transformed into 6 simplified data files for CPL use. Each of these
6 datasets are at the claim level, with each observation summarizing key
information for a unique UI claim identified by the SSN of the claimant
and the start date of the claim. The files are:

# General UI Claims File {#general_ui_claims_file}

A relatively small dataset containing the key information that is likely
to be of interest to users in LMID. Data includes UI claims filed after
1/1/2000.

-   Sample: Universe of initial claims filed in CA since 1/1/2000
-   Level of observation: claim
-   Links to other datasets with: SSN and benefit year begin date (BYB)

What types of variables does the file include?

-   SSN Key (masked)
-   Benefit Year Begin date (BYB)
-   Claim program (UI only, UI-UCFE, Disaster Unemployment Assistance
    (DUA), etc.
-   DUA claim dummy
-   Percent Workshare (for universe of workshare claims)
-   Intrastate Claim indicator
-   Combined Wage Claim indicator (are base period earnings from
    multiple states combined?)
-   Weekly Benefit amount at initial claim filing stage
-   Maximum Benefit Amount (MBA)
-   Last WBA recorded in activity transactions data
-   Last MBA recorded in activity transactions data
-   Claim deemed valid or invalid at initial claim filing stage
-   Claim deemed valid as of last reported claim status
-   Number of weekly payments denied
-   Gender
-   Ethnicity
-   DOB
-   Last Worked Date
-   SIC code
-   Total number and \$ amount of regular payments
-   Total number and \$ amount of extension payments
-   Extension type(s)
-   Address Zip code, Zip+4

## Other Files Available at EDD Related to UI {#other_files_available_at_edd_related_to_ui}

-   Initial Claims File
-   Payments File
-   Extension Payments File
-   Unpaid Weeks File
-   Other Transactions File

## Base Wage File {#base_wage_file}

-   Includes quarterly wage data and info about employers

## Data Linking {#data_linking}

Data from EDD\'s Base Wage File has been linked to the HMIS.

## CPL contact person {#cpl_contact_person}

[Geoff Schnorr](mailto:geoffrey.schnoor@edd.ca.gov)