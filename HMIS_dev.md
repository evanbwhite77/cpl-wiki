**Page under active development**

## HMIS revised documentation (in development) {#hmis_revised_documentation_in_development}

Do not edit without consulting Dean, please.

## Introduction

A Homeless Management Information System (HMIS) is a local information
technology system used to collect client-level data and data on the
provision of housing and services to homeless individuals and families
and persons at risk of homelessness. Each Continuum of Care is
responsible for selecting an HMIS software solution that complies with
HUD\'s data collection, management, and reporting standards.[^1]

The U.S. Department of Housing and Urban Development (HUD) and other
planners and policymakers use aggregate HMIS data to better inform
homeless policy and decision making at the federal, state, and local
levels. HMIS enables HUD to collect national-level data on the extent
and nature of homelessness over time. Specifically, an HMIS can be used
to produce an unduplicated count of homeless persons, understand
patterns of service use, and measure the effectiveness of homeless
programs. Data on homeless persons is collected and maintained at the
local level. HMIS implementations can encompass geographic areas ranging
from a single county to an entire state.[^2]

The Los Angeles Homelessness Services Authority maintains the HMIS in
order to help the four Continuums of Care in Los Angeles and Orange
Counties provide effective services and information to assist
individuals who are homeless, or those at-risk, to achieve housing
stability and self-sufficiency.

The HMIS data held by the California Policy Lab comes from the Los
Angeles Homeless Services Authority (LAHSA), with whom CPL has two
separate agreements to receive identified and de-identified data. The
functional range of data is January 2010 to June 30, 2018. [^3]

From LAHSA, CPL receives csv files that contain information on both
clients and service providers. Data on clients range from detailed
demographic information to program enrollment and services received.
Service provider data include populations served, inventories of
services and resources, and funding sources, among other information.
These data are captured in seventeen separate csv files.

## HUD HMIS Documentation {#hud_hmis_documentation}

The U.S. Department of Housing and Urban Development\'s **HMIS Data
Standards Manual**
[1](https://www.hudexchange.info/resources/documents/HMIS-Data-Standards-Manual.pdf)
includes an overview of the HMIS and data dictionary. Link last updated
on 04/04/2019 with the April 2018 version.

HUD also has **CSV format specifications**
[2](https://hudhdx.info/Resources/Vendors/5_1_2/HMISCSVSpecifications6_12.pdf)
available on their website. Link last updated on 04/04/2019 with v6.12
from September 2018.

HUD\'s **Standard Reporting Terminology Glossary**
[3](https://files.hudexchange.info/resources/documents/HMIS-Standard-Reporting-Terminology-Glossary.pdf)
provides HMIS system vendors a foundation to best program HMIS-required
reports. It is also useful for analysts.

See more **HMIS resources** on HUD\'s website
[4](https://www.hudexchange.info/programs/hmis/hmis-guides/#coc-resources).

## Adsystech and Clarity {#adsystech_and_clarity}

In May 2017, LAHSA changed its HMIS software, from Adsystech Inc.'s
Enginuity to BitFocus's Clarity Human Services. The new Clarity system
went live in June 2017.

In the new version of the HMIS, new Unique Identifiers (UIDs) were
utilized. The UIDs refer to PersonalID (Client.csv), EnrollmentID
(Enrollment.csv), and ProjectID (Project.csv). In order to connect
service and project histories from the old and new systems, a
LAHSA-supplied crosswalk is used. The crosswalk can be utilized using
the following linking procedure.

[<File:HMIS> id mapping.JPG](/File:HMIS_id_mapping.JPG "wikilink")

After performing the linking process, we observed the following:

-   1.5% of Adsystech IDs do not have a corresponding new ClarityId
-   40.65% of ProjectEntryIDs do not have a corresponding EnrollmentID
-   20% of ProjectIDs do not have a corresponding new ProjectID

### Data Structure {#data_structure}

The variables within individual HUD elements extracted from Clarity can
differ from the Adsystech extracts. Some elements, like Affiliation and
Client contain the exact same set of variables. Others like Disabilities
have fewer variables in Clarity than were available in Adsystech. Others
have variables in Clarity that were not included in Adsystech extracts.
A comparison of the variables found in Clarty and Adsystech extracts can
be found in the details for each element.

### Data Quality {#data_quality}

There was an observable improvement in the data quality in the new
version. The new data set has more complete observations. The new data
also has fewer tangential variables

## Q&A with LAHSA Data Support Team {#qa_with_lahsa_data_support_team}

**Q: 10/1/2018, A: 11/8/2018**

What is the best way to determine when someone enrolled in rapid
re-housing is currently receiving RRH-related assistance?

-   All RRH providers should be inputting at least one service each
    month, whether that's just "Housing Search and Placement" for
    clients not yet housed, or some type of financial assistance for
    clients that are housed. If there are no services for more than a
    month, providers are trained to exit the client.

What is the best way to determine when someone enrolled in Permanent
Supportive Housing(PSH) is currently receiving PSH-related assistance?

-   If a client is enrolled in PSH it means he/she is receiving
    assistance and is housed.

Are exit dates a reliable variable for the end of RRH services?

-   Yes, providers are trained to exit the client if no longer receiving
    services.

Is there any way to classify a household as exited if they do not have
an exit date?

-   If a household is enrolled, they should be receiving services every
    month. Practitioners are required to enter an update every 30 days,
    even if it's something like "housing search assistance." If there
    has been no service update within the last 30 days, the practitioner
    forgot to exit the client. It's also possible they exited early
    (and/or disappeared), so the practitioner has not exited them yet
    (or forgot). This answer is particular to RRH, we learned that each
    project has different requirements, hence, some may have a different
    criterion to exit clients when an exit date was not recorded.

Some clients have multiple RRH enrollment enrollments, and their entry
and exit dates overlap. Does this mean their RRH assistance has been
renewed?

-   This is most likely a data quality issue. If a client is referred to
    another RRH program, then the referring provider would need to exit
    the client (to a non-PH destination if not yet housed, or RRH
    subsidy if housed) and then the new RRH would enroll the client into
    their program. If the client was already housed before the move, the
    new program is supposed to have the move-in date equal to the
    program entry date, even if they moved in prior (since the move-in
    date is not allowed to be prior to entry date).

"faamount" values are missing for a large proportion of clients enrolled
in RRH. We are using this information to determine shallow subsidy
eligibility. Is there a workaround or alternative method for determining
this?

-   That is the only field that contains the financial assistance
    amounts.

How does LAHSA define a single shelter -- by project ID or by address?

-   We do analysis by project ID.

In the crosswalk between Adsystech and clarity, there are multiple
person IDs in the old system that match to a single ID in clarity. This
occurs in 600 observations. Is there a process LAHSA uses to verify
these multiple Adsystech IDs are in fact the same single person in
Clarity?

-   This is due to duplicate clients from our old system being merged in
    our new system. This is done on a case by case basis as identified
    by our providers, so each case is reviewed for accuracy (similar
    name, DOB, SSN, etc).

After our conversation about the migration of clients from Adsystech to
Clarity, LAHSA was going to verify whether the mapping document
contained only clients enrolled in programs. If it was determined that
is the case, a new mapping file was going to be provided that covered
individuals who took the CES but were not enrolled. Any update?

-   It only contained clients that were enrolled. I\'ve uploaded to the
    fileshare a full crosswalk \[\"LA Clarity_Legacy PersonalID
    crosswalk.csv\"\] of client IDs from our old system to the new, and
    includes clients that were only assessed (not enrolled), in addition
    to enrolled clients.

**Q: 10/19/2018, A: 11/8/2018, A: 12/20/18**

As part of our prevention work, we would like to get a sense of the
distribution of prevention services enrollments across SPAs. We are
currently getting zip codes from the site and geography .csv files in
order to determine SPA. However, there are a large proportion of project
IDs we observe in the enrollment files that do not have a corresponding
address in the site/geography files. Have you come across this issue
before? Do you have any ideas for how we can move forward determining
addresses/zip codes?

-   We\'re currently going through a cleanup of active projects and
    reviewing their address information for accuracy. Once that process
    has been completed in the next couple of weeks, I can send you that
-   I am sending an updated project list, it should have many more
    addresses than the one in the data file sent months ago.
    -   Original filename: HIC_RDC_Programs_12.14.18
    -   Location on server: /updated project lists with
        addresses/projects_updated_w_address_12.14.18.xlsx in both deid
        and ided folders

**Q: 12/5/18, A: 12/6/18**

When did projects begin using the Prevention Targeting Tool? Should we
expect that families seeking prevention services before a certain date
never received this assessment?

-   I don\'t have the exact day, but the family version of the HP
    targeting tool was originally rolled out in December 2016. And yes,
    prior to that, prevention families would not have this assessment,
    as providers were not required to fill out a new assessment and
    backdate it.
-   The single and youth HP targeting tools were rolled out on 7/1/2018.

In the CES screening tool data, we see there are 3 versions of the tool.
When were they rolled out?

-   Version 1: 7/1/2013 (although this wasn\'t a fully fleshed out
    process until 7/1/2016).
-   Version 2: 7/1/2017
-   Version 3: 3/1/2018

To whom does the "UserID" refer to in the Services.csv files? Is this
the case manager?

-   It\'s the HMIS user that put the service into HMIS. This isn\'t
    always the case manager, as several agencies have data staff that
    input the data on the CM\'s behalf.

**Q: 12/20/18, A: 1/2/2019**

Do you have historical grant inventory information? The HUD website has
information on 2018 and 2017 for LA CoC online: [link
here](https://www.hudexchange.info/programs/coc/coc-giw-reports/?filter_Year=&filter_State=CA&filter_CoC=CA-600&program=CoC&group=GIW)
We are interested in similar data for 2016 and before, especially if it
was previously publically available.

-   I\'ll find out about the GIW, I\'m not sure why HUD doesn\'t have
    them posted for prior years. I\'ll ask around our CoC team and see
    if there are clean copies that we can share.

Regarding the rollout of prevention services: our understanding is that
prevention services were not available for families until 2016, and not
available for single adults until 2017. We do however, see prevention
services enrollments prior to 2016. Our belief is that these are single
veteran adults and families with a veteran as head of household.
However, over 35% of those enrollments prior to 2016 do not indicate the
HOH was a veteran (assuming the "veteranstatus" indicator is reliable).

-   I believe LAHSA funded prevention projects didn\'t start until
    around 2016/2017 like you stated, but there have always been
    non-LAHSA funded prevention projects as well. The two main sets of
    projects are:
    -   SSVF prevention and rapid re-housing, for individuals and
        families with veterans (the veteran does not need to be the
        HoH). Started in October 2012.
    -   HUD HPRP (prevention and rapid re-housing) projects, which
        operated from 2009 to 2012.

Crosswalk question: the first crosswalk you sent us a few months ago
included a crosswalk from adsystech projectentryid to clarity enrollment
id. Our attempts to link between adsystech and clarity show that about
20% of the projects from adsystech do not have new clarity IDs. Do these
projects no longer exist after May 2017, or were some projects not
migrated to Clarity in the same way that not all clients were initially
migrated?

-   Not all programs were migrated from Adsystech to Clarity. Many of
    the assessment only/coordinated entry programs were not transferred,
    as we took the assessment data from those enrollments and imported
    as stand-alone assessments (Adsystech required a program for all
    assessments, while Clarity does not). We also did not transfer some
    projects that ended prior to 10/1/2012, or projects that entered an
    initial set of client data but never updated it.

**Q: 1/22/2019**

While analyzing financial assistance for rapid re-housing in the
services.csv file, we noticed that beginning in May 2017, there is a
drop-off in the number of services recorded for these clients. For
clients with move-in dates (which we're interpreting as a proxy for
being housed in RRH), we expect to see financial assistance records for
moving, rent, etc. in the services file, but only 7% of RRH households
have a service listed. For comparison, 91% of pre-May 2017 RRH clients
had at least one service record. Was there a change in the way
rental/moving/utility assistance was recorded starting May 2017?

Also, I know you are very busy right now, but just wanted to put in a
request for a data refresh for all HUD elements and assessment files
from 07/01/2018 to 12/31/2018.

**Q: 2/28/2019, A: 3/6/2019**

Have the priority score ranges on the VISPDAT changed over time?

-   Yes. It changed from a four point priority scale to a three point
    scale some time in the latter half of 2014. Before this change,
    clients with scores 1-4 were recommended for Market-Rate Housing or
    Affordable Housing, clients scoring 5-9 were recommended for Limited
    Term Rental Subsidy and Supportive Services, clients scoring 10+
    were recommended for Permanent Supportive housing. This VISPDAT
    (Version 1) had a 20-point acuity scale. LAHSA switched to the
    VISPDAT version 2 in early 2015, which changed the point scale
    to 17.

What percentage of clients are assessed with VISPDAT and never enrolled?

-   15.3% of clients are assessed but not enrolled in any program.

**Calls with Charisse about the administration of RRH and PSH programs**

-   Monday 12/03/18

\- Eligible people for RRH must be homeless according to LAHSA's
definition, this implies that not only people in shelters can access
RRH.

\- Basic eligibility criteria: Being homeless and have an income lower
than 50% of AMI. The source of income does not matter. Sometimes
screening tools are used such as VISPDAT, CES, triage tools, but their
use is at the agency's discretion.

\- Who conducts the assessments? It varies, agencies or case managers.

\- Are there any criteria to place people into housing? No, it varies by
case and there are no priority lists. When people are enrolled is
because they met the basic criteria and they start getting services,
sometimes there are capacity constraints, but there isn't a priority
constraint established.

\- How are case managers assigned to families? It varies by
organization. In general, it depends on caseloads, whoever has capacity;
however, in some cases, they are assigned to families that might be a
good fit based on veteran status, gender or other criteria.

\- How does the search for housing work? It varies, case managers or the
client (family) can be in charge.

\- Limits for assistance: 24 months. There can be extensions, but most
families get assistance for 5-6 months. Agencies do not advertise that
the assistance can last up to 2 years, because there are financial
constraints. Extensions are usually granted to people who are waiting
for PSH or other subsidies to go into effect.

\- In LA, as opposed to other contexts, there are no employment
requirements to keep receiving assistance. Although, case managers can
provide families with resources for finding a job. Sometimes their
current income is not enough to pay rent.

What is the ultimate goal of the program?

\- Take people off the street as quickly as possible and place them into
housing.

\- Reduce recidivism.

\- Make sure people are able to have an independent life.

-   Tuesday 12/11/18

\- Is there any way to distinguish people who go only for RRH from
people who eventually go for PSH? No, it depends on the case.

\- Are there any different criteria to place elderly population into RRH
as opposed to families or single adults? No.

\- Is the elderly demand for housing higher than the demand of other
types of families? We ask because it seems a priority for LAHSA, but we
don't observe many elderly who are head of households in the RRH
enrollment data.

\- Is it the case that RRH can be used as a waiting list for PSH?
Charisse said she wasn't aware of this but will ask.

**Q: 7/17/2019, A:**

For the Strategies A1 and A5 Evaluation, we are being asked to look at
all prevention projects that receive Measure H funding. It's our
understanding this includes some programs in the Long Beach CoC. Does
LAHSA have Long Beach's HMIS data?

How does LAHSA determine household type (TAY, family, single adult) in
the data? CPL's process is copied below. Is this LAHSA's methodology as
well?

-   Calculate head of household's age at enrollment
-   Count number of individuals per household per enrollment to get
    household size
-   Calculate ages of household members to determine if there are any
    minor children present
-   Use rules re: relationship to HOH, household size, and household
    members' ages to define household type
    -   Family: At least 1 guardian (HOH) and 1 minor child (age \<18)
    -   Single Adult: HOH is aged 25+, household size of one
    -   TAY: HOH is between 18 and 24, household size of one
    -   Others:
        -   Unaccompanied minor: HOH's age\<18, household size of one
        -   Other: all other household structures

Does LAHSA use only the *livingsituation* and *lengthofstay* variables
to determine how long someone has been homeless at the time of service
enrollment? We see these variables have high rates of missingness in the
data. Is there another way to calculate length of homelessness prior to
entry?

Does LAHSA have a way to calculate duration of current homeless spell?

How does LAHSA determine the time periods which an individual is deemed
literally homeless (either documented and/or self-reported)? How closely
are the [HUD
guidelines](https://files.hudexchange.info/resources/documents/Client-Level-Length-of-Time-Homeless-Reporting-Specifications.pdf)
followed for doing so? For example, is *DateToStreetESSH* column used to
determine duration of self-reported homelessness before enrollment in
PSH?

Does LAHSA consider clients currently enrolled in projects to be
homeless unless they are placed in housing units through RRH or PSH? Are
there any other projects aside from RRH and PSH in which someone is
enrolled and would thus no longer be homeless by HUD standards?

As you informed us earlier this year, in mid-2018, LAHSA provided
guidance on tracking diversion services in the HMIS. Service providers
were instructed to enroll these clients into the "Services Only" project
type and indicate "Diversion" in the project name. Is there any way to
discern diversion clients from prevention clients in the data prior to
mid-2018?

Lastly, is there any update on our request to receive PTT data for
individuals and families?

## HUD Elements {#hud_elements}

*Add description of HUD elements*

### Affiliation

**Description**

Provides information about the association between Services Only
projects (project type = 6; variable "ProjectID") and lodging projects
(variable "ResProjectID"). Each observation is a unique lodging project
affiliated with a Services Only project

**Known data issues**

The DateCreated variable contains dates that go as far back as
01/01/1900, which is presumably a default date if one is not entered. No
other data issues identified as of October 2018.

**Use Cases**

The affiliation.csv file contains technical information about the
projects in the HMIS. As of October 2018, CPL has not used
Affiliation.csv on a research or technical assistance project.

### Client

**Description**

The client file contains demographic and military service information
about each client in the HMIS system. Each observation is an individual
who has been enrolled in an HMIS project and/or been assessed by an HMIS
project. Clients who were active in a project from 2012 forward were
transferred from the old HMIS system (AdSystech) to the new Clarity
system and assigned a new personal identification number. LAHSA has
provided a client crosswalk to allow for longitudinal analyses.

**Known Data Issues**

After the switch from AdSystech to Clarity in 2017, service providers
noticed duplication of client files, where a single client was entered
into HMIS more than once and was thus given two or more personal
identification numbers. Providers have been working with the LAHSA HMIS
team to de-duplicate records. Conversely, they have also been working on
creating new records for multiple clients who were erroneously entered
into HMIS as a single individual.

**Use Cases**

The client and enrollment files are the foundation of the HMIS. The
client file is used in all analyses to connect HMIS enrollments to
individuals in order to obtain demographic information or create a data
set for longitudinal analysis.

### Disabilities

**Description**

The file includes information on physical disabilities, developmental
disabilities, chronic health conditions, HIV/AIDS, mental health issues,
and substance use disorders. Each record is for a disability type,
project entry ID number, and personal ID number. This means each project
entry identification number will have multiple observations, one for
each disability type. Disability information can be collected at entry,
case file update, and/or exit. The time at which this information is
collected is indicated in each observation\'s DataCollectionStage
variable.

**Known Data Issues**

No known issues.

**Use Cases**

In the EDD-HMIS merge, CPL used disability data to estimate who among
homeless service clients would be more likely to demonstrate attachment
to the labor market. Disability data has also been used to estimate
eligibility for potential programs, as disability is a service
requirement for the more costly HMIS housing interventions.

### Employment and Education {#employment_and_education}

**Description**

Provides information about education level, school status, and
employment status.

**Known data issues**

Values for key elements (lastgradecompleted, schoolstatus, employed,
employmenttype, notemployedreason) are largely missing.

**Use Cases**

As of July 9, 2019, CPL has not used this file for research of technical
assistance projects.

### Enrollment

**Description** The core for all enrollment data, this file includes
date of enrollment, disabling condition indicator, and residential
history such as prior residence and history of homelessness. Some of
these elements can be combined to impute chronicity. They are
livingsituation, lengthofstay, timeshomelesspastthreeyears,
monthshomelesspastthreeyears, disablingcondition.

**Known Data Issues** Some elements have a significant proportion of
missing values, such as timeshomelesspastthreeyears and
losunderthreshold.

**Use Cases** Because enrollments are at the core of our homelessness
data work, this file has been used in all of our projects, such as the
technical assistance for LAHSA\'s Ad Hoc Committee on Black People
Experiencing Homelessness, the EDD-HMIS merge, and the LA County
Predictive Analytics project.

### Enrollment CoC {#enrollment_coc}

**Description** This data links project enrollments to their appropriate
Continua of Care in Los Angeles County. Our less-identified data pulls
from 2018 and 2019 include enrollments from the Glendale (CA-612) and
Pasadena (CA-607) Continua of Care, in addition to the Los Angeles City
and County Continuum of Care (CA-600).

### Exit

**Description** This data includes information recorded upon exiting a
client from a program. Information includes exit date and housing
destination. There should only be one exit per enrollment.

**Known data issues** Many of the elements\' values are missing in the
majority of observations. Destination can be a helpful element for
projects, but it is largely missing in the biggest project types
(emergency shelter, for instance). However, the quality of the
destination element is better for more resource-intensive project types
such as PSH.

**Use Cases** We have used exit data for numerous CPL projects. Exit
dates allow us to determine the length of service enrollment, which
we\'ve used in our rapid re-housing and homelessness prevention work. We
discovered the data quality issues with the destination variable when
performing an analysis on interim housing.

### Export

**Description** This file provides information on the data pull (or
export) and thus has one observation. It includes an Export ID, name of
source, source contact information, software name, etc. We do not use
this file, but it is helpful in identifying the date of the export.

### Funder

**Description** These data provide a list of all the federal partner
funding sources of the programs in the HMIS and include funding start
and end dates. Each project that is part of a CoC must have at least one
funder.

### Geography

**Description** Each observation in the data is an HMIS project.
Elements include CoC code, geocode, and address. In pulls from the old
software system (AdSystech), this file is called Site.csv.

### HealthAndDV

### IncomeBenefits

### Inventory

### Organization

### Project

### ProjectCoC

## CPL Work Product {#cpl_work_product}

**[Predicting Exits from Permanent Supportive Housing - Adam
Scherling](https://escholarship.org/uc/item/0p50w569)**: Permanent
supportive housing programs, which provide high-need homeless
individuals with long-term housing and supportive services, are thought
to be crucial for addressing chronic homelessness. However, many
individuals who enroll into permanent supportive housing programs exit
within a short period of time, often to unsuitable destinations. This
paper utilizes a random survival forest model to predict the outcomes of
permanent supportive housing programs in Los Angeles County.

The model demonstrates moderate success out-of-sample, with a
concordance of 75% between expected risk of exit and observed length of
stay. The identification of negative outcomes is similarly successful,
with an AUC of 0.7. Organization-level covariates are found to be the
most important predictors. Other important factors include age, previous
homeless experience, and variables related to client income and
benefits. On the other hand, most demographic variables, client health,
and client disabilities are found to play relatively small roles in
predicting outcomes.

## Data Requests {#data_requests}

**Requested 10/2/2018, received 11/8/2018**

In August 2018 we received revised VI-SPDAT files that included client
demographic information. Previously we had to link the VISPDAT
assessments to the client file in order to pull the demographics asked
on the first page of the VISPDAT. This left us unable to see those
demographics for the clients assessed but not enrolled in programs.
These revised files include assessments from 5/1/17 for the
de-identified data, and 1/1/18 for identified data.

Is it possible to received full historical pulls of all VISPDATS +
client demographic information? This would include assessments prior to
5/1/17 for de-identified data and prior to 1/1/18 for the identified
data.

**Requested 10/19/2018, updated 11/8/2018, received 12/13/18**

De-identified Prevention Targeting Tool data for single adults, 2010 (or
oldest available)-current.

-   We\'re working on getting you the prevention targeting tool for
    individuals. This is taking some additional time, as we have not
    fully exported this data before.

## General Data Quality Issues {#general_data_quality_issues}

### Coverage

The HMIS does not cover all homelessness programs throughout the county.
HMIS coverage varies by continuum of care. Domestic violence programs do
not participate in the HMIS to better protect vulnerable clients\'
information. Programs that do not rely on LAHSA funding are not required
to participate in the HMIS, and this also decreases coverage.

In the LA CoC, coverage for certain programs types is especially low,
most notably emergency shelter (ES) and transitional housing (TH).

[<File:LA> coc hmis coverage
.png](/File:LA_coc_hmis_coverage_.png "wikilink")[^4]

## LAHSA Data Conventions and Standards {#lahsa_data_conventions_and_standards}

### Demographics

**Race/Ethnicity**

Hispanic: A person is defined to be Hispanic if ethnicity =1. This is
true irrespective of race. For instance, an individual who is white
(white = 1) and Hispanic (ethnicity = 1), is considered to be Hispanic.

Race: If the Client indicates Hispanic/Latino ethnicity, LAHSA
recommends marking American Indian/Alaska Native as the default race.
However, in reporting statistics on race/ethnicity, CPL has not assigned
individuals who identify as Hispanic (ethnicity = 1) to the American
Indian/Alaska Native racial category. Instead, individuals who indicate
they are Hispanic are categorized as \"Latinx.\"

**Age and Household Type**

LAHSA has three target population categories for programming and funding
purposes - single adults, transition age youth, and families. These
categories are defined by the number and age of individuals in each
household.

Age: When looking at the age of each client, their DOB is subtracted
from the project entry date (in the Enrollment.csv file) and divided by
365 to determine the client's age at project entry.

Single Adults: Anyone who does not have a minor age dependent and is at
least 25 years of age or older.

Transition Age Youth (TAY): Unaccompanied individuals who are 18-24
years old at the time of project entry. Anyone under 18 is considered a
minor. If a TAY head of household is accompanied by a minor child, the
household should be categorized as a family.

Family: A household consisting of at least one minor child AND one TAY
(aged 18-25) OR Adult (aged 25+).

To determine an individual\'s household type:

`         1. Calculate the head of household's age at enrollment. `\
`         2. Count the number of individuals per household per enrollment to get household size.`\
`         3. Use household type definitions (above) to create rules for assigning household type (e.g. if household size=1, and HOH age>=25, the household can be classified as "single adult"). `

There will be unaccompanied minors and other household structures that
do not fit into these categories. We label them as \"Other\" so that
they don\'t get

**Gender**

In recent years, the gender variable\'s values have been expanded to
include Female, Male, Trans Female, Trans Male, and Gender
Non-Conforming. If a client already has a record in HMIS, the service
provider is instructed to verify the gender information and make
corrections as necessary. Therefore, the most recent intake information
should be used in CPL analysis should there be any discrepancies.

## HMIS data loaded into SQL Server {#hmis_data_loaded_into_sql_server}

Since the summer of 2019, CPL has been loading LAHSA\'s deliveries of
HMIS data into our internal Microsoft SQL Server database. The purposes
of this project are:

-   1\. Standardization of the data loading and preprocessing steps, so
    that different projects using the HMIS data are using a consistent
    version of the underlying data;
-   2\. More fine-grained permissions over access to columns containing
    PII, so that LAHSA can deliver us a single dataset containing PII
    (rather than two separate, and often inconsistent, datasets
    containing PII and with PII removed);
-   3\. Integration with other data already loaded into SQL (such as the
    ELP), and the general benefits for analysis that come with a SQL
    database.

Going forward, HMIS analysis at CPL can be performed either directly on
the HMIS tables in SQL Server, or using preprocessed CSV extracts from
SQL Server.

### Data Load and Preprocessing Overview {#data_load_and_preprocessing_overview}

LAHSA uses export tools built into their HMIS software (previously
Adsystech, now Clarity) in order to provide export HMIS data according
to the HUD definition. The data and preprocessing steps are designed to
deal with the issues introduced by that export process, such as:

-   1\. Adsystech and Clarity are separate pieces of software, with
    separate exports required from each, and with some (but not all)
    data present in both systems, with conflicting identifiers used in
    each.
-   2\. The export tools appear to have size limitations, which mean
    that the data is often exported in several \'batches\' that need to
    be stitched together.
-   3\. The columns in each of the separate batches may not be
    consistent.
-   4\. There may be duplicate records across batches or sometimes
    within the same file.
-   5\. There may be other delivery-specific problems or corruption that
    need to be handled on an ad-hoc basis.

The loading and preprocessing steps into SQL are intended to be as
minimal as possible in order to deal with the above issues.

### Data Load and Preprocessing Steps {#data_load_and_preprocessing_steps}

-   1\. When running the scripts, the user specifies a set of file
    delivery locations on the server, in order of precedence. This
    allows us to specify that, in the case of duplicate records, the
    record from the more recent delivery should take precendence.
-   2\. If there are multiple deliveries of a given file (e.g. the
    Enrollment file), the columns are unified across the separate files
    so that the final tables contain all columns encountered in all file
    deliveries.
-   3\. Appropriate SQL datatypes are inferred from the data (e.g. INT,
    VARCHAR, DATE, etc).
-   4\. The Adsystech-to-Clarity crosswalk files are applied to the
    EnrollmentID, PersonalID, ProjectID, and OrganizationID identifiers.
    This means that any occurrences of the Adsystech identifiers are
    replaced with Clarity identifiers.
-   5\. Duplicate records are then handled as follows. (Note that this
    step is currently performed only for the Affiliation, Client,
    CurrentLivingSituation, EmploymentEducation, Enrollment,
    EnrollmentCoC, ProjectCoC, Exit, Geography, HealthAndDV,
    IncomeBenefits, Organization, and Project files). Whether or not a
    record is a duplicate is determined by the \'primary key\' of the
    file (e.g. the PersonalID in the case of the Client file).
-   5.1. If a record appears in both an older and a newer version of the
    file (as determined by the precendences specified in step 1), the
    record from the newer version of the file is used.
-   5.2. If a record appears multiple times in a single version of the
    file, the duplicates are replaced with a single merged record which
    includes all non-missing values where available.
-   5.3. If there are any entries in the source data that are exact
    duplicates across all columns, only one record is inserted into the
    final table.

### Current versions of Gold Standard HMIS Data {#current_versions_of_gold_standard_hmis_data}

A Gold Standard HMIS dataset is a version of the HMIS data that has been
fully cleaned, preprocessed, and loaded into SQL Server. They can be
considered \'official CPL releases\' of the HMIS data.

#### Gold Standard HMIS 20190812 {#gold_standard_hmis_20190812}

As of the time of writing (2/4/2020), `<b>`{=html}Gold Standard HMIS
20190812`</b>`{=html} is the version loaded into the
`<b>`{=html}hmis`</b>`{=html} database on SQL Server on the ELP VM. It
is also the version of the HMIS that has been loaded in CSV format on
the Randall Kuhn VM.

It contains data loaded from CSV source files from the following LAHSA
data deliveries, stored in the following locations on the ELP VM:

-   1\. E:\\OriginalData\\LA HMIS\\ided\\HUD extracts\\20180730\\
-   2\. E:\\OriginalData\\LA HMIS\\ided\\HUD extracts\\20181108\\
-   3\. E:\\OriginalData\\LA HMIS\\ided\\HUD extracts\\20190219\\
-   4\. E:\\OriginalData\\LA HMIS\\ided\\hmis_20100101_to_20170401\\
-   5\. E:\\OriginalData\\LA HMIS\\ided\\hmis_20170501_to_20171231\\
-   6\. E:\\OriginalData\\LA HMIS\\ided\\hmis_refresh_20190812\\

As a matter of historical record, the data in the folder
`<b>`{=html}hmis_refresh_20190812`</b>`{=html} was intended by LAHSA to
be a full refreshed delivery of the HMIS from the beginning of time, up
until the extraction date (8/12/2019). Upon initial receipt and
investigation of the data, CPL discovered that there were significantly
fewer clients and enrollments in this delivery of the data as compared
to previously received deliveries. When we asked Steven Rocha from LAHSA
we received the following explanation:

`<i>`{=html} Email dated Tuesday 9/3/2019

Ticket 47055:
<https://hmissupport.freshdesk.com/public/tickets/ca29e3f7b40b84ad0e59a445575309fb48573e6151f3397d54e57c64325218ec>

Hi Nathan,

Here are some updates: (1) Any updates on the missing enrollments from
the refreshed HMIS data as per our email of 8/14? (see below)
`<b>`{=html} It seems like the missing information is most likely due to
enrollments that have not been migrated from our old HMIS. We did not
migrate coordinated entry program type projects because we transferred
just the assessments portion of it. We also did not migrate a few old
programs that had data quality issues and stopped participating in HMIS.
Regarding the examples you provided, I checked those and those used to
be in Clarity, but have since been deleted by users since the data was
last exported. `</b>`{=html}

If you count the missing enrollments by program type and see that the
majority are not coordinated entry projects, let me know and I can
investigate further. Also, I\'m not sure if I updated you since our last
call, but our IT updated Nathan\'s fileshare account to allow for write
access, so you can upload files now too.

\(2\) When looking at the refreshed PTT scores, I noticed that there are
PersonalIDs which have PTT scores but which cannot be found in the
Client file. It looks like these are people who were assessed but never
enrolled in any project. There are 379 in the Families PTT file and 156
in the Individuals PTT file. Do Client records for these PTT assessments
exist, and if so would it be possible to get hold of them? Some examples
of missing PersonalIDs in the Families PTT are 1106, 285026, and 416813.
In the Individuals PTT, examples of missing PersonalIDs are 350257,
429731, and 413384. This is the same issue we had with the VI-SPDAT
assessments. Last time we worked around this by adding the demographic
information for each client to the assessment file. Would you like the
same here?

\(3\) We're using the services file to better characterize prevention
enrollments. A large proportion of prevention enrollments do not have
related records in the services file. What would you make of this
missingness? Is it due to the fact that enrollments without services
records received no services or are there other reasons for missingness?
I\'ll need some additional time to research this.

\(4\) We're looking at the mix of services tied to prevention
enrollments over time to better understand what's actually occurring
under the prevention heading. We see that "legal services" (looking at
ServiceName and ServiceItem fields for this analysis) are very common
among prevention enrollments until 2012, but then "legal services" drops
to almost 0 for years after. Could this be because legal services are
being fulfilled by provider outside of the HMIS system after 2012? Was
there any HMIS change you're aware of that would affect how people
record this? Any other insights? This is because of HUD\'s Homelessness
Prevention and Rapid Re-housing (HPRP) program that operated from 2009
to 2012. Legal services was one of the services available, and we also
had a legal organization using these funds, so it makes sense that there
were more of those types of services then. In our current programs, that
is not as common of a service as you saw, as much of that is tracked
outside of HMIS in separate non-implemented programs.

Thanks, Steven Rocha `</i>`{=html}

In order to have an HMIS database that is as complete as possible and
consistent with previously-used versions, we decided to merge the full
refresh supplied by LAHSA with records from previous deliveries. In the
final tables, data delivered from source (6) above takes precedence. Any
records which are not present in this data are drawn from sources (1)
through (5).

In the final tables, the column `<b>`{=html}HMISRefreshID`</b>`{=html}
is set to 1 if the record was backfilled from previously acquired data,
and is set to 0 otherwise.

## Notes

```{=html}
<references />
```

[^1]: HMIS: Homeless Management Information System - HUD Exchange.
    (n.d.). Retrieved August 9, 2018, from
    <https://www.hudexchange.info/programs/hmis/>

[^2]: HMIS Requirements - HUD Exchange. (n.d.). Retrieved August 9,
    2018, from
    <https://www.hudexchange.info/programs/hmis/hmis-requirements/>

[^3]: Enacted into law in May of 2009 as part of S.896 The Homeless
    Emergency Assistance and Rapid Transition to Housing (HEARTH) Act,
    the McKinney-Vento Homeless Assistance Act established standards
    related to HMIS. In 2010, we begin to see a difference in the data
    quality and usability. For instance, in 2009, the data contains
    10,702 unique personal identification numbers. In 2010, that number
    jumps to 59,045.

[^4]: FY 2018 CoC Application (n.d.). Retrieved September 16, 2019, from
    <https://www.lahsa.org/documents?id=2512-fy-2018-coc-application-narratives-only>