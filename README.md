# Binder for BVCN sortmerna lesson

Initially forked from [here](https://github.com/binder-examples/conda). Thank you to the awesome [binder](https://mybinder.org/) team!

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/Arkadiy-Garber/bcvn-binder-sortmerna/master?urlpath=lab)

Part of the [Bioinformatics Virtual Coordination Network](https://biovcnet.github.io/) :)

## Walkthrough

Take a look around
    
    ls


Check out the rRNA database files

    cd rRNA_databases/sample/

Look inside one of the database FASTA files

    less silva-bac-16s-id90.fasta

go back to the home directory

    cd ../../

Go into the reads directory

    reads

Print the sortmerna help menu

    sortmerna -h
    
Run command on single-end reads

    sortmerna --reads MBIC-2-sw0.trimmed.sample.fastq --ref ../rRNA_databases/sample/silva-bac-16s-id90.fasta --ref ../rRNA_databases/sample/silva-bac-23s-id98.fasta --fastx --aligned MBIC-2-sw0.trimmed.sample.rRNA.fastq --other MBIC-2-sw0.trimmed.sample.mRNA.fastq

Examine the output files. Look inside the .log output to see the summary of results

    less MBIC-2-sw0.trimmed.sample.rRNA.fastq.log

Run command on paired-end reads

    sortmerna --reads SRR6039934_1P.fastq --reads SRR6039934_2P.fastq --ref ../rRNA_databases/sample/silva-bac-16s-id90.fasta --ref ../rRNA_databases/sample/silva-bac-23s-id98.fasta --fastx --other SRR6039934.mRNA --out2 --paired_out

Run command on single-end reads, creating an OTU map

    sortmerna --reads MBIC-2-sw0.trimmed.sample.fastq --ref ../rRNA_databases/sample/silva-bac-16s-id90.fasta --ref ../rRNA_databases/sample/silva-bac-23s-id98.fasta --fastx --aligned MBIC-2-sw0.trimmed.sample.rRNA.fastq --other MBIC-2-sw0.trimmed.sample.mRNA.fastq --otu_map

Examine OTU map output

    less -S MBIC-2-sw0.trimmed.sample.rRNA.fastq_otus.txt

## Bonus section (if I don't run out of time)
Run Flash
    
    flash SRR6039934_1P.fastq SRR6039934_2P.fastq

Run SortMeRNA on Flashed reads

    sortmerna --reads ./out.extendedFrags.fastq --ref ../rRNA_databases/sample/silva-bac-16s-id90.fasta --ref ../rRNA_databases/sample/silva-bac-23s-id98.fasta --fastx --aligned out.extendedFrags.rRNA.fastq --other out.extendedFrags.mRNA.fastq







