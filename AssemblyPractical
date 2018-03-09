Transcriptome Assembly Practical
--

You all should be using an AMI where the requisite software is already installed. For whne you get home, and want to install this on your own machines, see http://oyster-river-protocol.readthedocs.io/en/latest/aws_setup.html



> Make a directory that will contain all of your assembly materials

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
python $(which run_BUSCO.py) -i $HOME/share/SRR3499127.orthomerged.fasta -m transcriptome --cpu 4 -o plant
```
