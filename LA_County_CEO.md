# Los Angeles County CEO {#los_angeles_county_ceo}

## Background

The `<b>`{=html}LA County Chief Executive Office (CEO)`</b>`{=html}
assists the LA County Board of Supervisors with administering the
County. CPL has research partnerships with two subdivisions within the
CEO:

-   The `<b>`{=html}Chief Information Office (CIO)`</b>`{=html} provides
    vision and strategic direction for the effective use of information
    technology (IT) to achieve business objectives and improve the
    delivery of services throughout the County of Los Angeles. CIO
    management staff support County departments by providing business
    and technical analysis of IT projects and initiatives,
    request-for-proposals and contracts.
-   The `<b>`{=html}Homeless Initiative (HI)`</b>`{=html} was created by
    the Board of Supervisors in 2015. It is responsible for coordinating
    and overseeing the County\'s efforts to use Measure H funding to
    address the homelessness crisis in the County.

## CPL Research Partnership {#cpl_research_partnership}

The purpose of our agreement with the CIO and HI is to conduct research
into homelessness in Los Angeles County, and to provide practical
assistance to the County in implementing concrete strategies to address
the homelessness crisis. This includes the use of predictive analytics
on LA County administrative data to predict and prevent homelessness,
but also covers descriptive analysis and modeling to understand
homelessness more generally.

CPL\'s partnership with the CIO is focused on issues of data
acquisition, data infrastructure, and research design, whereas the
partnership with the HI is focused on strategic direction for CPL\'s
homelessness research and its application to on-the-ground County
initiatives to address homelessness.

## Data Holdings {#data_holdings}

The CIO has legal agreements with most LA County agencies to collect
service utilization data at the individual level. This data falls under
the legal and technical umbrella of the `<b>`{=html}Enterprise Linkages
Project`</b>`{=html}. Until 2018, this has consisted of regular but
ad-hoc flat-file deliveries from County agencies to the CIO. The data
are provided by the following agencies:

-   `<b>`{=html}Department of Health Services (DHS)`</b>`{=html}
-   `<b>`{=html}Department of Mental Health (DMH)`</b>`{=html}
-   `<b>`{=html}Department of Public Health (DPH)`</b>`{=html}
    (restricted to the Substance Abuse Prevention and Control program)
-   `<b>`{=html}Department of Public and Social Services
    (DPSS)`</b>`{=html}
-   `<b>`{=html}LA County Sheriff`</b>`{=html}
-   `<b>`{=html}Probation Department`</b>`{=html}
-   `<b>`{=html}Department of Child and Family Services
    (DCFS)`</b>`{=html}

The CIO\'s historical ELP data holdings from approximately 2006 through
2018 exist as flat files that are linked and merged by the CIO\'s
analysts on an ad-hoc basis in response to requests for data analysis
from the County. The CIO does not possess this data in the form of an
Integrated Data System (IDS) or data warehouse. In order to facilitate
large-scale, timely, and flexible data analysis, CPL has preprocessed
and integrated this historical data into the `<b>`{=html}CPL Historical
ELP`</b>`{=html}, an IDS that resides in our SQL Server environment. The
CPL Historical ELP represents several years\' work in cleaning,
preprocessing, and integrating the County\'s historical ELP data. In
particular, it includes a unique system-wide person identifier generated
through an entity-resolution algorithm.

Note that the historical ELP data is supplied to CPL with all Personal
Identifying Information (PII) encrypted through the SAS Dataflux
algorithm. CPL then performs entity resolution on the encrypted PII to
generate unique system-wide person identifiers.

The CPL Historical ELP is fully integrated with CPL\'s copy of the LAHSA
HMIS.

### Summary of CPL Historical ELP as of 4/16/2020 {#summary_of_cpl_historical_elp_as_of_4162020}

  Agency                            Approximate Coverage Dates                                                                                   \# Unique Persons                    \# Service Records\*                   Key Data Elements\*\*
  --------------------------------- ------------------------------------------------------------------------------------------------------------ ------------------------------------ -------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------
  DHS                               1/2006 - 5/2018                                                                                              1,474,377                            22,056,309                             Dates of service; service types (emergency, inpatient, outpatient); procedure and diagnosis codes; facility name
  DMH                               1/2006 - 8/2018                                                                                              609,091                              67,182,654                             Dates of service; service types (inpatient, outpatient, crisis stabilization); diagnosis codes (cuts off in 2015); service cost; facility name
  DPH/SAPC program                  1/2006 - 12/2017                                                                                             180,130                              781,533                                Dates of service; service type; intake questionnaire with \~90 questions including areas of dependency and completion status; facility name
  DPSS/General Relief program       2/2010 - 8/2018                                                                                              485,503                              15,104,013                             Dates of service; homeless flag
  DPSS/CalFresh program             1/2009 - 9/2019                                                                                              3,402,194                            11,749,429                             Dates of service; homeless flag; case numbers linking family members
  DPSS/CalWORKs program             1/2009 - 9/2019                                                                                              1,513,843                            4,129,260                              Dates of service; homeless flag; case numbers linking family members
  Probation                         1/2005 - 8/2018 (data missing from 4/2014 through 7/2015 due to IT system failure at Probation department)   144,870                              3,297,494                              Probation months; facility name
  Sheriff                           1/2012 - 7/2018                                                                                              520,261                              11,603,983                             Booking and jail dates; arrest charge codes (from 2015 onwards)
  DCFS                              1/2010 - 9/2018                                                                                              95,964 children                      410,654                                Case and placement start and end dates; facility type; father and mother; homeless indicator
  HMIS\*\*\*                        1/2010 - 9/2019                                                                                              354,515                              761,804                                See HUD HMIS Codebook and CPL HMIS documentation
  `<b>`{=html}Totals`</b>`{=html}   `<b>`{=html}N/A`</b>`{=html}                                                                                 `<b>`{=html}6,120,028`</b>`{=html}   `<b>`{=html}137,077,133`</b>`{=html}   `<b>`{=html}N/A`</b>`{=html}

`*Since this depends upon the granularity of data collection at each agency, it may not be a meaningful metric nor one that can be compared across agencies or datasets.`\
`**Full description of data elements is restricted by the Data Usage Agreement and cannot be included here. A subset of key data elements is provided.`\
`***CPL uses our own copy of the HMIS data sourced directly from LAHSA, rather than a copy sourced from the CIO.`

### Infohub

Since 2018, the CIO has been working on utilizing the legal
infrastructure and data holdings of the ELP to build a true IDS that is
refreshed on a regular basis, and which can be utilized for real-world
business intelligence and research applications. This IDS is called the
`<b>`{=html}Infohub`</b>`{=html}. As of the time of writing (4/17/2020),
the Infohub is still being developed at the CIO, and is undergoing
frequent architectural changes. As far as CPL is aware, the only use
cases for which the Infohub is being utilized in production are (i) an
application called CHIP allowing inter-agency lookup of homeless
individuals\' service utilization data under the legal framework of
AB210; and (ii) ad-hoc analyses by CIO analysts at the request of County
stakeholders.

Unlike the historical ELP, entity-resolution and generation of unique
system-wide person identifiers is performed at the CIO. The resulting
identifier is called an `<b>`{=html}Enterprise ID (EID)`</b>`{=html}.
The CIO has informed CPL that the EID is not guaranteed to be stable
across data refreshes (i.e. it is not guaranteed that a particular EID
will refer to the same individual from one refresh to another).

Since the Infohub will be refreshed on a weekly or monthly basis, CPL is
regarding it as an essential prerequisite to deploying any predictive
models in the field. (Such models cannot be deployed using the CPL
Historical ELP since it is not refreshed on a regular basis).

The agencies supplying data to the Infohub are the same as for the
historical ELP above, with the following differences (as of 4/16/2020):

-   DHS and DMH are only supplying data from 2015 onwards.
-   DPH is not currently supplying any data, although CPL has been
    informed that the DPH/SAPC data will be coming online in the first
    half of 2020.
-   As of 4/17/2020, DPSS is only supplying data for a subset of their
    client base who are currently flagged as homeless according to
    DPSS\'s homeless flags. DPSS is currently collaborating with the CIO
    on a significant new data delivery into the Infohub, which will
    represent a majority of the data elements available in DPSS\'s
    internal systems. The CIO anticipates that this data will be loaded
    in May 2020.
-   As of 1/15/2021, DPSS is supplying their entire database to the CIO,
    including employment and education information, as well as the
    monetary amounts for benefits, which were missing in the ELP
    versions of the data.
-   The HMIS data loaded into the Infohub represents only
    `<b>`{=html}enrollments which are active from 2016
    onwards`</b>`{=html}.

## Data Linking {#data_linking}

As of 4/17/2020, CPL has obtained permission to link the County\'s data
to copies of the HMIS obtained directly from LAHSA.

As of 12/2020, CPL was also received datafluxed matchcodes for the
Infohub data. The idea to undertake matching between the Infohub, the
historical ELP, the HMIS as well as any ad hoc file deliveries such as
CHAMP (housing program within DHS) or CHEERD (housing program within
DMH).

## Documentation

Detailed documentations for the ELP and the Infohub data can be found on
the `<b>`{=html}ELP Server`</b>`{=html}. The documentation can be found
in various formats, including jupyter notebooks, which allows the
documentation to be fully up to date, as well as HTML and PDF formats.

The path to the documentations is `<b>`{=html}E:/Projects/elp/Homeless
Prediction/codebooks`</b>`{=html}.

## CPL contact person {#cpl_contact_person}

`<b>`{=html}All contact with the LA County CEO should proceed through
Janey Rountree and Brian Blackwell. Please contact Janey and Brian
before reaching out to CEO personnel directly`</b>`{=html}.

[Max Stevens](mailto:mstevens@ceo.lacounty.gov) Chief Research Officer