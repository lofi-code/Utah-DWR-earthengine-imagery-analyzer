# Utah-DWR-earthengine-imagery-analyzer
Contains an interactive notebook to examine sentinel imagery anywhere in the world, designed to be used by the Utah DWR to examine phenology patterns.  

## Summary
This interactive notebook bundles together two main features. The first of these is an interactive plot generator for vegetation index timeseries. For any reasonably sized bounding box, the code will grab sentinel 2 imagery between two input dates, mask out clouds and snow, and reduce the average vegetation index values to an interactive altair plot. The second feature is an interactive imagery comparison map that allows users to compare sentinel imagery using a slider.

## Python Version
This app was built and tested using Python 3.8.0.

## Setting up Conda and Jupyter

First make sure Anaconda or miniconda is installed. I use minicona.
* [miniconda](https://docs.conda.io/en/latest/miniconda.html)
* [anaconda](https://www.anaconda.com/distribution/#download-section)

It is reccomended to create a new conda environment specifically for earthengine analysis and install all the packages in it. 

Create a new environment called "gee" (enter into terminal):

    conda create -n gee python

Prior to launching jupyter notebooks or installing any packages, activate the conda environment:

    conda activate gee

Install [jupyterlab](https://jupyter.org/install):

    conda install -c conda-forge jupyterlab
 
Install [Jypyter Notebook Extensions](https://github.com/ipython-contrib/jupyter_contrib_nbextensions) to enable hiding the code, as well as other useful features:

    mamba install jupyter_contrib_nbextensions -c conda-forge

## List of Packages and Links to Installation

Most of the interactive features on this app are built using [ipywidgets](https://github.com/jupyter-widgets/ipywidgets) and [geemap](https://github.com/giswqs/geemap). Huge thanks to Qiusheng Wu of the geemap package for the helpful tutorials and package. All of the packages needed and links to installation are included below. 

* [geemap](https://github.com/giswqs/geemap#installation): Interactive mapping with earth engine
* [earthengine](https://developers.google.com/earth-engine/guides/python_install): Imagery visualization and processing platform
* [ipywidgets](https://github.com/jupyter-widgets/ipywidgets#Install): Interactive widgets in jupyter notebook
* [pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/install.html): DataFrame manipulation
* [geopandas](https://geopandas.org/getting_started/install.html): Geospatial data in python
* [OWSLib](https://geopython.github.io/OWSLib/): WFS retrieval
* [requests](https://pypi.org/project/requests/): HTTP requests
* [IPython](https://ipython.org/install.html): Interactive Data Visualization (should be included with Jupyter)
* [statistics](https://pypi.org/project/statistics/): Quick statistics in python
* [altair](https://altair-viz.github.io/getting_started/installation.html): Interactive plotting

## Starting the notebook

### Download the Notebook

[Click here](https://raw.githubusercontent.com/lofi-code/Utah-DWR-earthengine-imagery-analyzer/main/Wildlife_Crossing_Sentinel_Analyzer.ipynb) or navigate to "Utah-DWR-earthengine-imagery-analyzer" in this github repository and click "raw". Then press command/control S to save the notebook. Make sure to remove ".txt" from the file, so that the file type is ".ipynb". Save it to your preferred folder. 

### Start the Jupyter Notebooks Application
Open command line/terminal and activate your python environment:

    conda activate gee
    
Enter the following:

    jupyter notebook
    
Jupyter Notebooks will open in your browser. Open the Nbextesions tab and make sure "Hide input all" is checked.

![image](https://user-images.githubusercontent.com/82716404/115119378-4f8bb000-9f65-11eb-91da-56ed1250639e.jpeg)

### Initialize and Authenticate Earthengine:
In the Jupyter Notebook application, navigate to the notebook you just downloaded using the files tab. Click to open it. Run the first cell to authenticate and initialize eathengine (shift+enter will run the selected cell). Once initialized, comment out "ee.authenticate()". The authentication token will be saved for future sessions. 

### Run notebook interactively:
To run the notebook in interactive mode, first click on the eye symbol to hide the code. Then click "Kernel> Restart & Run All", and wait for the code to run. When using the app, keep an eye on the circle in the upper right corner next to "Python 3". If this is solid, python is running. If it is a circle outline, then the code has excecuted. See the highlighted sections in the screenshot below: 

![Screen Shot 2021-04-17 at 10 29 18 AM](https://user-images.githubusercontent.com/82716404/115119975-43edb880-9f68-11eb-9495-9fad1326ab07.jpg)

The app should be ready to use. 

## Future Developments:
As this is quite an interesting project and useful tool, I could see myself adding more functionality and features in the future. Some examples would be:

* Hosting the site as an HTML web site
* More vegetation indicies
* Snowcover percentage
* Atmospheric correction for sentinel imagery to allow the app to go further back in time
* Harmonizing sentinel and LANDSAT to even further back in time

## References

1) Jdbcode. (2021). Sentinel-2 cloud masking with S2CLOUDLESS | Google Earth Engine. Retrieved April 17, 2021, from https://developers.google.com/earth-engine/tutorials/community/sentinel-2-s2cloudless
2) Jdbcode. (2021). Time series visualization with altair | google earth engine. Retrieved April 17, 2021, from https://developers.google.com/earth-engine/tutorials/community/time-series-visualization-with-altair
3) Wu, Q., (2020). geemap: A Python package for interactive mapping with Google Earth Engine. The Journal of Open Source Software, 5(51), 2305. https://doi.org/10.21105/joss.02305
4) Cong Wang, Jin Chen, Jin Wu, Yanhong Tang, Peijun Shi, T. Andrew Black, Kai Zhu, A snow-free vegetation index for improved monitoring of vegetation spring green-up date in deciduous ecosystems, Remote Sensing of Environment, Volume 196, 2017, Pages 1-12, ISSN 0034-4257, https://doi.org/10.1016/j.rse.2017.04.031. (https://www.sciencedirect.com/science/article/pii/S0034425717301906)
5) VanderPlas, J., Granger, B., Heer, J., Moritz, D., Wongsuphasawat, K., Satyanarayan, A., … Sievert, S. (2018). Altair: Interactive statistical visualizations for python. Journal of Open Source Software, 3(32), 1057.
6) McKinney, W., & others. (2010). Data structures for statistical computing in python. In Proceedings of the 9th Python in Science Conference (Vol. 445, pp. 51–56).
7) Jordahl, K. (2014). GeoPandas: Python tools for geographic data. URL: Https://Github. Com/Geopandas/Geopandas.
8) Kluyver, T., Ragan-Kelley, B., Fernando P'erez, Granger, B., Bussonnier, M., Frederic, J., … Willing, C. (2016). Jupyter Notebooks – a publishing format for reproducible computational workflows. In F. Loizides & B. Schmidt (Eds.), Positioning and Power in Academic Publishing: Players, Agents and Agendas (pp. 87–90).





