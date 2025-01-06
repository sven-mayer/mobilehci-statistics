# MobileHCI Statistics
The repository contains data and script to analyze the ACM Conference MobileHCI.

The different scripts should be run subsequently, starting with the lowest number to reproduce the information. `Step_10_Get-Proceedings.ipynb` can be skipped as the data is already included in the repository. This step can take multiple days, and the raw data from the ACM DL needs to be crawled without risking IP blocking. 

## Utilizes 

### Declarations
All country names are according to ISO 3166 using the list of [github.comlukes/ISO-3166-Countries-with-Regional-Codes](https://github.com/lukes/ISO-3166-Countries-with-Regional-Codes/blob/master/all/all.csv) regions are according to [UN MP49](https://unstats.un.org/unsd/methodology/m49/overview). However, ACM does not always use the Official names; thus, to map ACM names to the Alpha-3 country code, we can use `uitls/mapCountryNamesACM.csv` to clean the data coming from ACM. 

Affiliation names are commonly associated with the [https://www.wikidata.org/](https://www.wikidata.org/) entry. Affiliation names are typically in line with their English names. If they are different, then the affiliation has a different official name. `uitls/mapAffiliationDefault.csv` provides the link map between the affiliation, Wikimedia entry, and the default county. 

For the map draing we use the data as defined by [github.com/nvkelso/natural-earth-vector](https://github.com/nvkelso/natural-earth-vector/tree/master)

### Mapper
Since various affiliations have multiple names, one big clearning task is to consolidate them all. All current fixes are stored in  `uitls/mapAffiliation.csv`. If one is missing, they can be simply added to the `uitls/mapAffiliation.csv` file.

### General Data
The folder `data` holds general information about the conferences, e.g. the locations, acceptance rates.