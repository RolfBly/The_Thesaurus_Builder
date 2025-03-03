# The Thesaurus Builder
Building a thesaurus from pre-existing terms in your database.



- The Thesaurus Builder
  - [Build from existing terms](#build-from-existing-terms)
  - [Fix domains](#fix-domains)
  - [Terms without a broader but with AAT URI]
  - [Terms without a broader without AAT URI]

 ## Build from existing terms

How does it work?
Have an excel document. In Sheet1, in column F there are multiple concepts and URI's in one cell. They correspond to the value in the same row in column B. The concepts and URI's in the cells in column F are seperated by a [$]. Individual concepts and their URI's are seperated by a [ ,] (comma and space) 
Example: paintings by form$http://vocab.getty.edu/aat/300033638, paintings (visual works)$http://vocab.getty.edu/aat/300033618, etc etc. 

In Sheet2 I have a list of terms in column B and a list of URI's in column C. 

terms2broaders.py is a Python script that creates a new Excel document where columns A to F from Sheet1 are in, and the URI's from column F in Sheet1 are matched with the URI's in column C from Sheet2. If there is a match it must be returned in column G in the new Excel. If there is more than one match a new column must be added for each match.

THIS Needs 1 workbook named terms_need_broaders.xslx, which is the result of an OpenRefine action to obtain the parentsXML from the AAT URI attached to terms (Sheet1) and a Collections export (Sheet2). Sheet1, columns A-F (contain A; priref, B; term C; AAT-URI, D; AAT-ID only, E; Full AAT-parentXML, F; parsed XML to human readable form), Sheet2 columns A-C (A; priref, B; term, C; AAT-URI. Keep in mind that export must be of terms + URI with exact match only)

Works on ANY LANGUAGE!

Example Sheet1
| A | B | C | D | E | F |
|----------|----------|----------|----------|----------|----------|
| 16   | schilderij  | http://vocab.getty.edu/aat/300177435   | 300177435   | XML export from OpenRefine   | paintings by form$http://vocab.getty.edu/aat/300033638, paintings (visual works)$http://vocab.getty.edu/aat/300033618, visual works by material or technique$http://vocab.getty.edu/aat/300191091, visual works (works)$http://vocab.getty.edu/aat/300191086, Visual Works (hierarchy name)$http://vocab.getty.edu/aat/300179869, Visual and Verbal Communication (hierarchy name)$http://vocab.getty.edu/aat/300264552, Objects Facet$http://vocab.getty.edu/aat/300264092   |
| 117   | serviesgoed   | http://vocab.getty.edu/aat/300236054   | 300236054   | XML export from OpenRefine   | sets (groups)$http://vocab.getty.edu/aat/300133146, object groupings by general context$http://vocab.getty.edu/aat/300241508, object groupings$http://vocab.getty.edu/aat/300241507, Object Groupings and Systems (hierarchy name)$http://vocab.getty.edu/aat/300241489, Objects Facet$http://vocab.getty.edu/aat/300264092   |
| 154   | persoonlijk object   | http://vocab.getty.edu/aat/300238982   | 300238982   | XML export from OpenRefine   | equipment by context$http://vocab.getty.edu/aat/300239170, equipment$http://vocab.getty.edu/aat/300122241, Tools and Equipment (hierarchy name)$http://vocab.getty.edu/aat/300022238, Furnishings and Equipment (hierarchy name)$http://vocab.getty.edu/aat/300264551, Objects Facet$http://vocab.getty.edu/aat/300264092   |
| 155   | servetring   | http://vocab.getty.edu/aat/300043085   | 300043085   | XML export from OpenRefine   | accessory containers for food service$http://vocab.getty.edu/aat/300198761, containers for serving and consuming food$http://vocab.getty.edu/aat/300198760, culinary containers$http://vocab.getty.edu/aat/300197577, containers by function or context$http://vocab.getty.edu/aat/300197200, containers (receptacles)$http://vocab.getty.edu/aat/300197197, Containers (hierarchy name)$http://vocab.getty.edu/aat/300045611, Furnishings and Equipment (hierarchy name)$http://vocab.getty.edu/aat/300264551, Objects Facet$http://vocab.getty.edu/aat/300264092   |



Example Sheet2
| A | B | C |
|----------|----------|----------|
| 1   | bord  | http://vocab.getty.edu/aat/300042991   |
| 6   | diepte   | http://vocab.getty.edu/aat/300072633   |
| 13   | schenking   | http://vocab.getty.edu/aat/300138913   |
| 16   | schilderij   | http://vocab.getty.edu/aat/300177435   |



 ## Fix domains

 SOMETHING SOMETHING

 ## Terms with minus Broader but plus AAT URI

  SOMETHING SOMETHING

 ## Terms with minus Broader and minus AAT URI

  SOMETHING SOMETHING
