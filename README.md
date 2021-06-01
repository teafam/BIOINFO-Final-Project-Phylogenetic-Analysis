![BIOINFOFinalReport](https://cdn.discordapp.com/attachments/821762884668358657/849300106117382144/bioinfo_readme_header.jpg)
> This is a course requirement for the subject BioInformatics (BIOINFO). 

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
In total, there are <b>4 programs</b> to be used in the both methods: 
1. FESTA to CSV Conversion.ipynb
2. muscle.exe
3. iqtree-1.6.12-Windows folder
4. FigTree v1.4.4 folder

# Data Preprocessing
* For Netherlands dataset:
1. Prepare the raw Netherlands FASTA sequence data file.
2. Perpare a placeholder FASTA file for the output (should be initially empty).
3. Open the jupyter notebook titled "[BIOINFO Netherlands only] FESTA to CSV Conversion.ipynb". 
4. Run the scripts in a sequential order, from top to bottom. 

The notebook is responsible for providing the basic 
statistics of the raw file, the removing of sequences with more than 10% of 'N' characters,
the downsizing of data using random sampling, the labelling of cities/towns/villages to 
its respective Dutch provinces, and the writing of the sampled FASTA file.

Should there be any Dutch provinces, cities, towns,
or villages that are not included in the code, add these information as necessary. 

Comments are provided within each code segment to provide description to the purpose of each section. Keep in 
mind that each code block is most likely dependent on the previous block, therefore no step
should be skipped or ignored.

* For Philippines dataset:
1. Prepare the raw Philippines FASTA sequence data file.
2. Perpare a placeholder FASTA file for the output (should be initially empty).
3. Open the jupyter notebook titled "[BIOINFO Philippines only] FESTA to CSV Conversion.ipynb". 
4. Run the scripts in a sequential order, from top to bottom. 

The notebook is responsible for providing the basic 
statistics of the raw file, the removing of sequences with more than 10% of 'N' characters,
the downsizing of data using random sampling, the limiting of  sequences based from the 
specified timespan (March to April 2021), and the writing of the sampled FASTA file.

Should the user want to sample the dataset with a 
different timespan in mind, modify these information as necessary. 

# MUSCLE Alignment
* Generate the AFA file output:
1. Open Command Prompt in the folder that contains muscle.exe and your input FASTA file
2. Run the command "muscle.exe -in filename1.fasta -out filename2.fasta"
3. Ensure that the process terminates accordingly. MUSCLE will forcefully stop if there is a memory limit exceeded error. Downsize your data for this issue.
4. Upon completion, your AFA file should be in the same folder. 

Note: replace "filename1" with the actual name of your FASTA file from data preprocessing stage, and "filename2" with the desired output name of the AFA file.

# IQ-TREE Building
* Create Environment Variables on Windows
1. Go to Control Panel > System and Security > System.
2. Choose 'Advanced system settings'.
3. Click 'Environment Variables' on the Advanced tab.
4. Highlight the 'Path' under User Variables.
5. Click 'New' to create a new environment variable, or click 'Edit' to modify an existing environment variable.
6. Select 'New' and paste the folder directory where the iqtree-1.6.12-Windows folder is located.
7. Click 'OK' for all tabs.

* Generate the IQ-TREE files:
1. Open Command Prompt in the folder that contains your input AFA file
2. Run the command "iqtree -s filename1.afa -m GTR+F+I+G4 -bb 1000"
3. Upon completion, you should have a set of IQTREE files. More importantly, make sure that these files are complete:
- filename1.afa.log: logs the entire IQ-TREE processes
- filename1.afa.iqtree: contains the IQ-TREE and its details
- filename1.afa.treefile: contains the IQ-TREE in Newick format

Note: replace "filename1" with the actual name of your AFA file from MUSCLE Alignment stage. All the generated files will have this filename as your output by default.

To change the model, simply replace "GTR+F+I+G4" of the command with the substitution model of your choice. 
To change to bootstrapping replicate limit, simply replace "1000" with your desired value.
To ignore ultrafast bootstrap, simply remove the line "-bb 1000" and run the code.

# FIGTREE Visualization
* For Netherlands dataset:
1. Install FigTree: https://github.com/rambaut/figtree/releases/download/v1.4.4/FigTree.v1.4.4.zip
2. Open the zip file, and then open the FigTree application.
3. Go to File > Open, and then choose the Netherlands treefile extension to generate the tree output for the Netherlands dataset.
4. After selecting the treefile, an Input box will pop up prompting the user to select a name for the values. Just click OK.
Optional: For users who want every label to be aligned, select “Align Tip Labels” by clicking its checkbox.

* For Philippines dataset:
1. Install FigTree: https://github.com/rambaut/figtree/releases/download/v1.4.4/FigTree.v1.4.4.zip
2. Open the zip file, and then open the FigTree application.
3. Go to File > Open, and then choose the Philippines treefile extension to generate the tree output for the sampled Philippines dataset.
4. After selecting the treefile, an Input box will pop up prompting the user to select a name for the values. Just click OK.
Optional: For users who want every label to be aligned, select “Align Tip Labels” by clicking its checkbox.

* Coloring Labels
1. Pick "Taxa" as the Selection Mode. 
2. With Taxa, the user can now select the labels one at a time. Pressing down the ctrl button on the keyboard while clicking the labels will give users the ability to select multiple labels. 
3. Once the user has selected the labels they want to color, click "Colour". 
4. Choose a color and then pick OK.

* Arranging Trees Decreasing/Increasing
There are two ways to do this:
1. First Step: After generating the tree, click “Tree” at the top. At the dropdown menu, the user can either choose Increasing Node Order or Decreasing Node Order.
2. Second Step: After generating the tree, click “Trees” at the left sidebar. A dropdown menu will appear - select Order Nodes. Order Nodes has a dropdown box where users can either pick increasing or decreasing.
