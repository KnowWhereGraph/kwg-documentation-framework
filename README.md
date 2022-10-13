# kwg-documentation-framework
The purpose of this project is to create a single source of truth for the kwg schema. We want to:

1. Have a method for easily generating the documentation when anything changes
2. Ensure that the schema files are the single source of truth (i.e., well documented)
3. Connect the schema files to the metadata model appropriately

## Running
run the `generate-documentation.py` file

## Program Flow
* The program will expect there to be a folder of schemas, which is expected to have a folder for each dataset
* the program will ingest each schema ttl and construct a markdown file for it, in the manner that exists for the code readmes.
* Each code readme should have the following sections, after a title for the dataset name
  * Description
  * Metadata
    * This should be populated with the dataset specific metadata model characteristics
  * Schema Diagram
  * Axioms
  * Explanations
  * Remarks
    * If there are no comments in the ttl, the remarks section should not appear.
* convert the markdown file for the dataset to a pdf using pandoc
* use `pdfunite` to combine all of the schema readme markdowns into a single document.
