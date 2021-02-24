
alcf plot - plot lidar data

Usage: `alcf plot <plot_type> <input> <output> [<options>] [<plot_options>]`

Arguments:

- `plot_type`: plot type (see Plot types below)
- `input`: input filename or directory
- `output`: output filename or directory
- `options`: see Options below
- `plot_options`: Plot type specific options. See Plot options below.

Plot types:

- `backscatter`: plot backscatter from `alcf lidar` output
- `backscatter_hist`: plot backscatter histogram from `alcf stats` output
- `backscatter_sd_hist`: plot backscatter standard deviation histogram from
  `alcf stats` output
- `cl`: plot model cloud area fraction from `alcf lidar` output
- `cli`: plot model mass fraction of cloud ice from `alcf lidar` output
- `cloud_occurrence`: plot cloud occurrence from `alcf stats` output
- `clw`: plot model mass fraction of cloud liquid water from `alcf lidar`
  output
- `clw+cli`: plot model mass fraction of cloud liquid water and ice from
  `alcf lidar` output

Options:

- `dpi: <value>`: Resolution in dots per inch (DPI). Default: `300`.
- `--grid`: plot grid
- `height: <value>`: Plot height (inches).
    Default: `5` if `plot_type` is `cloud_occurrence` or `backscatter_hist`
    else `4`.
- `subcolumn: <value>`: Model subcolumn to plot. Default: `0`.
- `title: <value>`: Plot title.
- `width: <value>`: Plot width (inches).
    Default: `5` if `plot_type` is `cloud_occurrence` or `backscatter_hist`
    else `10`.

Plot command options:

- `backscatter`:
    - `lr: <value>`: Plot effective lidar ratio. Default: `true`.
    - `cloud_mask: <value>`: plot cloud mask. Default: `true`.
    - `sigma: <value>`: Remove of number of standard deviations of backscatter
        from the mean backscatter (real). Default: `5`.
    - `remove_bmol: <value>`: Remove molecular backscatter (observed data have
        to be coupled with model data via the `couple` option of `alcf lidar`).
        Default: `true`.
    - `vlim: { <min> <max }`. Value limits (10^6 m-1.sr-1).
        Default: `{ 0.1 200 }`.
    - `vlog: <value>`: Plot values on logarithmic scale: `true` of `false`.
        Default: `true`.
- `backscatter_hist`:
    - `vlim: { <min> <max> }`. Value limits (%) or `none` for auto. If `none`
        and `vlog` is `none`, `min` is set to 1e-3 if less or equal to zero.
        Default: `none`.
    - `--vlog`: use logarithmic scale for values
    - `xlim: { <min> <max> }`. x axis limits (10^6 m-1.sr-1) or `none` for
        automatic. Default: `none`.
    - `zlim: { <min> <max> }`. z axis limits (m) or `none` for automatic.
        Default: `none`.
- `backscatter_sd_hist`:
    - `xlim: { <min> <max> }`. x axis limits (10^6 m-1.sr-1) or `none` for
        automatic. Default: `none`.
    - `zlim: { <min> <max> }`. z axis limits (%) or `none` for
        automatic. Default: `none`.
- `cl`:
    - `vlim: { <min> <max> }`. Value limits (%).
        Default: `{ 0 100 }`.
    - `vlog: <value>`: Plot values on logarithmic scale: `true` of `false`.
        Default: `false`.
    - `zres: <zres>`: Height resolution (m). Default: `50`.
- `cli`, `clw`, `clw+cli`:
    - `vlim: { <min> <max> }`. Value limits (g/kg).
        Default: `{ 1e-3 1 }`.
    - `vlog: <value>`: Plot values on logarithmic scale: `true` of `false`.
        Default: `true`.
    - `zres: <zres>`: Height resolution (m). Default: `50`.
- `cloud_occurrence`:
    - `colors: { <value>... }`: Line colors.
        Default: `{ #0084c8 #dc0000 #009100 #ffc022 #ba00ff }`
    - `linestyle: { <value> ... }`: Line style (`solid`, `dashed`, `dotted`).
        Default: `solid`.
    - `labels: { <value>... }`: Line labels. Default: `none`.
    - `lw: <value>`: Line width. Default: `1`.
    - `xlim: { <min> <max> }`: x axis limits (%). Default: `{ 0 100 }`.
    - `zlim: { <min> <max> }`: z axis limits (m). Default: `{ 0 15 }`.

Examples:

Plot backscatter from processed Vaisala CL51 data in `alcf_cl51_lidar`
and store the output in the directory `alcf_cl51_backscatter`.

    alcf plot backscatter alcf_cl51_lidar alcf_cl51_backscatter
	