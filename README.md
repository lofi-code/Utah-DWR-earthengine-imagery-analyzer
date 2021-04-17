# Utah-DWR-earthengine-imagery-analyzer
Contains an interactive notebook to examine sentinel imagery anywhere in the world, designed to be used by the Utah DWR to examine phenology patterns.  

## Summary
This interactive notebook bundles together two main features. The first of these is an interactive plot generator for vegetation index timeseries. For any reasonably sized bounding box, the code will grab sentinel 2 imagery between two input dates, mask out clouds and snow, and reduce the average vegetation index values to an interactive altair plot. The second feature is an interactive imagery comparison map that allows users to compare sentinel imagery using a slider. 

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

Open command line/terminal and activate your python environment:

    conda activate gee
    
Enter the following:

    jupyter notebook
    
Jupyter Notebooks will open in your browser. Open the Nbextesions tab and make sure "Hide input all" is checked.

![image](https://user-images.githubusercontent.com/82716404/115119378-4f8bb000-9f65-11eb-91da-56ed1250639e.jpeg)

### Download the Notebook

[Click here](https://raw.githubusercontent.com/lofi-code/Utah-DWR-earthengine-imagery-analyzer/main/Wildlife_Crossing_Sentinel_Analyzer.ipynb) or navigate to the notebook in github and click "raw". Then press command/control S to save the notebook. Make sure to remove ".txt" from the file, so that the file type is ".ipynb". Save it to your preffered folder. 


### Initialize and Authenticate Earthengine:
Return to Jupyter Notebook in your browser. Navigate to the notebook you just downloaded using the files tab. Click to open it. Run the first cell to authenticate and initialize eathengine. once initialized, comment out "ee.authenticate()". The authentication token will be saved for future sessions. 

### Run notebook interactively:
To run the notebook in interactive mode, first click on the eye symbol to hide the code. Then click Kernel> Restart & Run All, and wait for the code to run. When using the app, keep an eye on the circle in the upper right corner next to "Python 3". If this is solid, python is running. If it is a circle outline, then the code has excecuted. See the highlighted sections in the screenshot below: 

![Screen Shot 2021-04-17 at 10 29 18 AM](https://user-images.githubusercontent.com/82716404/115119975-43edb880-9f68-11eb-9495-9fad1326ab07.jpg)

The app should be ready to use. 




