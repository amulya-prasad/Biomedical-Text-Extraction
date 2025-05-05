
# Biomedical Text Extraction

PubMed is a vast repository of medical research papers that provides API access to an extensive wealth of data. This treasure trove of information can be harnessed to construct knowledge graphs for applications such as healthbots and recommender systems. However, an inherent challenge lies in effectively sorting and analyzing these papers: while some journals boast high impact factors, others may not meet the same standards. Addressing this, the current project serves as a proof of concept, showcasing a comprehensive approach that combines advanced methods for scoring, extracting, and analyzing high-quality papers.

The project begins by scraping PubMed data, extracting the journal impact factor and university research scores through different API services. Once the data is collated in a tabular format, data analysis has been performed to understand the underlying distribution and idenitify the correlation between the parameters. Further,  an unsupervised learning-based scoring system has been introduced to rank papers based on features such as journal impact factors and university research scores. Finally after scoring, top tier articles have been extracted for constructing Knowledge Graphs. Using BERN2,  Named Entity Recognition (NER) is performed to identify critical biomedical entities . Further to identify the relationships between these entities LLama 3.1 was used. This extracted information forms the foundation for constructing sophisticated knowledge graphs, enabling enhanced insights and explainability.

While this project lays the groundwork for these capabilities, it is merely a starting point. With the rapid advancements in Large Language Models (LLMs) and other AI technologies, numerous improvements can be envisioned. These include refining entity extraction, enhancing relationship modeling, and integrating more dynamic scoring methods, ultimately expanding the potential applications and impact of this system in real-world scenarios.

## Problem Overview

The sorting of papers is based on various features such as:
- Citation count
- Impact factor of the journal
- Research score of the university
- Study type

Due to limitations in web scraping, only the impact factor and research score of universities could be scraped. In this project:
- Data scraping is achieved for impact factors and research scores from different sources.
- The extracted data is merged into a single dataframe.
- GLiner transformer is used to extract entities like universities and study types.

## Key Features

- **Data Extraction**: Extract PubMed data and append impact factors and research scores of different universities.
- **Data Visualization**: Perform exploratory data analysis to understand correlations between various categories.
- **Feature Importance**: Identify and weigh critical features to rank high-quality papers effectively.
- **Entity and Relationship Extraction**: Use Large Language Models (LLMs) such as Llama 3.1 to extract entities and relationships from text and build knowledge graphs.
- **Knowledge Graphs**: Populate data into Neo4j, enabling explainable insights and chatbot functionality for healthcare providers.

## Structure

The repository is organized as follows:

- `pubmed/` - Main directory containing PubMed data processing resources.
  - `notebooks/` - Jupyter notebooks with detailed examples and use cases.
  - `csv/` - Sample CSV files for testing and demonstration purposes.
- `README.md` - Project documentation (you are here!).
- `.gitignore` - Specifies files and directories to ignore in the repository.

## Pipeline Overview

1. **Data Extraction**:
   - Extract data from PubMed.
   - Append impact factor and research scores of universities.
2. **Data Visualization**:
   - Analyze correlations between different categories.
3. **Feature Importance**:
   - Determine and weigh critical features to filter high-quality papers.
4. **Entity and Relationship Extraction**:
   - Utilize BERN2 to extract entities and LLama 3.1 to identify the relationships.
   - Build knowledge graphs using Neo4j.
5. **Chatbot Integration**:
   - Use knowledge graphs to power a chatbot for healthcare providers, offering insights and explainability.


### Hosted Notebook on nbviewer

You can view the exploratory data analysis on nbviewer: [Pubmed_EDA_part2.ipynb](https://nbviewer.org/github/amulya-incorrigible/Biomedical-Text-Extraction/blob/main/pubmed/Notebooks/Pubmed_EDA_part2.ipynb)


To understand the project in detail please refer to this medium blog : https://medium.com/@fhirshotlearning/harnessing-pubmed-a-deep-dive-in-medical-knowledge-extraction-powered-by-llms-4e895b4f0839

