
## Installation

The ALCF is written in Python and Fortran. Installation on Linux is recommended.
Installation on Windows is possible under the "Windows Subsystem for Linux".

### Linux

The installation has been tested on [Debian GNU/Linux](https://www.debian.org/) 10, [Devuan GNU/Linux](https://devuan.org/) 2.1,
[Ubuntu](https://ubuntu.com/) Desktop 19.10 and [Fedora](https://getfedora.org/) 31 Workstation.

Install the following required software:

- gfortran and gcc (usually available in Linux distribution repositories)
- Python 3 (usually pre-installed on Linux distributions)

Download and unpack one of the [releases](#releases)
or the [latest development version](https://github.com/peterkuma/alcf/archive/master.zip)
of the ALCF and run commands below in the unpacked directory.

Before compiling the dependencies, you might need to install the following
packages: gfortran, libexpat-dev, m4, libcurl4-openssl-dev and zlib1g-dev,
python3-setuptools, python3-pip and eccodes. Install with:

```sh
# Debian, Devuan, Ubuntu:
apt-get install gfortran libexpat-dev m4 libcurl4-openssl-dev zlib1g-dev python3-setuptools python3-pip libeccodes-tools unzip
# Fedora:
yum install make patch g++ gfortran expat-devel m4 libcurl-devel zlib-devel python3-setuptools python3-pip eccodes
```

To download and build dependencies
([UDUNITS](https://www.unidata.ucar.edu/software/udunits/),
[NetCDF](https://www.unidata.ucar.edu/software/netcdf/),
[NetCDF-Fortran](https://www.unidata.ucar.edu/software/netcdf/docs-fortran/),
[OSSP uuid](http://www.ossp.org/pkg/lib/uuid/),
[HDF5](https://www.hdfgroup.org/solutions/hdf5),
[CMOR](https://pcmdi.github.io/cmor-site/),
[COSP](https://github.com/alcf-lidar/COSPv1)):

```sh
./download_dep
./build_dep
make
```

`download_dep` will automatically download required libraries and `build_dep`
will compile the libraries (it might take up to 5 minutes to finish).

**Note:** The ALCF uses Python libraries
[numpy](https://numpy.org),
[scipy](https://www.scipy.org),
[matplotlib](https://matplotlib.org),
[netCDF4](http://github.com/Unidata/netcdf4-python),
[ds-python](https://github.com/peterkuma/ds-python),
[aquarius-time](https://github.com/peterkuma/aquarius-time),
[pst-format](https://github.com/peterkuma/pst),
[cl2nc](https://github.com/peterkuma/cl2nc) and
[astropy](https://www.astropy.org), which are installed with the commands below.

To install in system directories:

```sh
python3 setup.py install
```

To install in user directories (make sure `~/.local/bin` is in the environmental variable `PATH`):

```sh
python3 setup.py install --user
```

You should now be able to run the ALCF in the terminal:

```sh
alcf
```

should output:

```
{% include cmd_main.md %}
```

### Windows

Installation on Windows is possible under the "Windows Subsystem for Linux".

1. Install "Ubuntu" from the Microsoft Store. You might have to enable
"Windows Subsystem for Linux" under "Windows Features" first.

2. Open "Ubuntu" from the Start Menu and follow the instructions above for
installation on Linux (Ubuntu). Use `cd /mnt/c/Users/<users>`, where `<user>`
is your Windows user name, to change the current directory to your home
directory, and `ls` to list the directory contents. Note that the alcf
release archive has to be extracted in the Ubuntu console in order to preserve
symbolic links: use the command `tar xf alcf-<version>.tar.gz`, where
`<version>` is the version string of the release you have downloaded.

## Releases

Below is a list of releases of the ALCF. The version numbers follow
the [Semantic Versioning](https://semver.org).

#### [1.1.0](https://github.com/alcf-lidar/alcf/releases/tag/v1.1.1) (2021-06-29)

<details>
<summary>Release notes</summary>
<ul>
<li>Support for Vaisala CL61 and NetCDF files produced by BL-VIEW.</li>
<li>Improved documentation.</li>
</ul>
</details>

#### [1.0.1](https://github.com/alcf-lidar/alcf/releases/tag/v1.0.1) (2021-02-24) [[documentation](https://github.com/alcf-lidar/alcf/releases/download/v1.0.1/alcf-doc-1.0.1.zip)] [DOI: [10.5281/zenodo.5036683](https://doi.org/10.5281/zenodo.5036683)]

<details>
<summary>Release notes</summary>
<ul>
<li>Fixed download links to dependencies (udunits archive was removed upstream).</li>
</ul>
</details>

#### [1.0.0](https://github.com/alcf-lidar/alcf/releases/tag/v1.0.0) (2021-01-02) [[documentation](https://github.com/alcf-lidar/alcf/releases/download/v1.0.0/alcf-doc-1.0.0.zip)] [DOI: [10.5281/zenodo.4411633](https://doi.org/10.5281/zenodo.4411633)]

<details>
<summary>Release notes</summary>
<ul>
<li>First stable release. No change from 1.0.0-beta.3.</li>
</ul>
</details>

#### [1.0.0-beta.3](https://github.com/alcf-lidar/alcf/releases/tag/v1.0.0-beta.3) (2020-10-15) [[documentation](https://github.com/alcf-lidar/alcf/releases/download/v1.0.0-beta.3/alcf-doc-1.0.0-beta.3.zip)] [DOI: [10.5281/zenodo.4088217](https://doi.org/10.5281/zenodo.4088217)]

<details>
<summary>Release notes</summary>
<ul>
<li>alcf lidar option for coupling of observed data with simulated molecular backscatter.</li>
<li>Removal of molecular backscatter in plots (if available).</li>
<li>alcf stats filter option now supports "night" and "day" and passing of multiple arguments.</li>
<li>New lidar type "default" for re-precessing of already processed lidar data.</li>
<li>Support for plotting of model cloud liquid water, ice content and cloud fraction.</li>
<li>Calculation of lidar ratio changed to effective lidar ratio.</li>
<li>Backscatter plots now show effective lidar ratio and cloud mask by default.</li>
<li>Changed default vlim for backscatter plots to { 0.1 200 } and default sigma to 5.</li>
<li>Output files names are now without colons, which are not compatible with Windows.</li>
<li>More accurate plot labels.</li>
<li>Improved time sampling: exact profile time bounds are used from weighting.</li>
<li>Improved handling of errors and stopping with Ctrl+C.</li>
<li>Improved NetCDF metadata.</li>
<li>Improved compatibility with newer versions of matplotlib.</li>
<li>Fixed clearing of figures in alcf plot backscatter.</li>
</ul>
</details>

#### [1.0.0-beta.2](https://github.com/alcf-lidar/alcf/releases/tag/v1.0.0-beta.2) (2020-05-01) [[documentation](https://github.com/alcf-lidar/alcf-lidar.github.io/releases/download/v1.0.0-beta.2/alcf-doc-1.0.0-beta.2.zip)] [DOI: [10.5281/zenodo.3779518](https://doi.org/10.5281/zenodo.3779518)]

<details>
<summary>Release notes</summary>
<ul>
<li>Initial beta release.</li>
</ul>
</details>
