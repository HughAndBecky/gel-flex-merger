# U̠t-Ma'in FLEx Wordlist database README

This readme is specially written so the two datasets mentioned below can be merged.

## The two data bases
There are two databases which need to be merged with all data and relationships being retained. The are named as follows:
*FLEx backup filename*:

*  gel Wordlist 2013-02-22 1819.fwbackup (DB1)
*  gel 2017 words and texts 2017-07-12 0021 Backup to send to Dallas for merger.fwbackup (DB2)

The (DB1) FLEx Database contains data imported from an .xls; 5 custom fields were added. Semantic Domain information from a built-into-FLEx list is also matched to each entry. We seek to retain all of this information in the merged dataset.

FLEx 8.0 will open (DB1). When it does it converts the file to "the most recent version". So this file is older than FLEx 8.0 but we are unsure what version of FLEx 7 was used to create the file.

The DB2 dataset is created with FLEx 8.3.8 on Linux. It too has custom fields. DB2 has additional lexemes (new entires compared to DB1) that come mostly from texts processed in DB2.

gel_ModOrth



### Writing systems for (DB1)
**Vernacular**:
gel_IPA
gel_orth - no data from this writing system in gel Wordlist 2013-02-22 1819.fwbackup  should overwrite gel_orth in the gel 2017 words and texts 2017-06-25 xxxx.fwbackup.

**Analysis**:
Eng - English
Swa - Swahili
Frn - French
Hau - Hausa
Hau_CL - Hausa Common Language
Spn - Spanish

### Fields used in (DB1)
**Custom fields**:
Plural
Class Number
Class
POS fr List
WACWL

**Other fields used**:
Lexeme
Citation Form
Pronunciation
Semantic Domain
General Note
Note
Gloss

(DB1) data can overwrite lexical data in the other FLEx database, as long as the lexemes are matched to the data in (DB2) on the number from the WACWL custom field. Both Databases should have WACWL numbers in them.
