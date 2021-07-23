# Sonoma County\'s Safety Net Departments {#sonoma_countys_safety_net_departments}

## CPL Research Partnership {#cpl_research_partnership}

This document provides a description of the data received by CPL for the
ACCESS Sonoma County project, and codebooks for each of the data files
used in CPL's analysis. The files described here are 5-year lookbacks
(data on services between 2013-2018), most of which were received by CPL
in July and August 2018 Secondary files that we received but have not
been cleaned or otherwise used are mentioned, but codebooks are not
provided.

More complete data documentation is available on the [CPL
Drive](https://drive.google.com/open?id=1oainz1Nc6YDp_J2RN_DexHqOpXHCeDii).

## Data Holdings {#data_holdings}

***Health data***

CPL receives 2 datasets from Sonoma\'s Department of Health
Services(DHS): **SWITS** (substance use treatment) and **AVATAR**
(mental health services).

-   AVATAR contains data from the Behavioral Health Division of DHS. It
    captures individual clients' treatment for mental health diagnoses.
    Each record represents an outpatient service provided to an
    individual client -- data points include demographics, mental health
    diagnosis, information on the service being provided, and billing
    details (insurance provider, amount billed, and more). The data
    covers services provided between July 2013-2018, capturing services
    provided to 8,381 individuals. Importantly, this data does not
    include inpatient or emergency mental health services.

```{=html}
<!-- -->
```
-   SWITS contains data from Sonoma County AODS (Alcohol and Other Drug
    Services). The data is on individual clients receiving treatment for
    substance use disorders. Each record represents an individual
    service provided to an individual client -- data points include
    client demographics, detailed data on the service being provided,
    and dollar amount that was billed for the service and to whom. This
    data includes inpatient and outpatient services; the longest
    enrollment captured in 1 record is 1 month. The data covers July
    2013 -- August 2018, capturing services provided to 12,527 clients
    in that time period.

***Criminal justice data***

Criminal justice data comes from the county\'s **Integrated Justice
System** which has data on bookings, sentences, case outcomes, and
probation terms.

-   Probation data carries information on all individuals with probation
    terms in Sonoma County. The main data file (original filename:
    "Active", renamed "ProbationCharges" when the 5-year data was
    pulled) contains basic information on each unique probation grant,
    including the start and stop date of the grant, the type of
    probation, and the convicted charges associated. The universe is
    individuals with active probation terms between 2013 and 2018; for
    each individual who meets that definition, all data on previous
    probation grants is also included in this dataset.

The file also contains basic demographic information on the individual
(race, gender, and details of most recent known address).

There are 9 additional data files that contain more robust information
on Probation clients. These have not yet been integrated into our
analyses.

***Housing data***

Sonoma\'s Community Development Commission (CDC) shares **HMIS
enrollments** and **HUD Assessment** data.

The Community Development Commission (CDC) is the county's housing
agency -- it runs affordable housing programs, homelessness programs and
systems, and more. The ACCESS Sonoma project is particularly interested
in homeless and housing unstable residents, and CDC has provided
multiple datasets to shed light on this population. The base file we
use, ProgramEnrollments, captures enrollments as early as 1992
(potentially a data error or idiosyncrasy), though 90% occur between
2010 and 2018.

-   ProgramEnrollments is a dataset that captures all records in HMIS of
    an enrollment into (and subsequent exit from) any housing program in
    Sonoma County. There are also other non-housing programs that are
    recorded in this data, such as some legal aid services. This data is
    sparse -- it contains only the program name and entry/exit dates --
    but it is the backbone of our housing-related analyses -- we use
    enrollment in a housing program as an indicator of
    homelessness/housing instability, and use additional datasets
    (Demographic_Data and ExportHmis2) for additional information.

```{=html}
<!-- -->
```
-   Demographic_Data is a separate file with demographic information on
    every individual known to the HMIS system. We match this data to
    ProgramEnrollments to capture demographic information on homeless
    and housing unstable individuals, including race/ethnicity, gender
    and age. This dataset also serves as our only way to identify
    individuals under the age of 18 in other datasets and remove them
    from our analyses.

```{=html}
<!-- -->
```
-   A third dataset, Hmis2, captures information from the HUD Assessment
    form, which is administered at least annually to individuals in HUD
    programs/shelters (at program entry, program exit, and annually if
    someone is enrolled for more than a year). This assessment captures
    lots of useful information -- for example, when done at program exit
    the form indicates where the individual is going - but the format of
    the data has made it, to date, difficult to analyze. At this point
    in time, it is only being used to create a crosswalk between
    ParticipantEnterpriseIdentifier (the internal HMIS identifier) and
    HMISpersonID (the ISD-generated identifier) in order to link the
    ProgramEnrollment dataset (which only has HMISpersonID) with the
    Demographic_Data dataset (which only has
    ParticipantEnterpriseIdentifier).

***Social services data***

Sonoma\'s Human Services Department (HSD) shares social service data
from its **CalWIN** system, which includes Medi-Cal, CalFresh, CalWorks,
etc.

-   Sonoma County's Human Services Department (HSD) administers the
    county's public assistance programs. The CalWIN data system tracks
    applications, eligibility, and enrollment information for public
    assistance programs, including Medi-Cal, CalFRESH, General
    Assistance, CalWORKS, and other programs. The main file used in this
    analysis, CalwinIndvCasePrograms, has information on each case
    active between January 2013 and August 2018. The data has details of
    the case (begin and end date, program(s) enrolled in, current status
    of the case) and demographic information on case beneficiaries
    (mostly primary beneficiaries, though some cases also have details
    on secondary beneficiaries). Supplementary data tables provide
    information on the all beneficiaries associated with a case and the
    amount of benefits allotted on a particular case over time
    (CalwinAllotments), all money allocated to individuals in the form
    of income payments (CalwinIncome) and records of the zip codes of
    individuals' known address (CalwinZipCodes). A mapping document
    originally created for IBM's work ("CalWIN Connect360 Data Mapping
    2018-02-09.xlsx") serves as a codebook for many of the fields in the
    IndvCasePrograms and Allotments files.

## Data Linking {#data_linking}

DHS\'s IT department (ISD) is responsible for linking and de-identifying
the data before it is sent to CPL. The crosswalk that CPL receives is a
\"master index\" with 1 row/individual, capturing every ID associated
with that individual across the datasets listed above.

ISD uses deterministic linking to load datasets iteratively; the fields
relied upon are generally SSN, name, and DOB.

***OSHPD data***

We have linked the Sonoma data to ASD, EDD, and PDD data from OSHPD
(2013-2018).

## CPL contact person {#cpl_contact_person}

Contact [Elsa Augustine](mailto:eaugustine@berkeley.edu) with any
questions