I research the prediction of river temperature in streams without local observations as a PhD Candidate in Hydrology at Colorado School of Mines working with Dr. Terri Hogue.  To do that, I mainly build new river temperature models, as well as researching efficient quantification of stream thermal regimes.  I have also worked with hydraulic modeling and maintain several HEC-RAS automation tools.

# Research

## Stream Temperature Models

My main research is developing several stream temperature models.  The emphasis is on statistical modeling at the scale of the contiguous United States.

- [TempEst 1](https://github.com/mines-ciroh/tempest1) estimates current/historic stream temperatures without local field data.  It uses a machine learning (random forest) model, trained on the USGS gage network, with publicly-available satellite remote sensing data to estimate monthly mean stream temperatures across the contiguous United States.  [Model description and citation](https://www.sciencedirect.com/science/article/pii/S003442572400289X)
- [TempEst 2](https://github.com/mines-ciroh/tempest2) is essentially a daily-resolution version of TempEst 1, built using an interpretable, geostatistical approach.  It estimates daily mean and maximum temperatures across the CONUS. (Manuscript in review.)  TempEst 2 implements what could be called a "regime-oriented" approach, where it estimates the quantitative thermal regime of the stream (seasonal variation and weather sensitivity), then applies that to actual weather data.  This approach is called SCHEMA, or "Seasonal Conditions Historical Estimation with Modeled daily Anomaly".

## Stream Thermal Regime

Modeling stream temperature through application of a stream thermal regime requires studying the stream thermal regime.  In particular, TempEst 2's SCHEMA approach depends on having a high-accuracy quantification of the seasonal thermal regime through an annual temperature cycle function.  That is the subject of ["Improved annual temperature cycle function for stream seasonal thermal regimes"](https://doi.org/10.1111/1752-1688.13228), which introduces the "three-sine function" for accurately quantifying stream seasonal thermal regimes across diverse environments such as mountain and desert streams.  Three-sine seasonal thermal regimes can be automatically fitted to temperature data using the [rtseason](https://pypi.org/project/rtseason/) Python package.

# Software

All of the software I have developed, below, is free and open-source under the terms of the GNU General Public License (GPL) v3.  Briefly, you are free to reuse, modify, and redistribute the software and source code, as long as any derivatives are also released under the GPL.

## Stream Temperature Models

All stream temperature models below provide a straightforward implementation (e.g., one function called with an input data frame) and come with a pre-trained model in some form and an automated data retrieval process.

- [TempEst 1](https://github.com/mines-ciroh/tempest1): monthly mean stream temperatures.  Implementation provided as R source code with data retrieval in Google Earth Engine.  I will consider a Python implementation and non-GEE data retrieval upon request and as time allows.
- [TempEst 2](https://github.com/mines-ciroh/TempEst2): daily mean and maximum stream temperatures.  Implementation provided as R source code with data retrieval in Google Earth Engine.  I will consider a Python implementation and non-GEE data retrieval upon request and as time allows.

## Stream Temperature Analysis Tools

- [rtseason](https://pypi.org/project/rtseason/) automatically computes three-sine function coefficients for the seasonal thermal regime from daily stream temperature data.  Implementation provided on the Python Package Index (`pip`) and as Python and R source code, though the R version is not actively maintained and lacks some functionality improvements.

## Hydraulic Modeling Tools

To support more efficient research on river hydraulics and restorations, I have developed several HEC-RAS automation tools.  They are available as Python packages on the Python Package Index.  In general, these are not under active development, but I will address Issues opened on their GitHub repositories (linked from the PyPI pages) as I have the time.

- [Raspy](https://pypi.org/project/raspy-auto/) is a general HEC-RAS automation tool.  It supports setting flow data and roughness coefficients, running (steady-state) models, and retrieving cross-section hydraulic data.  Support was recently added for HEC-RAS 6.x and for retrieving overbank hydraulic data and shear stress.
- [RaspyGeo](https://pypi.org/project/RaspyGeo/) automates geometry modification scenarios in HEC-RAS, including running the model and retrieving hydraulics data.  Geometry scenario functions are simply (cross-section) -> (cross-section) functions, and are able to freely preserve, modify, or replace channel geometry, roughness, and bank stations.  Functions are available to modify cross-section datums in a reach, or part of a reach, by a fixed or linearly interpolated quantity, and it is possible to adjust cross-section datums in a more fine-grained manner through the geometry modifications.  Both broad functions (geometry modification and datum adjustment) can be applied to an entire reach or a range of river stations.  A scenario runner function is provided which applies a dictionary of named geometry scenarios to specified reaches and retrieves main channel and overbank depth, velocity, and shear for each flow profile at specified locations, exported in CSV format. RaspyGeo comes with a few pre-specified geometry modification functions (e.g. adding a trapezoidal low-flow channel), but the user can also write their own, which allows unlimited flexibility.
- [Raspy-Cal](https://pypi.org/project/raspy-cal/) is a HEC-RAS roughness autocalibration tool built on Raspy using a genetic algorithm.  It can be used through the command line or a graphical user interface, and supports automatic retrieval of calibration data from a USGS gage.
