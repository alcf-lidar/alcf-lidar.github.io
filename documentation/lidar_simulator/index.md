---
title: Lidar simulator
layout: default
---

### [Documentation](../)
## Lidar simulator

ALCF uses a modified version of COSPv1 for lidar simulation, which can
be found at [github.com/peterkuma/COSPv1](https://github.com/peterkuma/COSPv1).
The ACTSIM lidar simulator included in COSP has been modified to account
for the different viewing geometry and wavelength of a ground-based lidar.

If you want to add support for another lidar in ALCF, you might have to
calculate Mie scattering parameters for the lidar wavelength, if it
is different from ones already implemented (532, 910, 1064 nm).
The code for calculating the parameters is located in
[github.com/alcf-lidar/alcf/mie_scattering](https://github.com/alcf-lidar/alcf/mie_scattering)
(TODO).
