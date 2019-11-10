
alcf convert - convert input instrument or model data to NetCDF

Usage: `alcf convert <type> <input> <output>`

- `type`: input data type (see Types below)
- `input`: input filename or dirname
- `output`: output filename or dirname

Types:

- `cl51`: Vaisala CL51 (converted with cl2nc)
- `jra55`: JRA-55 (converted with grib_to_netcdf)

If `input` is a directory, all data files in `input` are converted
to corresponding .nc files in `output`.
	