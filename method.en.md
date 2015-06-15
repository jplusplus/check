This document outlines the fact checking methods used by Journalism++ Stockholm. Inspiration has been drawn from  Jennifer LaFleur's [A Guide to Bulletproofing Your Data](https://github.com/propublica/guides/blob/master/data-bulletproofing.md) and Chris Groskopf's [Sixteen solutions for data-driven projects](https://docs.google.com/presentation/d/18KE-VO9T6V1I_aGyekdDtFhYP4K0Saph7aBuBS3N8tc/edit#slide=id.ga85f0df1a_049). Capitalized words like MUST and SHOULD shall be interpreted according to [RFC2119](https://www.ietf.org/rfc/rfc2119.txt)

## <span id="dataregister">Central data repository</span>

_what?_<br/>
At the start of each project, all original data SHOULD be collected in one place, together with a source note.

_why?_<br>
A central data repository reduces the risk of data being redefined along the way.

_how?_
 * Put (and write-protect) all data in one folder
 * Add a text file to that folder, with a list of data files and sources
 * Note if possible the number of rows (or relations, or similar, depending on data type) for each dataset
 * Add all new data sets that are introduced in the project here


## Dissertation

_what?_<br/>
One person in the office SHOULD be kept out the research process. That person will be our “opponent”. The opponent will call for an internal dissertation towards the end of the project.

_why?_<br>
With a dissertation we will find weak links before publishing

_how?_<br>
The opponent shall:
 * Question all definitions
 * Check against [the data repository](#central-data-repository) that all data seem to be used in the right place and ways
 * Question calculations
 * Assess the conclusions
 * Make _several_ spot-checks
 * Proofread units, scales, number formats, etc.


## Initial data sanity check

_what?_<br/>
At the start of the project, and whenever new data is introduced, time MUST be allocated for doing a sanity check.

_why?_<br>
An initial sanity check lets us detect exporting/importing errors, and error committed by our sources.

_how?_
 * Make pivot tables to check for alternate spellings of the same name, etc
 * Check completeness when relevant (are all [countries/weekdays/presidents] in there?)
 * Check the zeros. Should they really be 0, or did empty cell get transformed to 0 on the way here?
 * ...and vice versa. Check the empty fields.
 * Assess the reasonableness of the values
 * Visualize, to spot weird patterns, outlying points, etc


## Versioning

_what?_<br/>
To track errors, we need to be able go back to all earlier versions and editors of all files. One of the methods mentioned below SHOULD be used.

_why?_<br>
Versioning makes it easier to detect errors.<br>
Versioning makes it easier to spot “secondary errors” introduced by these errors.<br>

_how?_
 * Try to make all data processing in code
 * If you need to process data in a spreadsheet application or similar, save each new version under a new name. Put each set of versioned files in one folder, named after the original data file, and use the following naming pattern: `YYMMDDxx - changes`. E.g.: `map-of-sweden/15060401 - added postal code areas.shp`.
 * Or even better: Use Git for versioning.
 * When collaborating with other people, synchronize a Dropbox folder or a Google Docs document with Github.


## Standard formats for file based data

_what?_<br/>
File based data SHOULD use one of our standard formats for data.

_why?_<br>
Coherent file formats reduces the risk of conversion errors and truncations.

_how?_
 * CSV files for tabular data (comma as delimiter, quotation marks as string container)
 * XLSX files for tables with formulas
 * JSON for hierarchical data
 * Shape files for geodata
 * Always UTF-8, everywhere. Always. Everywhere.


## Line-by-line reading

_what?_<br/>
Articles SHOULD be line-by-line fact checked.

_how?_<br>
 * The non-involved opponent will be in charge of line-by-line reading, when relevant
 * Remember to check visual statements. A graph or a choropleth map is a statement in it self. Fact check that statement!


## Openness

_what?_<br/>
An open Github repo is not by itself a guarantee that someone will look at your code or data. For each project, we MAY try to offer something to value to the community. In return, we might get more eyes on our data.

_why?_<br>
Openness helps us detect errors and weaknesses earlier.

_how?_<br>
 * Use an open Github repo whenever possible
 * Always describe your project in a README file
 * Identify something in the project that would be of value to others, and share it. Use Google Sheets to share when possible (to make it accessible to non tech savvy users)
 * Github repos should contain original data when possible


## Inspiration

 * [A Guide to Bulletproofing Your Data, Jennifer LaFleur, ProPublica](https://github.com/propublica/guides/blob/master/data-bulletproofing.md)
 * [Sixteen solutions for data-driven projects](https://docs.google.com/presentation/d/18KE-VO9T6V1I_aGyekdDtFhYP4K0Saph7aBuBS3N8tc/edit#slide=id.ga85f0df1a_049)
