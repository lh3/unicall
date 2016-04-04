### Getting Started

```sh
unicall.kit/run-unicall hs37d5.fa mydata.bam > mydata.mak && make -j8 -f mydata.mak
```

### Introduction

UniCall is a wrapper around several variant callers, particularly designed for
Illumina data sequenced from a single high-coverage human sample. It takes a
reference genome and sorted alignment as input, and outputs filtered variants
in the VCF format. The wrapper provides a few advantages over seaprate callers:

1. Simple unified interface to multiple common variant callers, including
   GATK-HaplotypeCaller, GATK-UnifiedGenotyper, FreeBayes, Samtools and
   Platypus.

2. Potentially more effective settings and hard filters for a single
   high-coverage human sample, according to the CHM1-CHM13 benchmark data (to
   be released).

3. Parallelization by separating chromosomes at assembly gaps.

4. Portable precompiled binaries for open source variant callers.
