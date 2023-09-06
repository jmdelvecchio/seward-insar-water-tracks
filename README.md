**Hillslope-Channel Transitions and the Role of Water Tracks in a Changing Permafrost Landscape**

Joanmarie Del Vecchio, Simon Zwieback, Joel Rowland, Roman DiBiase, Marisa Palucis

[Now available in JGR: Earth Surface!](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2023JF007156)

# Where's the data??
If you don't want to run this notebook, the `basin_means.csv` file is a relatively small file that gives you the mean value of each data layer for the 190 delineated headwater catchments. 
## Reproduce data from existing rasters
Go to [Zenodo](https://doi.org/10.5281/zenodo.7708691) and download the `basic_stack_dir` folder and other large files and place them in the repo you download from GitHub. Also download [Simon's InSAR files](https://doi.org/10.5281/zenodo.7542485). 
## Reproduce data from scratch
Here is how you would reproduce the data in this repo if you don't download the associated large tif files from Zenodo:
1. Download the ArcticDEM DEM tiles for the Seward Peninsula
2. Trim to the study area using the `expanded_insar_clipper.shp` files
3. Use [`LSDTopoTools2`](https://lsdtopotools.github.io/LSDTT_documentation/) to perform basic topographic analyses, channel extraction, and hillslope channel coupling on that trimmed DEM. You can find these driver files in `lsdtt_drivers`. You need to make sure you get:
- elevation
- slope
- tan curv LW
- dinf area
- the hcc_AllBasins raster
4. Put those files into either the `basic_stack_dir` or main directory to run the analysis notebook. Also download [Simon's InSAR files](https://doi.org/10.5281/zenodo.7542485). 
5. There is a zipped folder on Zenodo called `junction _slopeareas` which contains manually sorted `.png` files named by the basin whether displacement occurred in the hillslope, water track, fluvial, or indeterminate geomorphic regime. You need this file to run the scripts to make Figure 8b and the supporting figure. 
6. There is a separate notebook for running `statannotator` to produce Figure 8b, which needs a seaborn version < 0.12, so I ended up running it in its own special conda environment. 
