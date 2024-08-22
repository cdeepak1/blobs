# Project Portfolio

This repository is our submission for the module **12-GEO-M-DS02 Spatio-temporal Data** by Dr. Guido Kraemer.


**The repository contains:**

- extreme_events_documentation.ipynb: main document, will be rendered in the pipeline as html file
- extreme_events_documentation.html: rendered output of extreme_events_documentation.ipynb
- src:
  - 01_create_core_area_mask.ipynb, src/02_compute_ecosystem_response.ipynb and src/03_analysis.ipynb: the jupyter notebooks with our code for creating the masks, computing ecosystem responses and the analysis
- data:
  - fluxcom_preprocessed_corearea.csv and data/gleam_preprocessed_corearea.csv: the files that are created in 01_create_core_area_mask.ipynb and used as input in the other notebooks 
  - masks.zip: zipped data that is created in 01_create_core_area_mask.ipynb and is used as input in the other notebooks
- quarto:
  - _quarto.yml: configuration file
- conda:
  - environment.yml: dependencies
- .gitlab-ci.yml:
  - it executes and builds everything on the server `quarto render extreme_events_documentation.ipynb`
  - the `extreme_events_documentation.html` will be generated automatically after running the pipeline-job manually



## Short Project Description

### The influence of compound heat and drought extreme events on ecosystem response variables

#### Question

As ecosystem response variables we chose Gross Primary Productivity (GPP), Total Ecosystem Respiration (TER) and Evaporative Stress (EvS). Ecosystem responses are influenced by various environmental factors. 
Gross primary productivity (GPP), the largest flux in the global carbon budget (Friedlingstein et al., 2019), is mainly influenced by air temperature and precipitation. These environmental factors strongly affect the spatial variation of GPP (Zhu et al. 2016). Higher temperatures and more precipitation typically lead to a higher GPP. However, heat waves slightly decrease GPP and droughts largely decrease GPP (Zscheischler et al. 2014). 
Higher temperatures and moisture usually lead to a higher total ecosystem respiration (TER). Heat waves increase TER, while droughts decrease TER (Zscheischler et al. 2014).
Environmental factors such as a lack of available soil water, decrease in biomass, and extreme temperatures can decrease the potential evaporation.
The evaporation stress factor (S) accounts for these effects, with zero indicating maximum evaporative stress (EvS) and one indicating no stress (Miralles et al. 2011).

Global extreme events have been on an increasing trend. The percentage of the global land area experiencing extreme temperatures is rising. S. E. Perkins et al. (2020) note an increase in the trends of duration of heat waves, particularly in South America, Africa, the Middle East, and Southwest Asia.
Since climate variables like temperature and precipitation influence different ecosystem responses, (extreme) changes in these variables also lead to changing responses. Changes in these responses can affect ecosystem functions and services.

This leads to the question we want to answer in this project:

**How do different ecosystem variables respond to extreme events with different area, duration and severity on a global scale?**


#### Data

There is a summary table for all extreme events that have been detected in the DeepExtremes project (https://s3.bgc-jena.mpg.de:9000/deepextremes/v3/MergedEventStats_landonly.csv). 

As input data for the ecosystem response variables we use the FLUXCOM and GLEAM data sets from the Earth System Data Cube (https://deepesdl.readthedocs.io/en/latest/datasets/ESDC/). 


## Getting started (locally)

To run this analysis you need to have python installed.

To clone this project, navigate to your directory and run the following command:
```bash
  git clone https://git.sc.uni-leipzig.de/ss2024-12-geo-m-ds02/blobs.git
```

Change your directory to the pulled project:
```bash
  cd blobs/
```

If you want to reproduce the full analysis you can re-create our conda-environment with this command:
```bash
  conda env create --file environment.yml
```

---
**Hint**

In the environment.yml file please adjust the prefix according to your folder structure.

From 
```yml
  prefix: /home/jasminkrebs/.conda/envs/blobs
```
To
```yml
  prefix: <your-desired-path>
```

---

You can render the .ipynb file locally (after installing quarto and cloning the repo) as follows:
```bash
  quarto render extreme_events_documentation.ipynb
```

### Getting started (pipeline)

Alternatively just use the pipeline (you need to start it manually, please run the job).

## References

[Miralles, D. Gonzalez, et al. "Global land-surface evaporation estimated from satellite-based observations." Hydrology and Earth System Sciences 15.2 (2011): 453-469.](doi.org/10.5194/hess-15-453-2011)

[Perkins-Kirkpatrick, S. E., and S. C. Lewis. "Increasing trends in regional heatwaves." Nature communications 11.1 (2020): 3357.](doi.org/10.1038/s41467-020-16970-7) 

[Zhu, Xian-Jin, et al. "Approaches of climate factors affecting the spatial variation of annual gross primary productivity among terrestrial ecosystems in China." Ecological Indicators 62 (2016): 174-181.](doi.org/10.1016/j.ecolind.2015.11.028)

[Zscheischler, Jakob, et al. "Impact of large‐scale climate extremes on biospheric carbon fluxes: An intercomparison based on MsTMIP data." Global Biogeochemical Cycles 28.6 (2014): 585-600.](doi.org/10.1002/2014GB004826)

## Acknowledgments

We would like to thank Mélanie Weynants from the Max-Planck-Institute for Biogeochemistry (Jena) to help us get access to the DeepExtreme data that we needed.

## Authors

- Georg Brandt (3750881)
- Chinthaparthy Deepak Reddy (3793056)
- Jasmin Krebs (3721364)
