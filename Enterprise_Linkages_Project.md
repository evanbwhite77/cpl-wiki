## Overview

\"The Enterprise Linkages Project (ELP) was started in 2007 with the
goal of providing comprehensive information on the multi-system service
utilization patterns of persons participating in the General Relief
Program, a Los Angeles county-funded cash assistance program
administered by the Department of Public Social Services (DPSS) that
serves more than 100,000 indigent adults who are ineligible for federal
or state-level assistance program. The ELP includes information not only
about GR participants, but about participants across a spectrum of
publicly funded health, mental health, social and corrections
services.as well. Most importantly, the ELP also tracks the costs
associated with such service utilization, allowing for the formulation
of a complete picture of county resources expended upon participants in
the GR and other public programs.

Tracking of costs of public service use also creates the potential for
conducting cost--benefit analysis using ELP data. In addition to records
maintained by DPSS, the ELP integrates records from the Departments of
Community and Senior Services (CSS), Health Services (DHS), Mental
Health (DMH), Public Health (DPH), Children and Family Services (DCFS),
as well as the Probation and Sheriff Departments. Given its capacity to
track the service use of GR recipients and other persons across
different county agencies, analysis of ELP data can help foster
collaboration between county agencies, and identify redundancies in
services resulting in the potential for cost avoidance and cost
savings.\"

[Source](https://escholarship.org/uc/item/4jm557wp)

**California Policy Lab's ELP Holdings**

The ELP data held by the California Policy Lab contains data from six LA
County public services agencies: Department of Public Social Services
(DPSS), Department of Mental Health, Department of Health Services,
Department of Public Health, Los Angeles County Sheriff\'s Department,
and Los Angeles County Probation Department. The Department of Children
and Family Services is also part of the ELP, but their foster care data
has not been included in the data CPL received. Similarly, CPL did not
receive data from LA County's Community and Senior Services department.

The DPSS data in the ELP contains information about recipients of cash
assistance through LA County's General Relief (GR) program, which can be
linked to the other agencies to obtain a full picture of their public
service utilization. The data from the other five agencies contains
de-identified records for all users of their services, including users
who receive GR funds.

The level of service receipt detail varies by agency. For example, the
Department of Health Services data contains facility name, diagnosis,
procedure, and payee information for users of its clinics and hospitals.
The Sheriff's department data contains the facility code and start/end
dates for an individual's jail stay, but no other information such as
reason for detention, bail amount, hearing dates, etc.

The functional range of the DPSS/GR recipient data is from 2010 to 2018.
The usable data in the ELP from each of the other five agencies spans
from 2006 to 2018.

**Linking External Data Sources**

External data, such as the Los Angeles Homeless Services Authority's
(LAHSA) Homelessness Management Information System (HMIS) data, which is
**not** part of the ELP, can be linked if the identifying information is
passed through the same encryption process used to encrypt the ELP.
Permission to link external data to the ELP must be granted by the
County and, if governed by a datasharing agreement, the agency providing
the external data. Once approved, the County can encrypt the identifying
information needed for matching.

## Agencies

**Department of Public Social Services**

The Department of Public Social Services (DPSS) is the department
responsible for providing social service benefits in Los Angeles County.
DPSS provides services like Cash Assistance (CalWorks), Food and
Nutrition (CalFresh), Health Assistance, Job Assistance (GROW), General
Relief (GR), and other community services. DPSS serves 10 million
residents with an annual budget of \$3.9 Billion.

**Department of Health Services**

The Department of Health Services (DHS) provides access to high-quality,
patient-centered, cost-effective health care to Los Angeles County
residents. DHS provides healthcare to youth in the juvenile justice
system, to inmates in County jails and to children in foster care. DHS
also runs the Emergency Medical Services (EMS) Agency and the County's
911 emergency response system. DHS operates 19 health centers and four
hospitals. DHS annually cares for about 600,000 unique patients, and has
an annual operating budget of \$4.3 billion.

-   Population: Any individual that used an LA County Dept. of Health
    Services healthcare facility after 2006.
-   Service variables: facility visited, funding source, type of
    service, diagnosis, procedure, and service time period

**Department of Mental Health**

The Department of Mental Health (DMH) is the primary mental health
organization in the County. Their mission to enhance the wellbeing of
LA's most vulnerable populations (such as the homeless). Mental health
services provided include assessments, case management, crisis
intervention, medication support, peer support, psychotherapy and other
rehabilitative services. DMH serves more than 250,000 county residents
annually, operating in more than 85 sites with close to 1000
organizations and individual practitioners.

**Department of Public Health**

The Department of Public Health\'s (DPH) mission is to protect health,
prevent disease, and promote health and well-being for everyone in Los
Angeles County. DPH educates the population on good health practices,
advocates for access to medical health coverage, ensures safe drinking
water, promotes childhood vaccination, and provides sexual education. It
also provides clinical services through 14 public health centers (plus a
satellite site on Skid Row).

-   County considers DPH data after December 2017 to be unreliable.
    County management alerted by 10/29/18 at latest.

**Department of Probation**

The Probation Department is responsible for enhancing public safety,
ensuring victim's rights, and effecting positive probationer behavioral
change. The Probation Department provides several adult services like
Supervision after release, investigations, AB 109, and specialized for
moderate to high risk clients. In addition, they provide juvenile
services such as diversion and prevention, supervision and school based
programs. They operate on \$935 million budget, in 50 different
facilities, working with 82,000 adults and 1000 juveniles.

**Sheriff\'s Department**

The Los Angeles Sheriff\'s Department (LASD) provides general law
enforcement services to 40 contract cities, 90 unincorporated
communities, 216 facilities, hospitals, and clinics located throughout
the County, nine (9) community colleges, the Metropolitan Transit
Authority and 47 Superior Courts. LASD also provides services such as
laboratories and academy training to smaller law enforcement agencies
within the County. Additionally, LASD is responsible in securing
approximately 18,000 inmates daily in 7 custody facilities which
includes providing food and medical treatment.

The Sheriff's data will not contain bookings in Los Angeles city jails
except for those arrestees who remain in custody after arraignment.
These individuals are remanded to custody of the LA County Sheriff's
department.

## Data Linkage and Deduplication {#data_linkage_and_deduplication}

## ELP Project Folder Documentation {#elp_project_folder_documentation}

### E:\\Projects\\ELP\\Homeless Prediction\\code {#eprojectselphomeless_predictioncode}

**General Notes**

In general, the *code* folder contains:

-   **Within-agency entity resolution code**, stored in a folder for
    each agency (e.g. *dhs* for Department of Health Services). In most
    cases the entity resolution code consists of four SAS code files,
    *XXXX_01_preprocess*, *XXXX_02_dedup*, *XXXX_03_postprocess*, and
    *XXXX_04_report_check*. These are based on templates written by
    Halil Toros. Halil wrote the original SAS code for DHS entity
    resolution. Halil\'s DHS code was duplicated and modified by other
    team members to perform entity resolution for other agencies. Other
    team members also wrote code in other languages/platforms (R, Stata,
    Python) in order to perform intermediate data wrangling tasks for
    the specific agencies they were working on. Other miscellaneous
    files in these folders (e.g. Excel files, CSV files) are usually
    intermediate outputs, or working \'scratch\' files that will not be
    needed going forward.
-   **Inter-agency entity resolution code**, stored in the *matching*
    folder.

*TODO: for agency entity resolution code in addition to Halil\'s
templates, add documentation about how the additional code needs to be
run and in what order.*

For exceptions to the above, see documentation for specific subfolders
below.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\archive**

Old code that is no longer needed going forward.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\dcfs**

Contains code used to explore a sample file provided by the Department
of Children and Family Services. This code is unlikely to be used going
forward.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\dhs**

Department of Health Services entity resolution code, written by Halil
Toros. This was the first within-agency entity resolution code to be
written. The code was subsequently used as a template for other
agencies. The different subfolder structure (Data/Outputs/Programs)
compared with other folders is a legacy of the code being moved from
another server and has no special significance.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\dmh**

Department of Mental Health entity resolution code, written by Patrick
Chang (based on Halil\'s templates). The R code file (in addition to the
SAS files) does some initial data conversion prior to the SAS program
steps.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\dph**

Department of Public Health entity resolution code, written by Owen
McCarthy (based on Halil\'s templates). *TODO: rename _vtest files to
standard naming convention for final production code.*

**E:\\Projects\\ELP\\Homeless Prediction\\code\\dpss**

Department of Public Social Services entity resolution code, written by
Halil Toros.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\feature engineering**

Owen\'s work-in-progress code to generate model evaluation metrics.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\fei**

Code to encrypt source data containing medical record identifiers,
written by Fei Wu at LA County.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\gr**

Department of Public Social Services General Relief file entity
resolution code, written by Halil Toros.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\matching**

Inter-agency entity resolution and matching code. Halil wrote the
original template files, which were duplicated and modified by Nathan
for each of the other agencies.

*TODO: As of 10/10/2018 Nathan was unsure of whether a final, definitive
\'persons\' file had been generated by the matching code, and if so
where it is stored. Need to clarify this.*

*TODO: The Entity Resolution documentation states that the inter-agency
matching generated 1,394,647 unique person IDs. Nathan mentioned that
this is significantly lower than some previous estimate (around 4m).
Need to clarify this.*

**E:\\Projects\\ELP\\Homeless Prediction\\code\\probation**

Probation Department entity resolution code, written by Nathan and
Fernanda. Fernanda\'s code is written in Stata.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\SAS Templates**

This contains Halil\'s DHS entity resolution code that serves as the
template for the other agencies.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\sheriff**

Department of the Sheriff entity resolution code, written by Lingwei
Cheng. There is Python and Stata code to perform additional data
wrangling tasks as well as SAS code based on Halil\'s templates.

### E:\\Projects\\ELP\\Homeless Prediction\\codebooks {#eprojectselphomeless_predictioncodebooks}

Contains the ELP codebook (which as of 10/11/2018 is out of date and
needs to be revised). Nathan is unsure what the SAP-C Excel file is.

### E:\\Projects\\ELP\\Homeless Prediction\\data {#eprojectselphomeless_predictiondata}

The *XXXX_preprocessed* files contain entity resolution output for each
agency. Within each agency folder, the following files are the final
outputs to be used in subsequent steps (any other files are intermediate
outputs that can be ignored):

*XXXX_master*: maps PIDs to PAIDs and matchcodes.

*XXXX_paid_final*: crosswalk for PID-PAID mapping.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\fei**

Contains encrypted preprocessed files generated by Fei Wu (to encrypt
medical identifiers). These files can be dropped into the relevant
agency files.

**E:\\Projects\\ELP\\Homeless Prediction\\code\\matching**

Contains inter-agency matching output. *TODO: is there a definitive
\'persons\' file? The Entity Resolution documentation suggests that
there is, based on the count of unique ids.*

### E:\\Projects\\ELP\\Homeless Prediction\\outputs {#eprojectselphomeless_predictionoutputs}

Owen\'s miscellaneous work-in-progress modeling and analysis files.