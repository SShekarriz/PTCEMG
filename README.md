
## TCEMG for pediatric patients with UC.

see tcemg_analysis for the complete 
script and list of required softwares.
in house scripts are stored under /bin

Workflow:

1 Trimming with Trimmomatic\

2 Building donor libraries; 
- A) interleave F and R reads into inter for each pt
- B) Concatanate the two sample for each pt; using mapfile

3 Assemble merged reads (co-assembly) via metaspade

4 Remove contigs < 1kb (a python script; see bin/)

5 Index the contigs using. (required for mapping)

6 identify CDS and annotate contigs via Prokka

7 Building anvio database for each assembly;
- A) identify CDS prodiga,
- B) multiple marker database via HMM
- C) this gives option to add many future annotations

8 map each sample from patient to their co-assembly via bwa mem

9 index the outputs

10 get 1x coverage for each contig via samtools coverage

11 profile each bam file so that it can be imported to anvio database

12 Binning the contigs via Metabat2

13 parse the contig names into seperated files, this will be useful for cumulative plots

14 Merge all the profiled anvio files into a single database;
- this can be used for anvio visualization
- it will give us all sort of normalized coverage information for genes/bins

15 check the quality of bins using checkM

16 running GTDB-k to assign taxonomy for all bins.
- this also give us phylogenetic tree based on gtdb marker alignment

17 Parsing all bin info into summary output; see bin/ for code
- bins with > 70% completeness and <10% contamination are MAGs
- generate a table that contain checkM, taxonomy, and 1X coverage of bins

18 copy all gene summary outputs from anvio in a gene summary folder

19 Identify plasmid from contigs using SCAPP
- this required debrijun graph data from spade

20 Running Humann3 for each sample
- this generate read-based taxonomy of each sample (best option to do taxonomy)
- also genefamily/ pathways annotations of each sample

21 code and workflow are backed in my github
