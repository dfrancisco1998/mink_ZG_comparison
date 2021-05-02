# Dimension selection algorithm  comparison between Graspologic's ZG and Sklearn's Minka 

The main goal of this project was to compare the implementations of dimension selection algorithms that 
graspologic(using ZG and a ZG hack that looks at only the first log(n) values)  and  sklearn (which uses minka) use. 
This project is useful because it will allow a more accurate quantification of different dimension selection algorithms 
that has not been performed. In doing so, this will illuminate both the strengths and weaknesses of these dimension selection 
algorithms in such a way that will allow the user to decide which is best to use in their particular circumstance. 

# Data
The data comes from [OpenML-CC18](https://www.openml.org/s/99/data). The data is read in within the [notebook](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/2021-04-28-real-data-minka-zg-comparison.ipynb)

# Experiment
In [notebook](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/2021-04-28-real-data-minka-zg-comparison.ipynb), the basic experiment is as follows: 
1. Read in each dataset from [OpenML-CC18](https://www.openml.org/s/99/data)
2. Perform ZG(1), ZG(1) hack, minka, ZG(2), ZG(2) hack, ZG(3), ZG(3) hack, ZG(4), ZG(4) hack dimension selection 
3. Using the original data perform PCA on each dataset, and then do LDA classification per dimension (first the first dim only, then the first and second dim only, etc) 
4. Create plots

# Files
Running the [notebook](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/2021-04-28-real-data-minka-zg-comparison.ipynb )  in order will produce same results and graphs that are in the [manuscript](https://www.overleaf.com/read/mrgdvkxgkzrs). 

I suggest only running through the entire notebook if you wish to create your own data. I have included in this repo many meta data in csv and pickle files 
so that you mayy avoid rerunning all the code which takes a long time(about 3 days). 
  1. survey [results](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/Guess%20the%20elbow-2.csv)
  2. [all_miss](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/all_miss.pkl)
      - this is where the PCA/LDA missclassification rates per dimension per dataset  are stored
  3. [all_ys](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/all_ys.pkl)
      - from reading in the benchmark suite, this is all the classifications per dataset
  4. [dims_ZG3](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/dims_ZG3.pkl)
      - this is the ZG(3) elbow estimations per plot       
  5. [dims_ZG3_hack](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/dims_ZG3_hack.pkl)
      - this is ZG(3) hack elbow estimation
  6. [dims_ZG4](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/dims_ZG4.pkl)
      - this is the ZG(3) elbow estimations per plot
  7. [dims_ZG4_hack](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/dims_ZG4_hack.pkl)
      - this is ZG(3) hack elbow estimation
  8. [dims_ZG_1_all](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/dims_ZG_1_all.pkl)
      - this is the ZG(1) elbow estimations per plot
  9. [dims_ZG_2_all](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/dims_ZG_2_all.pkl)
      - this is the ZG(2) elbow estimations per plot
  10. [dims_ZG_h_1_all](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/dims_ZG_h_1_all.pkl)
      - this is ZG(1) hack elbow estimation
  11. [dims_ZG_h_2_all](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/dims_ZG_h_2_all.pkl)
      - this is ZG(2) hack elbow estimation
  12. [dims_minka_all](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/dims_minka_all.pkl)
      - this is the minka elbow estimations per plot
  13. [surv_dims](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/surv_dims.pkl)
      - this holds the median value(which was the estimation chosen to represent that algorithm per plot) 
      of ZG(1), ZG(1) hack, minka, ZG(2), ZG(2) hack per plot
  14. [true_LDA](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/true_LDA.pkl)
      - this is the median per dataset of the data stored in [all_miss](https://github.com/dfrancisco1998/mink_ZG_comparison/blob/main/all_miss.pkl) 
  
