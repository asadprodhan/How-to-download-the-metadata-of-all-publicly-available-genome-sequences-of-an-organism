# **How to download the metadata of all publicly available genome sequences of an organism?** <br />


### **Asad Prodhan PhD** 


*https://asadprodhan.github.io/*


<br />


### **Step 1: Install NCBI datasets**


Datasets is a command line tool that allows you to easily download data from NCBI.


```
conda install -c conda-forge ncbi-datasets-cli
```


> For more information on the usage of datasets, explore the following pages:


https://www.ncbi.nlm.nih.gov/datasets/docs/v2/download-and-install/


https://github.com/ncbi/datasets


### **Step 2: Download the metadata of all the available genomes of Fusarium as an example**


The following command will download the entire metadata:


```
datasets summary genome taxon 'Fusarium' --as-json-lines | dataformat tsv genome > Fusarium_genomes_summary.tsv
```


> However, you can download the selected metadata of your interest only:


```
datasets summary genome taxon 'Fusarium' --as-json-lines | dataformat tsv genome --fields accession,assminfo-assembly-method,assminfo-bioproject,assminfo-biosample-accession,assminfo-biosample-bioproject-accession,assminfo-biosample-description-organism-common-name,assminfo-biosample-description-organism-name,assminfo-biosample-description-organism-tax-id,assminfo-biosample-owner-name,assminfo-biosample-package,assminfo-biosample-publication-date,assminfo-biosample-status-status,assminfo-biosample-submission-date,assminfo-description,assminfo-level,assminfo-name,assminfo-refseq-category,assminfo-release-date,assminfo-sequencing-tech,assminfo-status,assminfo-submitter,assminfo-type,assmstats-contig-l50,assmstats-contig-n50,assmstats-gc-count,assmstats-gc-percent,assmstats-genome-coverage,assmstats-number-of-contigs,assmstats-number-of-scaffolds,assmstats-scaffold-l50,assmstats-scaffold-n50,assmstats-total-number-of-chromosomes,assmstats-total-sequence-len,assmstats-total-ungapped-len,organelle-bioproject-accessions,organelle-submitter,organelle-total-seq-length,organism-common-name,organism-name,organism-tax-id > Fusarium_genomes_summary.tsv
```


To check the metadata fields (columns): 


```
dataformat tsv genome –help
```


