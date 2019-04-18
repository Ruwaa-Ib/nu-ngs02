# [Impute2](https://mathgen.stats.ox.ac.uk/impute/impute_v2.html)


## Download

```bash
wget -c https://mathgen.stats.ox.ac.uk/impute/impute_v2.3.2_x86_64_static.tgz
tar -zxvf impute_v2.3.2_x86_64_static.tgz
```


## Example (IMPUTATION WITH ONE PHASED REFERENCE PANEL)

> *impute untyped SNPs in a study dataset from a panel of reference haplotypes.*


| option                | description                                                                                                                            | 
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------| 
| -m <file>             | File containing genotypes                                                                                                              | 
| -h <file1> <file2>    | File of known haplotypes, with one row per SNP and one column per haplotype. All alleles must be coded as 0 or 1.                      | 
| -l <file1> <file2>    | Legend file(s) with information about the SNPs in the -h file(s).                                                                      | 
| -g <file>             | File containing genotypes for a study cohort that you want to impute or phase.                                                         | 
| -strand_g <file>      | File showing the strand orientation of the SNP allele codings in the -g file                                                           | 
| -int <lower> <upper>  | Genomic interval to use for inference, as specified by <lower> and <upper> boundaries in base pair position                            | 
| -Ne <int>             | "Effective size" of the population (commonly denoted as Ne in the population genetics literature) from which your dataset was sampled. | 
| -o                    | Name of main output file.                                                                                                              | 




```bash
cd impute_v2.3.2_x86_64_static/

./impute2 \
 -m ./Example/example.chr22.map \
 -h ./Example/example.chr22.1kG.haps \
 -l ./Example/example.chr22.1kG.legend \
 -g ./Example/example.chr22.study.gens \
 -strand_g ./Example/example.chr22.study.strand \
 -int 20.4e6 20.5e6 \
 -Ne 20000 \
 -o ./Example/example.chr22.one.phased.impute2
```


### [Output Description](http://mathgen.stats.ox.ac.uk/impute/concordance_table_description.html)