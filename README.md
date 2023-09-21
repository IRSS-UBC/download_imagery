# Bulk Download Satellite Imagery
Code used to download and process large amounts of Sentinel-2 and Landsat imagery using various methods.

## Google Earth Engine datasets using geemap (geemap_download_imagery.ipynb): 
This method has the benefit of removing the need for manually building mosaics, and makes use of analysis ready products (e.g., Landsat-8 surface reflectance) hosted by Google. This method also provides the benefit of skipping the need to download earth engine data to your google drive first, since geemap can download imagery directly to your local drive.

## Harmonized Landsat Sentinel products using USGS M2M
- HLS is a virtual constellation of Landsat (8/9) and Sentinel-2 data (L30 and S30)
- HLS Subsetting, Processing, and Exporting Reformatted data 
- Searches for available scenes for given parameters
- Downloads images cropped to your region of interest
- USGS Machine-2-Machine
- Command-line interface for downloading Landsat scenes
- Also available as a python script
- Requires USGS account and requested access

#### Setup and Use

1. Set up USGS account https://ers.cr.usgs.gov/register

2. Read documentation about how to request access from USGS to use M2M: https://github.com/Fergui/m2m-api

3. Install Machine-2-Machine package: https://pypi.org/project/usgsm2m/ in your python environment

    ```pip install usgsm2m```

4. (optional) Store your credentials as an environment variable (set in CMD)

5. Run the script with your own input arguments. Below is an example:

```usgsm2m search -l 30.482, -97.842 -u chrismulverhill -p MYPASSWORD -d landsat_tm_c2_l2 -c 50 > result.csv```

```usgsm2m downloadbulk -e result.csv -u chrismulverhill -p MYPASSWORD```

