# Comparing-Read-Times-of-NetCDF-and-Zarr
### Overview 
This project compares read times of netCDF-3, netCDF-4, netCDF-4 Classic, Zarr, and Zarr being read with Xarray.

The data used in this example is publicly avaliable from Unidata's [example files](https://www.unidata.ucar.edu/software/netcdf/examples/files.html). The file is from the Community Climate System Model (CCSM) with one time step of precipitation flux, air temperature, and eastward wind. The data was converted from netCDF-3 to Zarr using [this repository](https://github.com/jonahjoughin/netcdf-to-zarr). The netCDF-4 files were created from the original example file using Unidata's [nccopy utility](https://www.unidata.ucar.edu/software/netcdf/workshops/2011/utilities/Nccopy.html). Zarr directory stores were chunked using [Rechunker](https://rechunker.readthedocs.io/en/latest/).

The following chunk sizes applied to latitude and longitude (lat/lon) were compared:
* 128 x 256 (original)
* 64 x 64
* 16 x 16
* 4 x 4

Run times are recorded in milliseconds using `timeit` with the average taken of 100 excecutions.

### Dependencies
Dependencies & Versions
  - python=3
  - netcdf4=1.5.7
  - hdf5=1.8.20
  - jupyter=6.1.3
  - zarr=2.8.3
  - xarray = 0.11.3
  - matplotlib=3.4.2

