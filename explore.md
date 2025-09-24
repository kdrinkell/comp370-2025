1) How big is the dataset?
	
The number of rows (including the header) of the dataset is 36860 and the file size is 4.7MB.

wc -l clean_dialog.csv

ls -lh clean_dialog.csv

2) What’s the structure of the data? (i.e., what are the fields and what are values in them)

The data is split into 4 columns; title, writer, dialog, and pony. The title column contains the name of the episode and the writer column contains the name of the writer of the episode. The dialog column contains the quote said in the episode, and the pony column contains the name of the pony who says the quote.

head -n 1 clean_dialog.csv

csvtool col 1 clean_dialog.csv | head
csvtool col 2 clean_dialog.csv | head
csvtool col 3 clean_dialog.csv | head
csvtool col 4 clean_dialog.csv | head

3) How many episodes does it cover?

The dataset covers 197 different episodes. 

csvtool col 1 clean_dialog.csv | tail -n +2 | sort -u | wc -l

4) During the exploration phase, find at least one aspect of the dataset that is unexpected – meaning that it seems like it could create issues for later analysis.

During the exploration of different episode titles, using the command, csvtool col 1 clean_dialog.csv | tail -n +2 | sort -u | nl, it listed all the unique episode titles. Upon inspecting these names, I came across a title called "My Little Pony The Movie". This technically may not count as an episode; therefore the runtime of the content may be longer, causing there to be more dialogue from this "episode". This could potentially skew our data analysis. 
