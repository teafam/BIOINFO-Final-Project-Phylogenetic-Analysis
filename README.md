# BIOINFO Final Project: Phylogenetic Analysis
This project aims to replicate the phylogenetic analysis found inthe 3rd phase of the paper
"Rapid SARS-CoV-2 whole-genome sequencing and analysis for informed public health 
decision-making in the Netherlands", by Munnik et al. (2020). This paper can be found through
this link: https://www.nature.com/articles/s41591-020-0997-y

Moreover, the contributors extended this study by using a different set of sequence data, 
particularly that of the sequence dataset from the Philippines. As such, this process will 
follow two separate parts: replication and extension.

For both procedures, it is important to acquire first the sequence data to be imported in
these programs. These files must be in the FASTA extension, which could be retrieved from 
a website such as the GISAID site. The replication process makes use of sequence data from
the Netherlands, while the extension process uses sequence data from the Philippines.    

# Replication process
In total, there are <b>4 programs</b> to be used in the replication method: 
1. [BIOINFO Netherlands only] FESTA to CSV Conversion.ipynb
2. MUSCLE.exe
3. iqtree-1.6.12-Windows.zip
4. 

# Data Preprocessing
For this section, open the jupyter notebook titled "[BIOINFO Netherlands only] 
FESTA to CSV Conversion.ipynb". This notebook is responsible for providing the basic 
statistics of the raw file, the downsizing of data using random sampling, the labelling 
of cities/towns/villages to its respective Dutch provinces, and writing the sampled 
FASTA file.

This procedure is straightforward, as the user would only need to run the scripts in a 
sequential order, from top to bottom. Should there be any Dutch provinces, cities, towns,
or villages that are not included in the code, add these information as necessary. 

The two inputs needed for this would be the raw Netherlands FASTA sequence data file, and
a placeholder FASTA file for the output (should be initially empty). Comments are provided
within each code segment to provide description to the purpose of each section. Keep in 
mind that each code block is most likely dependent on the previous block, therefore no step
should be skipped or ignored.    

# MUSCLE Alignment

# IQ-TREE Building

# FIGTREE Visualization (???)

# Extension process

# Data Preprocessing

# MUSCLE Alignment

# IQ-TREE Building

# FIGTREE Visualization (???)
