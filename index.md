I research the prediction of river temperature in streams without local observations as a PhD Candidate in Hydrology at Colorado School of Mines working with Dr. Terri Hogue.  To do that, I mainly build new river temperature models, as well as researching efficient quantification of stream thermal regimes.  I have also worked with hydraulic modeling and maintain several HEC-RAS automation tools.

# Research

## Stream Temperature Models

My main research is developing several stream temperature models.  The emphasis is on statistical modeling at the scale of the contiguous United States.

- [TempEst 1](https://github.com/mines-ciroh/tempest1) estimates current/historic stream temperatures without local field data.  It uses a machine learning (random forest) model, trained on the USGS gage network, with publicly-available satellite remote sensing data to estimate monthly mean stream temperatures across the contiguous United States.  [Model description and citation](https://www.sciencedirect.com/science/article/pii/S003442572400289X)
- [TempEst 2](https://github.com/mines-ciroh/tempest2) is essentially a daily-resolution version of TempEst 1, built using an interpretable, geostatistical approach.  It estimates daily mean and maximum temperatures across the CONUS. (Manuscript in review.)

# Software

## Hydraulic Modeling Tools

To support more efficient research on river hydraulics and restorations, I have developed several HEC-RAS automation tools.  They are available as Python packages on the Python Package Index.  In general, these are not under active development, but I will address Issues opened on their GitHub repositories (linked from the PyPI pages) as I have time.

- [Raspy](https://pypi.org/project/raspy-auto/) is a general HEC-RAS automation tool.  It supports setting flow data and roughness coefficients, running (steady-state) models, and retrieving cross-section hydraulic data.  Support was recently added for HEC-RAS 6.x and for retrieving overbank hydraulic data and shear stress.
- [RaspyGeo](https://pypi.org/project/RaspyGeo/) automates geometry modification scenarios in HEC-RAS, including running the model and retrieving hydraulics data.  Geometry scenario functions are simply (cross-section) -> (cross-section) functions, and are able to freely preserve, modify, or replace channel geometry, roughness, and bank stations.  Functions are available to modify cross-section datums in a reach, or part of a reach, by a fixed or linearly interpolated quantity, and it is possible to adjust cross-section datums in a more fine-grained manner through the geometry modifications.  Both broad functions (geometry modification and datum adjustment) can be applied to an entire reach or a range of river stations.  A scenario runner function is provided which applies a dictionary of named geometry scenarios to specified reaches and retrieves main channel and overbank depth, velocity, and shear for each flow profile at specified locations, exported in CSV format. RaspyGeo comes with a few pre-specified geometry modification functions (e.g. adding a trapezoidal low-flow channel), but the user can also write their own, which allows unlimited flexibility.
- [Raspy-Cal](https://pypi.org/project/raspy-cal/) is a HEC-RAS roughness autocalibration tool built on Raspy using a genetic algorithm.
