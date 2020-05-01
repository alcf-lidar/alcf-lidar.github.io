
## Installation

ALCF is written in Python and Fortran. Installation on Linux is recommended.
Installation on other operating systems may be possible and planned in the
future, but is not described here at the moment.

### Linux

The installation has been tested on [Debian GNU/Linux](https://www.debian.org/) 10, [Devuan GNU/Linux](https://devuan.org/) 2.1,
[Ubuntu](https://ubuntu.com/) Desktop 19.10 and [Fedora](https://getfedora.org/) 31 Workstation.

Install the following required software:

- gfortran and gcc (usually available in Linux distribution repositories)
- Python 3 (usually pre-installed on Linux distributions)

Download and unpack the [latest ALCF version](https://github.com/peterkuma/alcf/archive/master.zip)
or one of the [releases](#releases),
and run commands below in the unpacked directory.

Before compiling the dependencies, you might need to install the following
packages: gfortran, libexpat-dev, m4, libcurl4-openssl-dev and zlib1g-dev,
python3-setuptools, python3-pip and eccodes. Install with:

```sh
# Debian, Devuan, Ubuntu:
apt-get install gfortran libexpat-dev m4 libcurl4-openssl-dev zlib1g-dev python3-setuptools python3-pip libeccodes-tools
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

**Note:** ALCF uses the Python libraries [ds-python](https://github.com/peterkuma/ds-python),
[aquarius-time](https://github.com/peterkuma/aquarius-time) and
[pst](https://github.com/peterkuma/pst), which are installed with the commands
below.

To install in system directories:

```sh
pip3 install https://github.com/peterkuma/ds-python/archive/master.zip \
    https://github.com/peterkuma/aquarius-time/archive/master.zip \
    https://github.com/peterkuma/pst/archive/master.zip
python3 setup.py install
```

To install in user directories (make sure `~/.local/bin` is in the environmental variable `PATH`):

```sh
pip3 install --user https://github.com/peterkuma/ds-python/archive/master.zip \
    https://github.com/peterkuma/aquarius-time/archive/master.zip \
    https://github.com/peterkuma/pst/archive/master.zip
python3 setup.py install --user
```

You should now be able to run ALCF in the terminal:

```sh
alcf
```

should output:

```
{% include cmd_main.md %}
```

## Releases

Below is a list of releases of ALCF. The version numbers follow
the [Semantic Versioning](https://semver.org).

#### [1.0.0-beta.2](https://github.com/alcf-lidar/alcf/releases/tag/v1.0.0-beta.2) (2020-05-01) [[documentation](https://github.com/alcf-lidar/alcf-lidar.github.io/releases/download/v1.0.0-beta.2/alcf-doc-1.0.0-beta.2.zip)]


- Initial beta release.
