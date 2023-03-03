# VLDB-2023
Spatio-temporal flow patterns

Chrysanthi Kosyfaki, PhD Candidate, University of Ioannina, Greece

Instructions for compiling and running the code
1. To use the code, you will need two files: - a trips table and a neighborhood graph: <br/>
The trips table has the following format: <br/>
  src dest timeslot flow <br/>
The neighborhood graph has the following format:<br/>
 neigh1 neigh2<br/>

2. To execute the basic code for finding the total number of patterns and time of execution, we run the following command: <br/>
        ```python3 findpatterns.py <neighborhood_graph> <trips_table> <support for atomic patterns> <support for extended patterns> <timebound>``` <br/>
  
        Example: python3 findpatterns.py adj_taxi.txt flows.txt 0.001 0.5 100000 - we don't bound the time dimension here <br/>
  
  - For the time breakdown experiment, we run the following command: <br/>
       python3 findpatterns-timebreakdown.py adj_taxi.txt flows.txt 0.001 0.5 100000
  
  - For the ranking experiment, we run the following command: <br/>
      default values: s_a=0.1, s_r=0.3, k=30, level=3000, timebound=100000 <br/>
      ```python3 findpatterns-ranking.py <neighborhood_graph> <trips_table> <support for atomic patterns> <support for extended patterns> <timebound> <k> <max-level>``` <br/>
      
        Example (for different levels - we use the default values): python3 findpatterns-ranking.py adj_taxi.txt flows.txt 0.1 0.3 10000 3000 10
        Example (for different k - we use the default values): python3 findpatterns-ranking.py adj_taxi.txt flows.txt 0.1 0.3 10000 1000 30
        
 - For the bounded experiment, we run the following command: <br/>
      default values (for taxi network): origin=6, destination=6, time=6 <br/>
      ```python3 findpatterns-bounded.py <neighborhood_graph> <trips_table> <support for atomic patterns> <support for extended patterns> <timebound> <src> <dest>``` <br/>
        
       Example (for different origins - we use the default values): python3 findpatterns-bounded.py adj_taxi.txt flows.txt 0.001 0.5 6 2 6
       
- For the use-cse experiment, we run the following command: <br/>    
    ```python3 findpatterns-bounded.py <neighborhood_graph> <trips_table> <support for atomic patterns> <support for extended patterns> <timebound> <query-file>```
       

 


