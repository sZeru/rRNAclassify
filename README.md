# 16S or 18S rrna classifier
Classifies a nucleotide sequence as either belonging to 16S (prokaryotic) or 18S (eukaryotic) ribosome.
Sequence must be no greater than 2400 nucleotides in length.

## Included Files :

#### SILVA_Parser :
It parses through the SILVA_input file, checking each accession number against NCBI.
Sorts the item as 16S or 18S according to the description recieved.
If it crashes or is exited early, it will pick up where it last left off.

#### FAFSA_Merger :
This merges the FASTA files from both SILVA and NCBI into merged files.

#### Remove_Duplicates :
Run the file to clean the data from FAFSA_Merger, removing duplicates.
It doesn't happen often, but its good practice.

#### Boolean_Formatter :
Formats the files output from Remove_Duplicates into binary for training.

#### Model_Train :
Trains the model using the data provided from Boolean_Formatter. Saves the final weights in the Model file.

#### Model :
The saved model weights after the training run.
