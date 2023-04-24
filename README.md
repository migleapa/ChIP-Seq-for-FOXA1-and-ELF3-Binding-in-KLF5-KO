# ChiP-Seq-for-FOXA1-and-ELF3-Binding-in-KLF5-KO

FASTQ file "CAPAN1_H3K9me3_chr12.fq" (CAPAN1 cell line) was used:


Pipeline:

1) Aligning the FASTQ file to chromosome 12 using BOWTIE2, using the existing BOWTIE2 chromosome 12 reference index files.
2) Converting SAM to BAM, sorting the BAM, removing PCR using samtools
3) Calling H3K9me3 ChIP peaks using MACS2 using the “CAPAN1_input_chr12.rmdup.bam”
4) Filtering the peaks using a q value cutoff of “q < 1E-5” (-log10(q))

Following the workflow above the 4 bed files were generated (code for these particular files is not included)
  “GSM1919987_CFPAC1.wtKLF5_FOXA1_vs_INPUT.CAPAN1_peaks.bed”: the anti-FOXA1 ChIP-seq peak file of the wildtype KLF5 CFPAC1 cell line, Control.FOXA1
  “GSM1919985_CFPAC1.crKLF5_FOXA1_vs_INPUT.CAPAN1_peaks.bed”: the anti-FOXA1 ChIP-seq peak file of the KLF5 knockout CFPAC1 cell line, KLF5-KO.FOXA1
  “GSM1919986_CFPAC1.wtKLF5.ELF3_vs_INPUT.CAPAN1_peaks.bed”: the anti-ELF3 ChIP-seq peak file of the wildtype KLF5 CFPAC1 cell line, Control.ELF3
  “GSM1919984_CFPAC1.crKLF5.ELF3_vs_INPUT.CAPAN1_peaks.bed”: the anti-ELF3 ChIP-seq peak file of the KLF5 knockout CFPAC1 cell line, KLF5-KO.ELF3

5) Using ChIPseeker to annotate all the peak files, including various plots regarding the relation to TSS, gene body, genomic annotation (e.g., Promoter, 5’ UTR, 3’ UTR, Exon, Intron, Downstream, Intergenic). 
6) Comparing the paired samples, e.g., KLF5-KO.FOXA1 vs. Control.FOXA1; KLF5-KO.ELF3 vs. Control.ELF3: changes of FOXA1 and ELF3 binding following the knockout of KLF5; difference between the FOXA1 and ELF3 binding after the KLF5 knockout.
