# aas4wrf.py

`aas4wrf.py` is a Python script for create the `wrfchemi` file from local emissions need to run WRF-Chem model. It's based on his older broder [AAS4WRF.ncl](https://github.com/alvv1986/AAS4WRF).
Currently, It works with CBMZ/MOSAIC chemical mechanism.

## Installation

First, you need to install the modules that `aas4wrf.py` needs. We recommend to use anaconda.

You can clone this repo by:
```
git clone https://github.com/quishqa/AAS4WRF.py.git
```

Then, install the modules by:

```
conda install --yes --file requirements.txt
```

If everything goes well, you are ready to go.

## The input data
To run this script you need the the `wrfinput_d0x` and your temporal and spatial disaggregated emissions. You can see the needed format by exploring `emissions.txt` file.

## Configuration file `aas4wrf.cfg`
This file control some parameters to run the script.
* `wrfinput_file`: the location of wrfinput_d0x.
* `emission_file`: the location of the local emission file.
* `nx` and `ny`: the number of longitude and latitude points in which local emission were spatially disaggregated.
* `start_date` and `end_date`: `emissions.txt` temporal availability.
* `method`: we implement `conservative` and `nearest_s2d` methods for emissions regridding.
* `output_name` : location and name of produced `wrfchemi` file

## Usage

To run the script, type:
```
python aasrwrf.py aas4wrf.cfg
```
