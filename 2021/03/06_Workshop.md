# Workshop

## Data

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
    ```