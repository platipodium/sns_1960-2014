# SNS 1960 - 2014

Configuration of the MOSSCO coupled system for simulating the Southern
North Sea (SNS) 1960-2014.  The material presented here is freely available under
the terms of the CC0 1.0 Universal Public Domain Dedication, the `License.md` for 
the full license terms.

The material presented here was created by Richard Hofmeister, Carsten Lemmen, 
Knut Klingbeil and Kai W Wirtz.

To be published as as supplement to Xu et al. 2020 "Less nutrients but more phytoplankton:
long-term ecosystem dynamics of the southern North Sea"

## Coupled system (MOSSCO) configuration

`gfbfrr.yaml`
:  Coupling topology, components, and coupling intervals.  This file is used
by `$MOSSCO_DIR/scripts/create_coupling.py` to create the hub and spoke
topology of a coupled system.

`boundary_input.cfg`
: Configuration of the BGC boundary input.  Climatological DIN and DIP are read from
`Forcing/bdy_3d_ecoham_2000-2010_linear_Z20_Tclim_redNP_phyZoo01.nc`, a file that
is available on request.

`mossco_gfbfrr.cfg`
: Configuration of the netcdf output component.

`nudge_connector.cfg`
: Configuration of boundary nudging.  The default value is to nudge with 100%.

`restart_soil.cfg`
: Configuration of benthic hotstart/initialization

`restart_water.cfg`
: Configuration of pelagic hotstart/initialization

`river_input.cfg`
: Configuration of river BGC input. Values are read from
`Forcing/River/river_ret85_19502016_phy.nc`, a file that
is available on request.

Component configuration files for all other components (`fabm_pelagic.cfg`,
  `fabm_sediment.cfg`, `default.cfg`, `getm.cfg`, `transport_connector.cfg`, `pelagic_soil_connector.cfg`, `soil_pelagic_connector.cfg`) are not used.
Instead, default configurations for these components are assumed or namelist input provided.

`default.dat`:
Constant values for sediment upper boundary used by default component

## Additional BGC (FABM) configuration

`fabm.nml`
: Configures pelagic FABM framework for MAECS model

`fabm_pelagic.nml`
: Configures pelagic FABM component

`fabm_sed.nml`
: Configures benthic FABM framework for OMExDia model

`run_sed.nml`
: Configures benthic FABM component

## Additional hydrodynamics (GETM) configuration

`getm.inp`
: Full specification of GETM

`bdyinfo.dat`
: Describes the 2 open boundaries.  The 2D and 3D boundary files `Forcing/sns_bdy_2d_1948-2015_trim1_coastdatII.nc` and
`Forcing/sns_climatology.nc` are available on request.

`riverinfo.dat`
: Describes the 10 river data sources. The river discharge file `Forcing/River/rivers.nc` is available on request.

`meteofiles_gen.dat`
: Describes path to meteorological forcing.  The coastDatII data are available
from the WDCC after registration.

`par_setup.dat`
: Domain partitioning for 61 compute domains

`parallel.inp`
: Parallelization strategy configuration
