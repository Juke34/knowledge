# Split a FASTA file
## Review of the main ways to split a FASTA file


| tool | language | One sequence per file | Can select nb of output files  | Can select nb seq by file | Can select size of output files | Overlap possible (when sequence cut) | Can cut sequences | Subsample possible | Example | Comment
| -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
awk | awk | yes | no | yes | no | no | no | no | [example](#awk) | 
split | bash | yes | no | yes | yes | no | no | no | [example](#split) | Fasta must be single line fasta (one header + one single sequence line)
bash | bash | yes | no | no | no | no | no | no | [example](#bash) |  Individual files will have the name of the corresponding sequence, without leading >
gaas_fasta_splitter.pl from [GAAS](https://github.com/NBISweden/GAAS) | Perl | yes | yes | yes | no | yes | yes | yes (stop when nb of files with the nb of seq asked reached) | [example](#agat) | 
[PyFasta](https://pypi.org/project/pyfasta/#command-line-interface) | Python | yes | yes | no  | no | yes | yes | NA | [example](#pyfasta) | 
[pyfaidx](https://github.com/mdshw5/pyfaidx) | Python | yes | no | no | no | no | no | no | [example](#pyfaidx) |
[GenomeTools](https://github.com/genometools/genometools) |  Mostly C | yes | yes | no | yes | no | no | no | [example](#genometools) | 
[seqretsplit](http://emboss.sourceforge.net/apps/release/6.6/emboss/apps/seqretsplit.html) from [EMBOSS](http://emboss.sourceforge.net/what/) |  C | yes | no | no | no | no | no | no | [example](#emboss) |
bp_seqretsplit.pl from [Bioperl](https://github.com/bioperl/bioperl-live) |  perl | yes | no | no | no | no | no | no | [example](#bp_seqretsplit) |
faSplit from [Kent utils](http://hgdownload.cse.ucsc.edu/admin/exe/) | C | yes | yes | no | yes | yes | yes | no | [example](#faSplit) |
partition.sh from [BBMap](https://jgi.doe.gov/data-and-tools/bbtools/bb-tools-user-guide/bbmap-guide/) | Java | no | yes | no | no | no | no | no | [example](#bbmap)  | multithreaded 
[seqkit](https://github.com/shenwei356/seqkit) | Go | yes | yes | yes | no | no | no | yes (subsequence of given region) | [example](https://bioinf.shenwei.me/seqkit/usage/#split) | 
[SEDA](https://github.com/sing-group/seda)| java | yes | yes | yes | no | no | no | yes (randomizable) | [example](https://www.sing-group.org/seda/manual/operations.html#id19) | GUI only. Using `Independent extractions` and `Randomize` options give the possibility to get sequences picked several times. There is an extra function called [regular expression split](https://www.sing-group.org/seda/manual/operations.html#regular-expression-split) (use of regex for selecting sequence by matching headers)


# Example

## Awk

size = chunk size
pre = output file prefix
pad = padding width (the width of the numeric suffix).

```
awk -v size=1000 -v pre=prefix -v pad=5 '
   /^>/ { n++; if (n % size == 1) { close(fname); fname = sprintf("%s.%0" pad "d", pre, n) } }
   { print >> fname }
' input.fasta
```

## Split

`split -l 2000 input.fasta`

## Bash

```
while read line
do
    if [[ ${line:0:1} == '>' ]]
    then
        outfile=${line#>}.fa
        echo $line > $outfile
    else
        echo $line >> $outfile
    fi
done < myseq.fa
```

## GAAS

split the fasta file into one file per sequence

`gaas_fasta_splitter.pl -f input.fa --nb_seq_by_chunk 1`

split the fasta file into files of 100 sequences

`gaas_fasta_splitter.pl  --nb_seq_by_chunk 100`

split the fasta file into 10 files

`gaas_fasta_splitter.pl  --nb_chunks 10`

split the fasta file into 10 files and cut the sequence in chunk of 1000000 bp

`gaas_fasta_splitter.pl  --nb_chunks 10 --size_seq 1000000`

split the fasta file into 10 files and cut the sequence in chunk of 1000000 bp with overlap of 2000 bp

`gaas_fasta_splitter.pl  --nb_chunks 10 --size_seq 1000000 --overlap 2000`

split the fasta file into 10 files of 20 sequences and the original sequences are cut in chunk of 1000000 bp with overlap of 2000 bp. If all the input data cannot be contained into the 10 files of 20 sequences, the output is actually a subsample of the input data.

`gaas_fasta_splitter.pl  --nb_chunks 10 --nb_seq_by_chunk 20 --size_seq 1000000 --overlap 2000`

## PyFasta

split a fasta file into 6 new files of relatively even size:

`pyfasta split -n 6 original.fasta`

split the fasta file into one new file per header with “%(seqid)s” being filled into each filename.:

`pyfasta split –header “%(seqid)s.fasta” original.fasta`

create 1 new fasta file with the sequence split into 10K-mers:

`pyfasta split -n 1 -k 10000 original.fasta`

2 new fasta files with the sequence split into 10K-mers with 2K overlap:

`pyfasta split -n 2 -k 10000 -o 2000 original.fasta`


## pyfaidx

`faidx --split-files original.fasta`

## GenomeTools

`gt splitfasta -splitdesc multifastafile.fa`

## EMBOSS

`seqretsplit input.fa`

## bp_seqretsplit

`bp_seqretsplit file1 file2`

Similar to:  
```
#!/usr/bin/env perl

use strict;
use warnings;
use Bio::SeqIO;
my $in = Bio::SeqIO->new(-format => 'fasta',
                         -fh   => \*ARGV);
while( my $s = $in->next_seq ) {
    my ($id) = ($s->id =~ /^(?:\w+)\|(\S+)\|/);
    Bio::SeqIO->new(-format => 'fasta',
                    -file   => ">".$id.".fasta")->write_seq($s);
}
```
## faSplit

Break up scaffolds.fa using sequence names as file names (one sequence per file).
Use the terminating / on the outRoot to get it to work correctly:

`faSplit byname scaffolds.fa outRoot/`

break up estAll.fa into 100 files
(numbered est001.fa est002.fa, ... est100.fa
Files will only be broken at fa record boundaries:

`faSplit sequence estAll.fa 100 est`

break up chr1.fa into 10 files:

`faSplit base chr1.fa 10 1_`

break up input.fa into 2000 base chunks:

`faSplit size input.fa 2000 outRoot`

break up est.fa into files of about 20000 bytes each by record:

`faSplit about est.fa 20000 outRoot`

Break up chrN.fa into files of at most 20000 bases each, 
at gap boundaries if possible.  If the sequence ends in N's, the last
piece, if larger than 20000, will be all one piece:

`faSplit gap chrN.fa 20000 outRoot`

## BBMap

Split the fasta file into 5 files:

`partition.sh in=file.fasta out=part%.fasta ways=5`


## Reference

https://www.biostars.org/p/229441/
