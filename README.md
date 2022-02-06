Project Description and Aims:



see tcemg_analysis for the complete 
script and list of required softwares.
in house scripts are stored under /bin

Workflow:

1.Trimming with Trimmomatic\
5.Building donor libraries; interleave and merge samples
from donors and parent (first generation) in order to do
the co-assembly (see study design for co-assembly)\
6.co-assembly of donor libraries\
7.Single assembly of donor samples\
8.Adding libray name to contig headers. this is useful for building a
donor database for short-read mapping and merging binning information\
9.Making cumulative assembly plot to compare single- vs. co-assembly\
10.Selecting contigs >= 1kb for the rest of analysis\
11.Indexing large contigs before mapping\
12.Mapping samples from co-assembly libraries to each donor co-assembly contigs\
13.Binning the contigs using Metabat2\
14.Parsing contigs in bins info as text file for future mapping\
15.Check the quality of bins using checkM\
16.Taxonomic composition of bins using GTDB database\
17.Parsing bins (taxonomy, quality, and contig) information for a single donor database
18...
19...
20...

