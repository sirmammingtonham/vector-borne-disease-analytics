# Scraping Unstructured Data to Explore the Relationship between Rainfall Anomalies and Vector-Borne Disease Outbreaks

This repo contains code for [Scraping Unstructured Data to Explore the Relationship between Rainfall Anomalies and Vector-Borne Disease Outbreaks
](https://ieeexplore.ieee.org/abstract/document/9671853) (Joseph, E., Munasinghe, T., Tubbs, H., Bishnoi, B., & Anyamba, A. (2021, December). Scraping Unstructured Data to Explore the Relationship between Rainfall Anomalies and Vector-Borne Disease Outbreaks. In 2021 IEEE International Conference on Big Data (Big Data) (pp. 4156-4164). IEEE.)

## Data

~~CSV formatted final datasets in the `data` folder.~~

Update 7/23: ProMED-mail changed their data policy so I can no longer share the dataset. Please run the code to acquire your own data.

Jupyter notebooks in the `notebooks` folder, mainly used for testing and analysis.

## Usage
If you only want to scrape the data from ProMED-mail, you can run the `scrape_promed.py` script. 
To use this, install the following packages: `requests`, `beautifulsoup4`, and `pandas`.
Then run the following command: `python scrape_promed.py search_term`, and replace search term with what you want to search (i.e. to scrape malaria data, run `python scrape_promed.py 'malaria'`). 
This will extract all articles with that search term and place them in `promed_(search_term).csv`.

To run my data extraction scripts, you need to install all the packages in the `extract_data.py` file. I created an conda `environment.yml` file. If you have conda installed, just run `conda env create -f environment.yml` in the root of this repository. *Note, you will need nvidia cuda installed.* 

However, `extract_data.py` will require the full combined dataset that I created in one of the jupyter notebooks in the notebook folder. It might be easier to use if you just export the functions and use them in your own code/data extraction pipeline.

Feel free to open up an issue if you are struggling with usage.

## Citation
```
@INPROCEEDINGS{9671853,
  author={Joseph, Ethan and Munasinghe, Thilanka and Tubbs, Heidi and Bishnoi, Bhaskar and Anyamba, Assaf},
  booktitle={2021 IEEE International Conference on Big Data (Big Data)}, 
  title={Scraping Unstructured Data to Explore the Relationship between Rainfall Anomalies and Vector-Borne Disease Outbreaks}, 
  year={2021},
  volume={},
  number={},
  pages={4156-4164},
  abstract={According to the World Health Organization (WHO), vector-borne diseases such as malaria and dengue account for 17% of all infectious disease cases and lead to more than 700,000 deaths per year. Tracking and predicting the spread of vector-borne diseases is a vital task that could save hundreds of thousands of lives annually. Oftentimes, the first reports of vector-borne disease outbreaks occur through emails and online reporting systems long before they are officially documented. Tracking and predicting the emergence and spread of vector-borne disease outbreaks requires extracting data from these unstructured sources in combination with historical weather and climate data to understand the underlying background triggers and disease dynamics. In this work, we develop a data extraction pipeline for the online outbreak reporting website ProMED-mail that utilizes a web scraper, transformer neural network summarizer, and named entity recognizer to obtain a dataset of malaria, dengue, zika, and chikungunya outbreaks over the last 30 years. This scraped dataset was further analyzed in association with global rainfall anomalies derived from NASA’s Integrated Multi-satellitE Retrievals for GPM [Global Precipitation Mission] (IMERG) dataset. This preliminary analysis was to understand the effect of global rainfall patterns on the spread of vector-borne diseases. Analysis of the ProMED-mail and GPM data shows that vector-borne disease outbreaks are clustered towards the tropics and outbreaks are often amplified during the rainy seasons. Our scraped dataset can be a valuable tool in creating comprehensive georeferenced disease records for modeling and predicting future outbreaks.},
  keywords={},
  doi={10.1109/BigData52589.2021.9671853},
  ISSN={},
  month={Dec},}
```
