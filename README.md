# House of Commons Question Analysis Project

This project analyzes parliamentary questions asked by Members of Parliament (MPs) in the UK House of Commons, focusing on identifying patterns in geographical references and exploring regional variations in topics discussed. The analysis uses data from the House of Commons SPARQL endpoint and supplements it with data from Wikidata. The results aim to provide insights into the degree to which MPs refer to their constituencies and regional trends in question topics.

## Project Overview

This project was completed as part of a computational modeling course focused on applications in the Humanities and Social Sciences. Key goals were to:

1. **Analyze MP References to Constituencies**: Identify the extent to which MPs refer to their own constituency or locations within it when asking questions, using Named Entity Recognition (NER) to detect geographical references.
2. **Identify Regional Topic Patterns**: Apply Latent Dirichlet Allocation (LDA) topic modeling to detect regional trends in question topics and investigate potential geographical influences on parliamentary interests.

## Data Sources and Collection

- **House of Commons SPARQL Endpoint**: Used to extract structured data on parliamentary questions from 1 January 2023 to 30 September 2023, including the MP’s identity, question text, and date.
- **Wikidata API**: Supplemented data to match geographical references with constituency information for accurate analysis of constituency-specific questions.

Data collection involved formulating SPARQL queries to gather relevant data points, with additional data cleaning and transformation steps to prepare text data for analysis.

## Technology Stack and Tools

- **Python 3.x**: Primary programming language, chosen for its robust libraries and SPARQL integration capabilities.
- **SPARQL & Wikidata APIs**: To access structured data from parliamentary sources and Wikidata.
- **NLTK and spaCy**: For natural language processing, specifically in Named Entity Recognition (NER) to detect geographical entities within question texts.
- **scikit-learn & Gensim**: Libraries used for topic modeling, specifically implementing LDA to detect thematic patterns in question data.
- **Matplotlib & Seaborn**: For visualizing data patterns and presenting regional differences effectively.

## Implementation

### 1. Constituency Reference Analysis
   - **Named Entity Recognition (NER)**: Implemented NER to extract geographical references from question texts, detecting place names or specific landmarks.
   - **Constituency Matching**: Used Wikidata’s administrative territorial properties (P131) to verify if detected locations align with the MP’s constituency. This step involved mapping locations to specific constituency boundaries and calculating accuracy estimates for the chosen approach.

### 2. Regional Topic Analysis Using LDA
   - **Data Aggregation**: Grouped questions by larger regional divisions (e.g., North England, Southeast England, Scotland) to enable comparative analysis across broad areas.
   - **LDA Topic Modeling**: Applied Latent Dirichlet Allocation to cluster questions into thematic topics, then analyzed these topics for notable trends or variations across regions.
   - **Assumption Analysis**: Evaluated assumptions made in regional classification and topic modeling, acknowledging limitations such as potential biases and data sparsity in certain areas.

## Key Findings

- **Constituency References**: A significant proportion of MPs included references to their constituencies in questions, indicating localized representation.
- **Regional Topic Patterns**: The LDA model revealed that MPs from different regions tended to focus on distinct topics; for example, MPs from Northern regions frequently raised issues related to industrial development, while MPs from the Southeast often addressed economic and infrastructure topics.

## Critical Evaluation

- **Modeling Accuracy**: While the constituency matching algorithm effectively matched many geographical entities to constituencies, some locations resulted in false negatives. Acknowledging these limitations, we estimated the reliability of NER and constituency matching at approximately 85%.
- **Regional Biases**: Topic modeling assumes uniformity in question length and topic representation across regions, potentially skewing results in regions with fewer data points.
- **External Comparisons**: Compared findings to existing research on regional political interests to validate observed patterns, finding alignment in most cases (e.g., industrial focus in Northern England).

## How to Run the Code

1. **Setup**: Clone the repository and ensure Python 3.x is installed with necessary packages (`nltk`, `spaCy`, `gensim`, `matplotlib`, etc.).
2. **Run SPARQL Queries**: Use provided SPARQL queries to retrieve House of Commons question data and save it in the required format.
3. **Run Analysis**:
   - Execute the constituency analysis script (`constituency_analysis.py`) to identify references to MP constituencies.
   - Execute the topic modeling script (`lda_topic_modeling.py`) to generate LDA models and analyze regional topic trends.
4. **Visualize Results**: Visualizations are automatically saved to the `output/` directory as `.png` files for inclusion in the final report.

## Conclusion

This project demonstrates a range of skills in computational modeling, natural language processing, and data visualization, providing valuable insights into how MPs use parliamentary questions to represent their constituencies and highlighting regional trends in political topics. This analysis could be extended to track evolving political interests over time or to assess other legislative bodies.

