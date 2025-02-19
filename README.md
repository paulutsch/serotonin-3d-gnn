This project builds upon research done by Łapińska et al. (2024): https://doi.org/10.3390/pharmaceutics16030349

Data used for training: https://ftp.ebi.ac.uk/pub/databases/chembl/ChEMBLdb/releases/chembl_35/
Move the chembl_35_sqlite.tar.gz file into the data/ dir.

Data used for pre-training: https://www.kaggle.com/datasets/basu369victor/zinc250k?resource=download

The research linked above presents two Quantitative Structure-Activity Relationship (QSAR) models to predict serotonergic binding affinity and selectivity, respectively, using Mordred molecular 2D descriptors. Specifically, one model classifies compounds binarily as "active" or "inactive", with a cutoff of pKi = 7. Another model does multiclass classification to predict the serotonergic selectivity of compounds previously classified as "active".

I am following the same approach with the only difference of replacing the input modality of 2D molecular descriptors with 3d graphical representations.
