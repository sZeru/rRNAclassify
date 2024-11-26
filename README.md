# 16S or 18S rrna classifier
Classifies a nucleotide sequence as either belonging to 16S (prokaryotic) or 18S (eukaryotic) ribosome.


## Included Files :

#### NCBI_Scraper :
Queries NCBI via Entrez API to obtain testing data for our model.
Saves it into the two files depending on its label: ncbi_16s and ncbi_18s.

#### SILVA_Parser :
It parses through the SILVA_input file, checking each accession number against NCBI.
Sorts the item as 16S or 18S according to the description recieved.
If it crashes or is exited early, it will pick up where it last left off.

#### Remove_Duplicates :
Run the file to clean the data from SILVA_Parser.
Duplicates can occur especially if it was exited partway through the process.
This data is used to train the model. NCBI is used for testing.

#### Model_Train :
Trains the model using the data provided in the directory. Saves the final weights in the Model file.

#### Model :
The saved model weights after the training run. Used in Model_Inference

#### Model_Inference :
Provide a nucleotide sequence, will use the weights from the Model file to classify it as either 16S or 18S rrna.