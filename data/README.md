# CSV Creation from ChEMBL Database

This brief README outlines the steps taken to create the `serotonin_binding_summary.csv` file in this directory, containing all molecules with at least one serotonin binding affinity record in the ChEMBL SQL database `chembl_35.db` ([Link](https://ftp.ebi.ac.uk/pub/databases/chembl/ChEMBLdb/releases/chembl_35/)), along with the average pchembl_value values for each receptor.

## Extracting Data from ChEMBL

Retrieved SMILES, receptor names, and standardized binding affinity values (pchembl_value) for serotonin receptors by joining the following tables:

-   `molecule_dictionary` (for the primary key, `molregno`)
-   `compound_structures` (for `canonical_smiles`)
-   `activities` (for `pchembl_value`)
-   `assays` (to link to receptor targets)
-   `target_dictionary` (for receptor names)

Filtered selected entries to ensure that `td.pref_name` contains "5-HT" and `pchembl_value` is not null.

## Aggregating Data into a Table

Consolidated the data so that each molecule (identified by `molregno`) has one row with average binding affinity values for all serotonin receptors.

Used `AVG()` to compute the mean of pchembl_value for each receptor per molecule (this handles duplicate assay entries). Grouped the data by `molregno` and `canonical_smiles`. Created a new table called `serotonin_binding_summary` from the aggregated query.

The resulting table was then exported to `serotonin_binding_summary.csv`.
