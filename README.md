# Riparian_Corridors
This repository contains code from my MRM thesis research. My objective was to understand how development intensity, stream channel morphology, and other landscape features determine how mammalian communities in Squamish and Maple Ridge, British Columbia, use stream, riparian, and matrix habitat types within watersheds.


*NOTE*: Much of this code was developed by Christopher Beirne and the Wildlife Coexistence Lab at the University of British Columbia, and the WildCAM network. I followed their technique from the following manuscript: https://wildcolab.github.io/Introduction-to-Camera-Trap-Data-Management-and-Analysis-in-R/.

The associated documents are explained in detail below:
    
**1) errorChecking.Rmd** - (Chapter 5 and 6 of the manuscript) This script examines the data exported from Wildlife Insights for any errors or abnormailities. This script organizes the dates, checks the date ranges, matches the date ranges with wildlife observations, and maps the study sites. Once the data have been cleaned of errors, taxonomic information is matched for each observation, and the dataset is separated to independent individuals among detections, and condensed to a single observation per event. There are 12 output dataframes from this script: 1) independent detections master dataframe, 2) a daily lookup table of when cameras were active, 3) unique camera trap locations, 4) species list, 5) site x species matrix of the number of independent detections, 6) site x species matrix of species counts, 7) site_month x species matrix of the number of independent detections, 8) site_month x species matrix of species counts, 9) site_week x species matrix of the number of independent detections, 10) site_week x species matrix of species counts, 11) site_day x species matrix of the number of independent detections, and 12) site_day x species matrix of species counts. 

**2) summaryCovariates.Rmd** - This script summarizes the data collected from vegetation surveys over the data collection period. This output was added to the master covariates dataframe. Summaries include mean duff depth, mean tallest woody and herbaceous vegetaion height, mean canopy cover, total DBH by tree species and site, total tree basal area by species and site, dominant tree species, and dominant shrub species. 

**3) pca.Rmd** - This script runs principal component analyses /principal coordinate analyses of various vegetation and habitat characteristic data collected throughout the data collection period. PCA tests were run for terrestrial quadrat surveys, stream quadrat surveys, tree density data, and tree biomass data. A PCoA was run for shrub species data. These results (excluding tree density PCA) are incorporated into the master covariates dataframe.
   
**4) analysisCovariates.Rmd** - (Chapter 7 of the manuscript) This script assembles the remaining covariates that will be brought into the models in later steps. Most of the covariates in this analysis were assembled outside of R as part of the additional data collected in my research. Covariates examined in this script include species traits (home range, body mass, activity patterns, and diet), camera locations (elevation and distance to roadways), and vegetation productivity (NDVI). Finally, all variables are tested for relatedness. 

**5) analysisDataExploration.Rmd** - (Chapter 8 of the manuscript) This script explores the data cleaned and prepared from the errorChecking.Rmd script. This scipt examines how many species were detected among all cameras, which species were the most common, where species detections occurred across cameras, individual species detection distribution across the deployment period, co-occurance of multiple species, and begins to relate species detections to covariates. 
    
**6) communityComposition.Rmd** - (Chapter 9 of the manuscript) This script explores patterns of species richness and metrics of community composition. Species accumulation curves are generated from this code. Shannon and Simpson's diversity indices are also produced. 

**7) HMSC_final.Rmd** - (Chapter 10 of the manuscript) This script generates a joint species distribution model, which explores habitat use trends for the mammalian community we collected data on. This model incorporates environmental predictor variables, species traits data, and species  interactions. This script creates several output plots from this model, including the variance explained by the model and the community and speceies levels, species-level associations to environmental predictor variables, species traits associations to environmental predictor variables, and species interaction associations. Model fit tests are also run in this script. 


    
