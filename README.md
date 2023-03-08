# Where's the data??
If you don't want to run this notebook, the `basin_means.csv` file is a relatively small file that gives you the mean value of each data layer for the 190 delineated headwater catchments. 
# Reproduce data from existing rasters
Go to Zenodo and download the `basic_stack_dir` folder and other large files and place them in the repo you download from GitHub. 
# Reproduce data from scratch
Here is how you would reproduce the data in this repo if you don't download the associated large tif files from Zenodo:
1. Download the ArcticDEM DEM tiles for the Seward Peninsula
2. Trim to the study area using the `expanded_insar_clipper.shp` files
3. Use `LSDTopoTools2` to perform basic topographic analyses, channel extraction and hillslope channel coupling on that trimmed DEM. You can find these driver files in `lsdtt_drivers`. You need to make sure you get:
- elevation
- slope
- tan curv LW
- dinf area
- the hcc_AllBasins raster
4. Put those files into either the `basic_stack_dir` or main directory to run the analysis notebook 
5. There is a separate notebook for running `statannotator ` which needs a seaborn version < 0.12, so I ended up running it in its own special conda environment. 