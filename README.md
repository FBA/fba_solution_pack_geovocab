FBA Geo Vocab Solution Pack for Islandora
Create all required Fedora Objects, and creates empty collection objects, along 
with forms and inter collection relations.

The installation of the "FBA Object Linker Module" is a prerequisite for the 
"FBA Vocabulary Module".
The installation instructions for it can be found at:
https://github.com/FBA/islandora_autocomplete/blob/6.x/modules/sparql/README.md

It is necessary to load rows into the existing islandora_autocomplete table and
the islandora_autocomplete_sparql table, which has been created by the installation
of the "FBA Object Linker Module". The latter table contains the primary key of
the former as a foreign key, so it is important that these keys match once the rows
have been loaded.
If the table islandora_autocomplete is empty, it should be possible to perform a
MySQL Restore from the file 
"/modules/fba_solution_pack_geovocab/sql/autocomplete_sparql.sql"
and both tables will be recreated and the keys will match. If is is not empty,
then a more manual procedure will have to be adopted by the Systems Administrator to achieve this.

The listing of linked PDFs at the bottom of Vocabulary or geoVocabulary records
will only occur if the PDFs that are linked have the standard Collection and
Content model PIDs for the "Islandora PDF Solution Pack"
i.e. islandora:sp_pdf_collection and islandora:sp_strict_pdf. If an alternative
content model or collection is used, it is necessary to substitute the alternative
PID values for those of the standard PID values in the two SPARQL queries contained
in the "/modules/fba_solution_pack_vocabulary/vocab_obj_process.inc" file.
