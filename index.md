I am a PhD student in Hydrology at Colorado School of Mines working with Dr. Terri Hogue.  My research is in river temperature modeling and hydraulic modeling for river restoration.  I am also an enrolled Engineer Intern in Colorado (civil engineering).

# Research

## Stream Temperature: PhD - NOAA National Water Model

For my PhD research beginning in the spring, I am working on developing and applying a stream temperature module for NOAA's NWM.  We hope to implement this as a stand-alone model as well.

## Stream Temperature: MS Thesis

My thesis research focused on analysis and prediction of river temperatures at high resolution.  As most smaller reaches in the contiguous United States do not have temperature monitoring, despite many extensive gauge networks, the first part of my work was the development of [TempEst](https://github.com/river-tempest/tempest), a machine learning model for estimating monthly mean stream temperatures at a point using only remotely-sensed data.  TempEst is trained on the USGS gage network, but is able to estimate the temperature of ungaged locations (based on a validation dataset) with high accuracy (a median Root Mean Square Error of 1.7 C) and is well-suited to large-scale analyses.

Building on TempEst, I developed another model, LOST, to model longitudinal stream temperature profiles based on land cover conditions, again using only remotely-sensed data.  LOST is particularly useful for sensitivity analyses, quickly running large numbers of scenarios, and rivers where field data are sparse.  Over testing reaches typically on the order of tens of kilometers in length, LOST introduces a median RMSE of about 1.2 C.

## Los Angeles River Hydraulics

Since June 2019, I have worked on the [Los Angeles River Environmental Flows Project](https://www.sccwrp.org/about/research-areas/ecohydrology/los-angeles-river-flows-project/), primarily as a hydraulic modeler.  The project's original goal was to investigate the impacts of increased wastewater recycling on ecology and recreational uses in the Los Angeles River, which, in the dry season, is mostly wastewater.  We are now working on restoration scenarios to mitigate the impact of wastewater recycling and other flow changes.  For the project, I assembled a HEC-RAS model from existing partial models and LIDAR data, calibrated the model, and used the model as well as a suite of utility scripts I developed to efficiently analyze a large range of hydrologic and hydraulic scenarios.  As a spinoff project, I developed an automatic calibration utility for HEC-RAS, [Raspy-Cal](https://raspy-cal.dphilippus.com/).

## Selected Publications & Conferences

* [Raspy-Cal: A Genetic Algorithm-Based Automatic Calibration Tool for HEC-RAS Hydraulic Models](https://www.mdpi.com/2073-4441/13/21/3061) (Philippus, Wolfand, Abdi, and Hogue, 2021; DOI:10.3390/w13213061) describes the implementation of the HEC-RAS automatic calibration utility I developed and a case study with it.  I also presented on this at the AGU Fall Meeting 2020 in an eLightning format.
* I presented a poster on TempEst at the AGU Frontiers in Hydrology Meeting in 2022.
* I gave an oral presentation on LOST and preliminary sensitivity results at the AWRA Annual Conference in 2022.

# Background & Education

My master's degree coursework focused on modeling, applied mathematics and field methods; I intend to use my remaining PhD coursework to develop a background in water policy and economics.  My undergraduate education, also at Colorado School of Mines, was in Civil Engineering, with specialized coursework on water resources, geotechnical engineering, and surveying.  In addition to my research with the Hogue Group, which I began after my sophomore year, I interned at Kilduff Underground Engineering, primarily as a geotechnical monitoring survey technician, though I also ran pipe jacking load calculations for trenchless tunneling projects.

## Specialized Coursework

* Modeling and computation:
  * Watershed Modeling
  * Advanced Machine Learning
  * Numerical Solutions to Partial Differential Equations
  * Spatial Statistics
* Other graduate-level:
  * Field Methods in Hydrology
  * Hydrometeorology
  * Unsaturated Soil Mechanics (with a focus on hydraulics)
* Undergraduate-level (civil engineering):
  * Advanced Surveying & Infrastructure Design
  * Onsite Wastewater Reuse
  * Mathematical Geophysics

# Skills

I have professional experience with machine learning and data analysis, hydraulic modeling, software development (particularly for data processing automation), GIS and remote sensing, and surveying, and am particularly familiar with HEC-RAS, R, Python, ArcMap (including ArcPy), and Google Earth Engine.  I also have course-related lab experience with river gaging, distributed temperature sensing, infiltration tests, geophysical surveys, MODFLOW, Hydrus, AutoCAD Civil3D, and HEC-HMS, and with implementing numerical models.

# Links

* [LinkedIn](https://www.linkedin.com/in/daniel-philippus/)
* [TempEst (stream temperature estimator)](https://github.com/river-tempest/tempest)
* [Raspy-Cal (HEC-RAS calibrator)](https://raspy-cal.dphilippus.com)

# Miscellaneous

* Engineer Intern in Colorado
* Associate Member, ASCE
