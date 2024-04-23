# Illinois Tech Info Finder

The project aims to develop an efficient search engine for the Illinois Institute Of Technology at Chicago using various Information Retrieval techniques and algorithms.

The construction of this search engine involves seven primary operations:

1) Data Collection - Crawling and Indexing
2) Data Preprocessing - Text Cleaning
3) Building Web Graph
4) Ranking Pages - PageRank Algorithm
5) Build Vector Space Model
6) Cosine Similarity - Indexed Pages and User Query
7) Get Search Results

These steps are elaborated below. The objective is to create a lightweight yet effective search engine. Ensure all libraries mentioned in the `requirements.txt` file are available.

## Build Locally

The user interface, powered by Flask, is hosted on localhost.

```
python search_engine_web_app.py
```

This command sets up the user interface, allowing users to input queries and receive results.


### Data Collection - Crawling and Indexing

Begin by creating a database of indexed pages within the `IIT` domain. Approximately 5000 pages will be crawled, and text will be extracted from them.


python engine.py --initial_url https://www.iit.edu/ \
                 --number_of_pages 5000 \s
                 --domain iit.edu


The command initiates crawling from the specified initial URL, indexing the desired number of pages within the specified domain. Data from each URL is stored in the `./documents` directory.

### Data Preprocessing - Text Cleaning

Extract text from webpages and perform preprocessing. Text is extracted from the `<body>` tag and cleaned.

### Building Web Graph

Record outgoing links from `<a>` anchor tags during crawling to create a web graph.

### Ranking Pages - PageRank Algorithm

Calculate page rank scores for each page using the PageRank algorithm.

python web_graph.py


This command generates page rank scores for each URL and stores them in the `./web_page_ranks` directory.

### Build Vector Space Model

Create a vector space model using the inverted index and TF-IDF scheme.

python build_inverted_index.py


This command generates TF-IDF files for the web graph in the `./tf_idf_files` directory.

### Cosine Similarity - Indexed Pages and User Query

Retrieve the top webpages using Cosine Similarity based on the user's query from the Vector Space Model.

### Get Search Results 

Set up the user interface using Flask.

python search_engine_web_app.py

This command initializes the UI, allowing users to enter queries and receive search results.

Sample Queries:
Admissions
Research

These steps collectively form the architecture of the Illinois Tech Info Finder, facilitating efficient information retrieval within the Illinois Institute Of Technology at Chicago domain.