# Propagation-of-Epidemics-in-Citation-Networks

This project was done as a part of the course requirement of CS 8803 : Data Science for Epidemiology (Fall 2020).
There are two folders in this package. The DOC folder contains a report and a presentation for the  project. The SRC folder is composed of a code and data folder. 

The codes of this project are written in Python3. The packages needed to run this project can be installed by running ```pip3 install -r requirements.txt``` on the ```requirements.txt``` file in SRC. 

1. **Preparing Prestige Data**: 

The raw CSV files for US News Rankings, CS Rankings and the faculty-hiring drive prestige are in ```data\prestige\```. The notebook ```prestige_calculation.ipynb``` contians code to compute prestige scores for all universties and can be run to do so. The resulting dataframe is pickled and stored for convenience in ```data\prestige\``` as ```prestige_data.pkl```. 

2. **Preparing Idea Quality Data**:

ICLR data is stored in ```\data\mag_papers\iclr.json```. The script to process these and get the papers that match the ones in our MAG data is ```code\python_scripts\iclr_matches.py```. The matched papers are pickled and stored for convenience in ```data\paper_quality\iclr_matched_papers.pkl```. The metadata for each paper of ICLR 2018 is stored in ```data\paper_quality\iclr2018_metadata.jsonl``` as a jsonlines file.

3. **Collecting and process MAG data**: 

We got our data from the Microsoft Academic Graph. One can read more about how to use their API from here : https://docs.microsoft.com/en-us/academic-services/project-academic-knowledge. The script to collect data is in the script ```query_mag.py```. The current parameters passed in the MAG query are to fetch conference papers post 2017 for the conferences ACL, ICCV, CVPR, ICLR, ICML, NAACL, NEURIPS. These can be changed as needed. When this script is run, the necessary data files will get collected in ```data\paper_data_mag```. Each ```.json``` file will be of the form ```MAG_conference_name.json```. These files are too big to be stored in github and hence will have to scraped. These files are then futher used to create the citation and infection networks. The notebook ```code\citation_network_dk.ipynb``` contains code to aggregate the data for all the conferecnes and collect it in a dataframe. Running this notebook will store the pickled version of this dataframe is in ```data\all_paper_data.pkl```. This file is too big to be stored in github and will have to be generated by runnin the code. 

4. **Creating the citation and infection network**:

The code to create the citation network and its infection network are in ```prestige_calculation.ipynb```. These have been pickled and stored in ```\data\networks\citation_network.pkl``` and ```\data\networks\citation_infection_network```. 
 
5. **Creating the patient zero paper data**:

The notebook ```code\patient_zero.ipynb``` contains code to process, aggregate and  visualise data for the infection sources and can be run to do so. The resultign dataframe is pickled and stored in ```\data\patient_zero_data.pkl```.

6. **Visualzing Netowrk Topology:**



7. **Simulating Epidemics**
