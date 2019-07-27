## Practice for reading big datasets

In this project, I worked on [California Road Network](https://www.cs.utah.edu/~lifeifei/SpatialDataset.htm) dataset as practice for reading and cleaning big datasets. I created csv files for further analysis, but in this part I only read the datasets and created csv files to make dataset ready for analysis.

In the following link there are 4 different datasets published at total. 

  1. California Road Network's Nodes (Node ID, Longitude, Latitude)
  2. California Road Network's Edges (Edge ID, Start Node ID, End Node ID, L2 Distance)
  3. California's Points of Interest With Original Category Name (Category Name, Longitude, Latitude)
  4. California's Points of Interest (Longitude, Latitude, Category ID)
  5. Merge Points of Interest with Road Network--Map Format For the 5th dataset, map format in detail is:
  
          For each edge:
          Start Node ID, End Node ID, Number of Points on This Edge, Edge Length. 
      
              For each point on this edge: 
              Category ID, Distance of This Point to the Start Node of This Edge  

For the first four datasets, I used ``pd.read_csv()`` command from pandas, but for the last file, I created generators for reading data. With this, my aim was to clean data while reading and also keep memory usage in minimum. I created 3 csv files from the 5th dataset. First file called "nodes_POIs.csv" was for spliting beginning node and related POIs in each line, but this dataset was also needed to be cleaned. So I created second csv as cleaned version of the first one which called "nodes_POIs2.csv". This dataset splits all POIs into different lines with keeping their beggining node as first in line. And as last csv file called "edge_lengths.csv" I only took into account beggining and end nodes of edges and the legth of them and also number of POIs on these edges while creating csv rows.
