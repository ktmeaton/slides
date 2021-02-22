# Workshop

## Charts

- [Plague Black Death SVG](https://raw.githack.com/ktmeaton/slides/master/2021/03/06_Workshop_Plague-Black-Death.svg)
- [Plague Black Death HTML](https://raw.githack.com/ktmeaton/slides/master/2021/03/06_Workshop_Plague-Black-Death.html)
    - Max Depth: 7
    - Font Size: 40
- [Plague Pre-Justinian SVG](https://raw.githack.com/ktmeaton/slides/master/2021/03/06_Workshop_Plague-Pre-Justinian.svg)
- [Plague Pre-Justinian HTML](https://raw.githack.com/ktmeaton/slides/master/2021/03/06_Workshop_Plague-Pre-Justinian.html)
    - Max Depth: 7
    - Font Size: 25

## Analysis

### Plague (Black Death)

1. Convert to fasta.

    ```bash
    samtools fasta Yersinia_pestis_Black-Death-8291.bam > Yersinia_pestis_Black-Death-8291.fasta
    ```

2. Taxonomic classification with Kraken.

    ```bash
    $ /home/keaton/Projects/Plague/YorkBarbican/envs/kraken2/bin/kraken2 \
        --db /2/scratch/keaton/kraken2-microbial-fatfree/ \
        --threads 10 \
        --confidence 0.2  \
        --report-minimizer-data \
        --minimum-hit-groups 2 \
        --output kraken2/Yersinia_pestis_Black-Death-8291.output \
        --report kraken2/Yersinia_pestis_Black-Death-8291.report \
        data/Yersinia_pestis_Black-Death-8291.fasta

    9776505 sequences (535.46 Mbp) processed in 7.526s (77936.7 Kseq/m, 4268.62 Mbp/m).
    7012387 sequences classified (71.73%)
    2764118 sequences unclassified (28.27%)
    ```

3. Krona chart creation.

    ```bash
    # Krona text
    $ cut \
        -f 2,3 \
        kraken2/Yersinia_pestis_Black-Death-8291.output \
        > kraken2/Yersinia_pestis_Black-Death-8291.krona

    # Krona html
    $ /home/keaton/myapps/KronaTools-2.8/bin/ktImportTaxonomy \
        -i \
        -k \
        -o kraken2/Yersinia_pestis_Black-Death-8291.krona.html \
        -tax /home/keaton/database/Krona/taxonomy-2019-12-16/ \
        kraken2/Yersinia_pestis_Black-Death-8291.krona

    Loading taxonomy...
    Importing kraken2/Yersinia_pestis_Black-Death-8291.krona...
    [ WARNING ]  The following taxonomy IDs were not found in the local database and were set to root (if they were recently added to NCBI, use updateTaxonomy.sh to update the local
                    database): 1743172 2109625 1049581 1981981 644968 2036817 2183547 1826873 134962 2071623
    Writing kraken2/Yersinia_pestis_Black-Death-8291.krona.html...
    [ WARNING ]  Too many query IDs to store in chart; storing supplemental files in 'kraken2/Yersinia_pestis_Black-Death-8291.krona.html.files'.        
    ```

### Plague (Pre-Justinian)

- BioSample: SAMEA1061800
- Strain: DA101
- DOI: https://doi.org/10.1038/s41586-018-0094-2  

1. Convert to fasta.

    ```bash
    samtools fasta Yersinia_pestis_Pre-Justinian-DA101.bam > Yersinia_pestis_Pre-Justinian-DA101.fasta
    ```

2. Taxonomic classification with Kraken.

    ```bash
    $ /home/keaton/Projects/Plague/YorkBarbican/envs/kraken2/bin/kraken2 \
    --db /2/scratch/keaton/kraken2-microbial-fatfree/ \
    --threads 10 \
    --confidence 0.2  \
    --report-minimizer-data \
    --minimum-hit-groups 2 \
    --output kraken2/Yersinia_pestis_Pre-Justinian-DA101.output \
    --report kraken2/Yersinia_pestis_Pre-Justinian-DA101.report \
    data/Yersinia_pestis_Pre-Justinian-DA101.fasta

    Loading database information... done.
    10086461 sequences (619.14 Mbp) processed in 10.512s (57573.6 Kseq/m, 3534.03 Mbp/m).
    477198 sequences classified (4.73%)
    9609263 sequences unclassified (95.27%)
    ```

3. Krona chart creation.

    ```bash
    # Krona text
    $ cut \
        -f 2,3 \
        kraken2/Yersinia_pestis_Pre-Justinian-DA101.output \
        > kraken2/Yersinia_pestis_Pre-Justinian-DA101.krona

    # Krona html
    $ /home/keaton/myapps/KronaTools-2.8/bin/ktImportTaxonomy \
        -i \
        -k \
        -o kraken2/Yersinia_pestis_Pre-Justinian-DA101.krona.html \
        -tax /home/keaton/database/Krona/taxonomy-2019-12-16/ \
        kraken2/Yersinia_pestis_Pre-Justinian-DA101.krona

    Loading taxonomy...
    Importing kraken2/Yersinia_pestis_Pre-Justinian-DA101.krona...
    [ WARNING ]  The following taxonomy IDs were not found in the local database and were set to root (if they were recently added to NCBI, use updateTaxonomy.sh to update
                    the local database): 2171980 2109625 134962 443255 2183547 2036817 330 62153
    Writing kraken2/Yersinia_pestis_Pre-Justinian-DA101.krona.html...
    [ WARNING ]  Too many query IDs to store in chart; storing supplemental files in 'kraken2/Yersinia_pestis_Pre-Justinian-DA101.krona.html.files'.
    ```