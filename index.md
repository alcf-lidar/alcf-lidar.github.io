---
title: Home
layout: default
---

<div class="abstract">
ALCF is an open source command line tool for processing of automatic lidar and ceilometer (ALC) data and intercomparison with atmospheric models such as general circulation models (GCMs), numerical weather prediction (NWP) models and reanalyses utilising a lidar simulator based on the <a href="https://www.earthsystemcog.org/projects/cfmip/cosp">COSP</a> instrument simulator framework. ALCs are vertically pointing atmospheric lidars, measuring cloud and aerosol backscatter. The primary focus of ALCF are atmospheric studies of cloud using ALC observations and model cloud validation.
<div style="font-weight: normal; text-align: center; margin: 14px 0">
<a href="https://github.com/peterkuma/research/raw/master/papers/Kuma%20et%20al.%20(2020),%20Ground-based%20lidar%20processing%20and%20simulator%20framework%20for%20comparing%20models%20and%20observations%20[2020-01-28].pdf">Paper</a> (submitted to GMD) &nbsp;|&nbsp; <a href="presentation.pdf">Presentation</a> &nbsp;|&nbsp; <a href="poster.pdf">Poster</a>
</div>

</div>

### Features

#### Multiple instruments and models

ALCF can process data from multiple ceilometers and lidars:
Vaisala [CL31](https://www.vaisala.com/en/products/instruments-sensors-and-other-measurement-devices/weather-stations-and-sensors/cl31), [CL51](https://www.vaisala.com/en/products/instruments-sensors-and-other-measurement-devices/weather-stations-and-sensors/cl51), Lufft [CHM 15k](https://www.lufft.com/products/cloud-height-snow-depth-sensors-288/ceilometer-chm-15k-nimbus-2300/) and Sigma Space [MiniMPL](https://www.micropulselidar.com/). Multiple models
and reanalyses are supported by the lidar simulator: [AMPS](http://www2.mmm.ucar.edu/rt/amps/), [ERA5](https://www.ecmwf.int/en/forecasts/datasets/reanalysis-datasets/era5), [JRA-55](https://jra.kishou.go.jp/JRA-55/index_en.html), [MERRA-2](https://gmao.gsfc.nasa.gov/reanalysis/MERRA-2/), [NZCSM](https://www.nesi.org.nz/case-studies/improving-new-zealands-weather-forecasting-ability) and [UM](https://www.metoffice.gov.uk/research/approach/modelling-systems/unified-model/index).

<div class="img-flex">
<a href="{{ "/img/chm15k_512x.jpg" | relative_url }}"><img src="{{ "/img/chm15k_512x.jpg" | relative_url }}" height="200" /></a>
<a href="{{ "/img/cl51_512x.jpg" | relative_url }}"><img src="{{ "/img/cl51_512x.jpg" | relative_url }}" height="200" /></a>
</div>

#### Resampling and noise removal

ALCF resamples lidar backscatter to chosen temporal and vertical sampling
to increase signal-to-noise ratio, calculates noise standard deviation from
the highest level and removes noise.

<div class="img-flex nospace">
<div>
<a href="{{ "/img/rutherford14_2014-03-30T00:00:00.png" | relative_url }}"><img src="{{ "/img/rutherford14_2014-03-30T00:00:00.png" | relative_url }}" width="600" /></a>
</div>
</div>

#### Lidar simulator

Embedded lidar simulator based on COSP can be applied on model data
to produce virtual backscatter measurements comparable with ALC observations
for the purpose of model evaluation.

<div class="img-flex nospace">
<div><center><strong>Luff CHM 15k observations</strong></center><a href="/img/birdlings16_chm15k_2016-07-18T00:00:00.png"><img src="/img/birdlings16_chm15k_2016-07-18T00:00:00.png" width="400" /></a></div>
<div><center><strong>AMPS model simulated lidar</strong></center><a href="/img/birdlings16_amps_2016-07-18T00:00:00.png"><img src="/img/birdlings16_amps_2016-07-18T00:00:00.png" width="400" /></a></div>
</div>

#### Cloud detection

Cloud detection is done by applying a threshold on the denoised absolute
backscatter. More sophisticated algorithms may be added in the future.

<div class="img-flex nospace">
<a href="/img/birdlings16_chm15k_cm_2016-07-04T00:00:00.png"><img src="/img/birdlings16_chm15k_cm_2016-07-04T00:00:00.png" width
="600" /></a>
</div>

#### Cloud occurrence

Cloud occurrence histogram as a function of height can be calculated
and plotted from observations and model simulated backscatter.

<figure>
<figcaption><center><strong>Vaisala CL 51 vs. HadGEM3 model</strong></center></figcaption>
<div class="img-flex nospace">
<div><a href="/img/mcq_cl51.png"><img src="/img/mcq_cl51.png" width="267" /></a></div>
<div><a href="/img/nbp1704_chm15k.png"><img src="/img/nbp1704_chm15k.png" width="267" /></a></div>
<div><a href="/img/tan1802_chm15k.png"><img src="/img/tan1802_chm15k.png" width="267" /></a></div>
</div>
</figure>

#### Calibration

Lidar ratio can calculated and plotted along the backscatter for absolute
calibration of lidar backscatter using fully-opaque stratocumulus scenes
([O'Connor et al., 2004](https://journals.ametsoc.org/doi/abs/10.1175/1520-0426(2004)021%3C0777%3AATFAOC%3E2.0.CO%3B2)).

<div class="img-flex nospace">
<a href="/img/birdlings16_chm15k_lr_2016-07-16T00:00:00.png"><img src="/img/birdlings16_chm15k_lr_2016-07-16T00:00:00.png" width="600" /></a>
</div>

<!--
#### Backscatter histogram
-->

#### Open source

<img src="{{ "/img/osi_mit.png" | relative_url }}" height="100" style="float: left; margin-right: 16px" />

ALCF is available under the terms of the MIT license, which allows free
use, copying, modification and redistribution.

