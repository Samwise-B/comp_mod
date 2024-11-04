# Computational Modelling: LDA Topic Analysis of Questions asked in the House of Commons

This project involved collecting data from various sources to present a research paper regarding the types of questions asking in the house of common's and the distribution of topics over the various constituencies around the UK.

It involved gathering question data from the Parliament SPARQL API for all available years and combining the data with enities originating in the UK stored in the Wiki Query Service.
The goal of the research paper was two-fold:
1. Analyse fuzzy references to places, objects and people in the UK and visualize this data according to consituency/regional breakdowns using QGIS.
2. Use Latent Dirichlet Allocation (LDA) Topic modelling to determine the distribution of topics for questions asked over various years by region.

The project required maticulous scrutiny to access the validatity of the results due to the imperfect nature of the model as the data was an aggregation of varying sources of truth (Wiki & Parliament API).
