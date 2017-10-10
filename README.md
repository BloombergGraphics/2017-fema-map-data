FEMA Flood MAP "Effective Date" Data and Map Files
===

This repo includes data used in a Oct. 6, 2017 story, [Outdated and Unreliable: FEMA’s Faulty Flood Maps Put Homeowners at Risk](https://www.bloomberg.com/graphics/2017-fema-faulty-flood-maps/).

The Federal Emergency Management Agency provided the data to Bloomberg News.

## Files

The [data](data/) folder includes two data files:

* Panel_Info_091217_Pivot.xlsx — The original spreadsheet provided to us in Excel format listing communities by ID showing the latest map "effective date." More information below.
* LFD master list.xlsx — The original spreadsheet provided to us in Excel format representing a master list of ["Letters of Final Determination"](https://www.fema.gov/letter-final-determination). More information below.

The second sheet in `Panel_Info_091217.xlsx`, the non-pivot table sheet, can be joined with geographies in FEMA shapefile `CL_Final_Deliverable_20150203.zip`, which is available at https://data.femadata.com/FIMA/FIMA_Community_Boundary_Data/Community_Layer/

That geodatabase comes with documentation describing the different geographic layers. We used the “Union Community Layer” since that is the most comprehensive.

Information about these files from FEMA:

> The FEMA Flood Map Service Center (MSC) is the official public source for flood hazard information produced in support of the National Flood Insurance Program (NFIP).
>  * The file “Panel Info 091217” contains the data requested.  One worksheet contains the raw data by community, the other data sheet contains a pivot table by county.

> The file “LFD_master_list” contains the data requested.  The data is organized with a pivot table in the first tab and the raw data under the second tab. 
>  * FEMA would like to note the following:
>    * The data presented in the table is only as current as the LFD date listed for that particular community as this is a comprehensive list that continues to be compiled.
>    * Each row of data is only as current as that LFD date since it is a comprehensive list of all communities for each LFD over several years. Therefore, multiple revision within these communities may have occurred and as such there will likely be more than one LFD for some communities and thus these will be listed multiple times with varying values for the rest of the columns.

## Caveats

The effective date does not necessarily reflect the date that the area was last studied. From the story:

> A map’s effective date comes with caveats. Maps can go into effect years after some of the terrain was actually studied, giving the impression an area is more up to date than it really is. Not every change is significant enough to warrant a new effective date. However, some small changes within a larger region will sometimes trigger a new effective date for the entire community, even if large swaths of the area weren’t re-examined—giving residents incomplete information about their flood risk.


### Community IDs

Many of the community IDs have leading zeros. When opening up the second sheet in Panel_Info_091217_Pivot.xlsx, be careful that Excel will generally remove these. It's best to save this sheet out as a CSV programatically and preserve leading zeros, or add them back in later.

### Possible errors

Community with ID `130665` and named `LINCOLN COUNTY UNINCORPORATED AREAS` is listed as being a part of `LEE COUNTY`. This [appears to be an error](https://map1.msc.fema.gov/data/13/S/PDF/13181CV000A.pdf?LOC=082cd284007d8ec8de83e676dc8e87be) and should be `LINCOLN COUNTY`.

## Attribution

The provided data should be cited as `Federal Emergency Management Data obtained by Bloomberg News`.

If the data is used in an online story, the source line should include a link to this repository.
