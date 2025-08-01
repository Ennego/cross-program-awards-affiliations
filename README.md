**README**

### Scholars Programs in Art History: Comparative Data Since 1961

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.16612951.svg)](https://doi.org/10.5281/zenodo.16612951)

### Overview and acknowledgments

Four major residential scholars programs in the history of art have aggregated data on past scholars who received fellowship awards. The compiled dataset presents public information about past awards and fellowships from The Clark in Williamstown, Massachusetts, the Getty Research Institute (GRI) in Los Angeles, California, the Smithsonian American Art Museum (SAAM), and the Center for Advanced Study in the Visual Arts (the Center, or CASVA) at the National Gallery of Art in Washington, District of Columbia.

In addition to enhancing the stories we can tell from this data, bringing this information together can help our institutions in better serving our communities and broadening the scope of scholarship we support.

The data contributors:

Eliza Dermott (The Clark)  
Caroline Fowler (The Clark)  
Lidia Ferrara (Getty Research Institute/UCLA)  
Amelia Goerlitz (SAAM)  
Jen Rokoski (The Center)  
Reed Silverstein (SAAM)  
Nancy Um (Getty Research Institute)  
Matt Westerby (The Center)  
Caitlin Woolsey (The Clark)

### How to use and extend this data set

1. ### Awards

The primary data set contains information about programs, individuals, and their affiliations or city of residence at the time of award from a research institute.

* The `program` field gives the short name of the research institute that granted the award. Currently these programs are Center, Getty, Clark, and SAAM.  
* The `year` field gives the residence year based on the academic calendar in a four-digit numeral. For example 1995 for the academic year 1995-96.  
* `last_name` of the individual who received the award. Add any applicable suffixes in this field.  
* `first_name` of the individual. Include middle names in this field.  
* The `subprogram` field can be adapted to the needs of a given research institute, and refers to specific tracks, with reference to the relevant career stage, early or senior.  
* The `fellowship.title` field can be adapted to the needs of a given research institute, and refers to specific award titles.  
* The `affiliation_QID` field refers to the second table, **Affiliations**, described below. With this data set, our solution for scholars unaffiliated with an institution at the time of award is to give a city of residence (noting the institution “Type” as “City of Residence”) with the accompanying QID from the **Affiliation** table.
* The `multi.year_award` field is used for awards with a duration of more than one year and only pertains to scholars programs that offer such awards. The value `checked` means this award is more than one year.

2. ### Affiliations

A second table of affiliations extends the cross-program awards data. Affiliations represent institutions, organizations, or cities of residence that individuals stated at the time they received an award. These affiliations are published in various forms by awarding institutions (such as annual reports or on program webpages). The “Affiliations” table is used as an active database of institution names that follows consistent standards (outlined below). An individual, such as an independent scholar, may be represented by their stated city of residence at the time of award. 

* The `institution` field gives the primary name for the institution. For example, Academia Nacional de Ciencias (Q30266822). Primary institution names are determined by the top-level VIAF entry using the Latin alphabet (no Cyrillic languages are used). When Institution type is “City of Residence,” format is \[City, State\] for cities/towns in the US, i.e. \[Los Angeles, CA\]; and \[City, Country\] for cities/towns outside of the US, i.e. \[Lima, Peru\]. In cases where institutions merged into a new entity, the current name (as of the last date of this document) is given, such as Aix-Marseille University (founded in 2012 from the merger of Université Aix Marseille I, Aix Marseille II and Aix Marseille III).  
* The `type` field distinguishes between “Institutions” and “Cities of Residence.” As noted above, the Institution Type “City of Residence” is used for scholars unaffiliated at time of award.  
* The `affiliation_QID` field contains the Wikidata identifier corresponding to the Institution.   
* The `affiliation_alt_name` field contains English alternatives for non-English institution names, using the English version of the Institution name, as per Wikidata. If Wikidata does not include the English institution name version, the first VIAF entry in English is used.  
* The `affiliation_ROR_ID` field contains the Research Organization Registry (ROR) identifier corresponding to the institution.  
* The `city` field includes the name of the city or town where the Institution is located.  
* The `state_province` field includes the state (if USA) or province (where relevant) of the Institution. For US states and Canadian provinces, abbreviations are used, i.e. MA, CA, MI, BC, ON.   
* The `country` field includes the English names of Institution countries. USA is used for the United States; United Kingdom is used for England, Northern Ireland, Scotland or Wales; Russia is used for USSR, and current names (as of the last date of this document) are given in similar cases in place of historical names.  
* `Coordinate-location` field contains coordinate locations of Institutions in decimal format, such as “38.891389, \-77.02”. These values were obtained by reconciling Wikidata Q identifiers for affiliations using Open Refine reconciliation service.  
* `Lat` and `long` fields contain individual coordinates for latitude and longitude in decimal format.  

*A note on context*: affiliations for awards may not reflect a given person’s long-term place of residence or nationality. A scholar may have a stated affiliation with an institution that does not reflect their country of residence or nationality.

### Why Wikidata?

Wikidata Q identifiers were selected as unique identifiers due to the large number of records about institutions and cities that already existed on Wikidata and due to the ease of contributing without extensive technical knowledge or support. The project contributors edited or created new Wikidata records as needed, and new records can easily be created in the future. Wikidata records for any given affiliation may also be helpful to future users of this data set. For example, the record for the National Gallery of Art (Q214867) features over 120 Wikidata statements relating to other identifiers, including Getty AAT and VIAF.

### Why ROR?

ROR (Research Organization Registry) identifiers are included in this dataset in order to expand the dataset’s interoperability with other linked open data repositories. However, many affiliations in the dataset are not associated with an organization represented in ROR. Further, ROR identifiers do not include independent scholars, who are recorded by city of residence in this dataset. For this reason, ROR identifiers are intended as a supplement but not a key facet.

Using the reconciliation tool in OpenRefine, ROR identifiers were reconciled with corresponding Q identifiers and added to the dataset computationally. ROR identifiers link directly to the corresponding institution record in the ROR and contain valuable information and additional links. For example, the ROR record for Humboldt-Universität zu Berlin links to the institution’s website, lists other identifiers (ISNI, Crossref Funder ID, Wikidata Q ID, Getty TGN), includes alternate names, and links to both “Child Organizations” and “Related Organizations” of the institution.

### Further Analysis

The “Affiliations” table can be merged with the “Awards” table to populate institution information and ensure consistency across datasets. As an example, a data story created with Tableau by Nancy Um presents these comparative data across the four programs through their past scholars, while also serving as a representation of the changing scope of the field of art history. For these visualizations, a merging process was done computationally, using a “join()” function. Datasets were joined on the column `affiliation_QID.`After the datasets were combined and joined, scholar first and last names were combined, and then cleaned and clustered in OpenRefine, in order to minimize duplications. 

In the future, contributions from other peer research programs and beyond 2024 may be added to extend this data set.

