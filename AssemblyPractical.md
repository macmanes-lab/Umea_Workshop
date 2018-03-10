Transcriptome Assembly Practical
--

#### The following details the steps involved in:

- Generating a _de novo_ RNA-Seq assembly using the Oyster River Protocol
- Evaluating the quality of the assembly
  - BUSCO and TransRate
- Quantifying transcript expression levels
  - Using Salmon
- Functionally annotating transcripts
  - dammit
- Predicting coding regions
  - TransDecoder

#### Oyster River Protocol

One of the nice things about the ORP is that it does, automatically, the assembly, evaluation, and quantification of the assembly. I will more fully introduce these procedures in the lecture part of the day.

All required software and data are provided pre-installed on an Amazon EC2 AMI. For when you get home, and want to install this on your own machines, see http://oyster-river-protocol.readthedocs.io/en/latest/aws_setup.html

The workshop materials here expect that you have some familiarity with UNIX. If you need a refresher, the Command Line Bootcamp is good (http://rik.smith-unna.com/command_line_bootcamp/). For extended prep, see DataCarpentry and SoftwareCarpentry organizations.

#### About the Tutorial

This tutorial uses a very small dataset, so that everyone can have the opportunity to complete an assembly without using a truly massive amount of compute. **BUT**, if you can assembly the small dataset, you can assembly a bigger one, too, assuming you have a big enough computer. 

#### Tutorial Begins

> The 1st thing you should always do when logging in to a new machine is explore the directory structure. Where are the data, where are programs installed, etc.



> Make a directory that will contain all of your assembly materials. In general, it's smart practice to have individual folders for each step in your bioinformatics pipeline.

```
mkdir $HOME/assembly_practical && cd $HOME/assembly_practical
```

> Assemble using the ORP

```
$HOME/Oyster_River_Protocol/oyster.mk main \
MEM=50 \
CPU=24 \
READ1=$HOME/share/reads.1.fq.gz \
READ2=$HOME/share/reads.2.fq.gz \
RUNOUT=ORPtest
```

> BUSCO

```
python $(which run_BUSCO.py) -m transcriptome -i $HOME/share/SRR1221220.orthomerged.fasta --out SRR1221220 -t 2
```
