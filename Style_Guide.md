# Formatting Guidelines for Policy Briefs {#formatting_guidelines_for_policy_briefs}

All text should use Gil Sans Nova as the font.

**Black text unless otherwise noted**

**[Get Gill Sans Nova
here!](https://www.microsoft.com/en-us/p/gill-sans-nova/9pk93bg0z1jj?activetab=pivot:overviewtab)**

#### Title Page {#title_page}

Use orange text (246, 139, 31) for title and section headings within a
policy brief.

Use blue text (38, 145, 208) for the summary text and to introduce key
takeaways.

Use black text for the body of text within a policy brief.

Use blue text (38, 145, 208) to reference Figures or Tables within the
brief.

#### Footer

Page number in black in left hand corner.

\"capolicylab.org\" in blue text (38, 145, 208) two tabs in from page
number.

Right justify and capitalize the title in blue text (38, 145, 208).

# Formatting Guidelines for Exhibits {#formatting_guidelines_for_exhibits}

The following is meant as a guide, and was written with input from
Faculty Directors and Research Directors at both sites. While there will
be instances where a particular graph or table will need to stray from
some aspect of the guidance, **using these principles as a starting
point for tables and figures at CPL is strongly recommended.** Using the
templates provided in the [Commons](/Commons "wikilink") under
\\Templates\\ and linked below is similarly recommended.

A great primer for creating data visualizations at CPL is Evan White\'s
[Data Visualization
Seminar](https://drive.google.com/file/d/1sQ8j38QI9u9SbXN_KTk698tQfgB3a_LC/view?usp=sharing)
from CPL\'s 2020 virtual staff retreat. The principles he discusses are
reflected in this style guide and in the STATA/R guides for figures and
tables on our VMs (also available in links below; not guaranteed to be
as current as source documents on VM).

-   [Design Guide for Figures and Tables in
    R](https://drive.google.com/drive/folders/15z0-UB315KnW0NPsvq5lwbeE3cAgfIcX?usp=sharing)
    (download html and open in new window)

## Tables

-   Even in draft form tables should be easy to read and easy to
    understand. Always include a descriptive title, column headers, and
    table notes.
-   Use descriptive variable labels instead of variable names as column
    headers. \"Graduation Year\" instead of \"gradyr\"
-   Top row (column header) should be bold.
-   Use consistent precision in decimals; generally 2 for non-technical
    audience, 3 for technical.
-   Format percentages from 0-100, not 0-1. Include a % sign.
-   Center columns of numbers. Left justify the left-most column.
-   Horizontal lines should be used for the header (above and below the
    top row) and below the final row. Thats it.
-   In general, vertical lines should not be used.
-   Titles should be added in the destination document (Word doc,
    Powerpoint presentation) rather than in the software generating the
    exhibit.

[<File:Sample_table.JPG>](/File:Sample_table.JPG "wikilink")

## Graphs

### General Guidance {#general_guidance}

-   Even in draft form figures need to be easy to read, and easy to
    understand. When drafting always include a descriptive title, axis
    labels, and figure notes.
    -   Finalized figures should have titles added in the destination
        document (Word doc, Powerpoint presentation) rather than in the
        software generating the exhibit.

### Axis Formatting {#axis_formatting}

-   Avoid using abbreviations in your axis labels or in your legend.
    Shorten and simplify where possible without losing key information.
-   Make sure font size on x and y-axis titles or labels is large enough
    that it can be read without squinting.
-   When expressing percentages format your number labels or axes with %
    signs not as decimals (10% not 0.10).
-   Axis titles should be bold, axis labels should not.

### Labels and Legend Formatting {#labels_and_legend_formatting}

-   Legends should almost always be included when two or more groups or
    variables are displayed.
-   Use descriptive variable labels instead of variable names.
    \"Graduation Year\" instead of \"gradyr.\"
-   In draft form place legends to the right of the figure
-   In publication form, place legends within the graph if space allows,
    otherwise legends should remain to the right of the figure

**Race-equity considerations**
([source](https://urban-institute.medium.com/applying-racial-equity-awareness-in-data-visualization-bd359bf7a7ff)):

Be purposeful in the ordering of your data labels. Which group we choose
to show as the first row in a table or the first bar in a graph can
affect how readers perceive the relationship or hierarchy between
groups; always starting with "White" or "Men" can make these groups
appear as the default against which other groups should be compared,
suggesting they're the most important populations.

When deciding how to order your data labels, ask yourself the following
questions:

-   Does your study focus on a particular community? If it does, that
    group should be presented first.
-   Is there a particular argument or story you are trying to tell? If
    so, the order or presentation of results should reflect that
    argument.
-   Is there a quantitative relationship that can guide how the groups
    are ordered? Can they be sorted alphabetically or by population
    size, sample size (weighted or unweighted), or magnitude or effect
    of the results?

### Grouping, Colors, and Line Styles {#grouping_colors_and_line_styles}

-   Colors and line styles should be easily distinguished from each
    other in color and black and white printing.
-   Use no more than 4 or 5 groups per figure.
-   Don\'t let Microsoft, R, Stata, SAS, Tableau, etc choose colors for
    you.
-   Use the color palettes below to select colors for figures based on
    the design of CPL\'s Policy Briefs, or the UCLA and UCB color
    scheme.
-   At CPL-UCLA use Darker Blue for the first element, Darkest Gold for
    the second, Lighter Blue for the third, Darkest Blue for the fourth,
    and Lightest Blue for the fifth.
-   At CPL-Berkeley use Founders Rock for the first element, California
    Gold for the second, Lawrence for the third, Berkeley Blue for the
    fourth, and Bay Fog for the fifth.
-   [ColorBrewer2](http://colorbrewer2.org) can also be a helpful
    resource for picking color schemes when the University or Policy
    Brief palettes aren\'t what you need for a particular exhibit.
-   In a pinch, there\'s always [Wes Anderson
    Palettes](https://wesandersonpalettes.tumblr.com/).

### Pep talk for Stata Users {#pep_talk_for_stata_users}

It is possible to make nice looking Stata graphs that compare well to
what ggplot produces in R. A big first step: set scheme to s1mono. More
on schemes in Stata
[here.](https://www.stata.com/manuals13/g-4schemesintro.pdf) Take the
time to learn the options for things like twoway and scatter. [A primer
here.](https://www.stata.com/manuals13/g-3twoway_options.pdf)

## Color Palette for Figures {#color_palette_for_figures}

  Color                 Name              Hex      RGB             CMYK
  --------------------- ----------------- -------- --------------- -----------------
  *CPL Policy Briefs*
                        Blue              2493D1   38, 145, 208    83, 30, 0, 18
                        Orange            F68B1F   246, 139, 31    0, 43, 87, 4
                        Light Blue        48C5DB   72, 197, 219    67, 10, 0, 14
                        Green             9AC43F   153, 198, 66    23, 0, 67, 22
                        Blue Grey         809BB2   128, 155, 178   28, 13, 0, 30
                        Red               ED3B13   237, 59, 19     0, 75, 92, 7
                        Darker Blue       2D3172   45, 49, 114     61, 57, 0, 55
                        Dark Grey         6D6E71   109, 110, 113   4, 3, 0, 56
  *CPL-UCLA*
                        Darker Blue       005587   0, 85, 135      100, 45, 0, 45
                        Darkest Gold      FFB81C   255, 184, 28    0, 31, 98, 0
                        Lighter Blue      8BB8E8   139, 184, 232   45, 14, 9, 9
                        Darkest Blue      003B5C   0, 59, 92       100, 48, 12, 58
                        Lightest Blue     C3D7EE   195, 215, 238   20, 6, 0, 0
                        Dark Grey         6D6E71   109, 110, 113   4, 3, 0, 56
  *CPL-Berkeley*
                        Founders Rock     3B7EA1   45, 99, 127     71, 30, 13, 45
                        California Gold   FDB515   253, 181, 21    0, 23, 91, 0
                        Lawrence          00B0DA   0, 176, 218     79, 0, 6, 5
                        Berkeley Blue     003262   0, 50, 98       100, 71, 10, 47
                        Bay Fog           DDD5C7   194, 185, 167   7, 10, 22, 20
                        Web Grey          888888   136, 136, 136   0, 0, 0, 47

  : Frequently used color palette and codes

## Additional Resources {#additional_resources}

[An Economist's Guide to Visualizing
Data](https://pubs.aeaweb.org/doi/pdfplus/10.1257/jep.28.1.209): a
helpful resource in thinking about how to translate your research into
impactful figures.

[Applying Racial Equity Awareness in Data
Visualization](https://urban-institute.medium.com/applying-racial-equity-awareness-in-data-visualization-bd359bf7a7ff):
Urban Institute\'s guide to integrating race-equity perspectives into
data viz.

[Organizing Data for Economic
Research](https://www.brendanmichaelprice.com/workflow/) Three part
guide for effective workflows for managing, analyzing, and visualizing
data in Stata. Written by Brendan Price, Senior Economist at the Federal
Reserve Board of Governors.