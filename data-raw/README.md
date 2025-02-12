# Data collecting and formatting routines

This directory contains scripts to collect / populate basic data used in the
FluxDataKit workflow (formal product output, not the package as such). Some
data is provided with the repo (such as ancillary and meta data folders), other
data is too large and needs to be downloaded separately, using included scripts
or manually due to login walls on download APIs.

Scripts need to be executed in order, and data directories need to be populated
for them to function.

## Scripts

- 00_download_plumber_data.R - downloads PLUMBER-2 data
- 01_collect_meta-data.R - collects meta-data given downloaded data
- 02_compile_final_site_list.R - using the data set age determine the most recent version
- 03_convert_plumber.R - converts PLUMBER-2 data to a FLUXNET format to ensure parity with other final data outputs
- 04_download_modis_data.R - collect required MODIS products (FPAR/LAI)

## Data requirements

Data was sourced from different locations:

- ICOS data was provided through the ICOS carbon portal, this is a pre-release currently *not publicly available*
- FLUXNET2015 data can be retrieved from the [FLUXNET data porta](https://fluxnet.org/data/fluxnet2015-dataset/)
- OneFlux data can be retrieved from the [Ameriflux data portal](https://ameriflux.lbl.gov/data/download-data/)
- PLUMBER data can be downloaded using [an included script](https://github.com/geco-bern/FluxDataKit/blob/main/data-raw/00_download_plumber_data.R)
- MODIS LAI/FPAR data is downloaded by an included script

## Data structure

Data should be structured in the following directory structure and referenced
to as such in the data generation workflow:

```
data/
   ├─ modis/
   ├─ flux_data/
      ├─ fluxnet2015/
      ├─ icos/
      ├─ oneflux/
      ├─ ameriflux/
```
