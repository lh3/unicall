### Getting Started

```sh
wget -O- https://github.com/lh3/unicall/releases/download/v1/unicall-0.1_x64-linux.tar.bz2 | tar jxf -
unicall.kit/run-unicall hs37d5.fa mydata.bam > mydata.mak && make -j8 -f mydata.mak
```
In this example, the filtered small variants are available in `mydata.flt.vcf.gz`.

### Introduction

UniCall is a wrapper around several variant callers, particularly designed for
Illumina data sequenced from a single high-coverage human sample. It takes a
reference genome and sorted alignment as input, and outputs filtered variants
in the VCF format. The wrapper provides a few advantages over separate callers:

1. Simple unified interface to multiple variant callers, including
   GATK-HaplotypeCaller, GATK-UnifiedGenotyper, FreeBayes, Samtools and
   Platypus.

2. Potentially more effective settings and hard filters for a single
   high-coverage human sample, according to the CHM1-CHM13 benchmark data (to
   be released).

3. Makefile-based parallelization by separating chromosomes at assembly gaps.

4. Download-and-use portable precompiled binaries for open source variant
   callers.
