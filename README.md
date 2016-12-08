# biseqMethCalling
* __Title:__ biseqMethCalling
* __Description:__ Methylation calling script for bisulfite sequencing
* __Authors:__ Christoph Bock, Natalie Jaeger, Fabian Mueller, Michael Ziller
* __Version:__ 2012-08-22

The following methods are supported
* Whole genome bisulfite sequencing (WGBS)
* Reduced-representation bisulfite sequencing (RRBS)
* Hybrid-selection bisulfite sequencing
* Other variants of region-specific bisulfite sequencing (e.g. MethylCap-biseq and ChIP-biseq)

By default CpG are analyzed, but other sequence contexts (CpA, CpH, CpHpG, etc.) are also supported.

## Usage
The main script is `biseqMethCalling.py`. See `python biseqMethCalling.py --help` for a full listing of parameters

### Input
* (multiple) BAM files containing containing read alignments
* parameters (see --help for more info)

### Output
* statistics (see the description in StatisticsCollection.writeStatistics2files() for details)
* CpGs with genomic coordinates and methylation ratios as a bed file
* Fragment coverage: coordinates, readcounts and CpG methylation ratios of each generated fragment (RRBS: MspI digestion, WGBSS: Paired end reads)
* Reads: coords (read and fragment the read is on), CpG (possibly other patterns) of __processed__ reads
* ReadDetails: more detailed read info for processed reads including base quality details, alignment/mismatch details, conversion rates, ...
* runtime profile files for each processed region, if desired
* if the verbose option is set: information on the processed windows/regions
* log files
* a vast amount of temporary files for each processed region
