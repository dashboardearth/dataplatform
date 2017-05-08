# dataplatform
This is the aggregation, synthesize and analysis platform to supply Dashboard.Earth services with data

# overview
In order to build various user interfaces, services, platforms, partner integrations and all other future aspects of Dashboard.Earth it is required we create and maintain a data platform to bring in global climate, weather, condition and geo data from as many sources as possible.

This platform must aggregate data from a variety of sources operating on different collection timescales and data fidelity.  The platform will normalize, cleanse and present data to downstream applications in a unified and immediately usable form.  The platform will also make it possible to do custom analysis, create data packages ad hoc and systemically, and provide a search functionality.

# basic concept of data platform stack
Follow a typical big data nearline, off line and hot data model with exposure of each layer via APIs or a query interface.  Hide the internals of the data cleansing and normalization behind an abstraction layer so application develoeprs can treat all data in a simplified way.

* Offline data: long term historical data as well as raw data  (Azure/Hadoop)
* Nearline data: data that is often accessed but not required to be real time served to end client applications  (Azure, SQL Server)
* Real time data: real time application data access  (SQL Server/Caching Layer)

# stack interfaces
APIs should be JSON compatable and follow common RESTFul design patterns.

A Wolfram|Alpha/ElasticSearch/Solr style search/computable data query interface and results should be available for ad hoc queries and ad hoc api exposure.

Security should be as light weight as possible while logging should be extensive.

# data elements
The biggest challenge of climate, weather and conditional data within various geographies is normalizing space and time dimensions as well as units for what is measured.  e.g. not all data is collected on the same time scale which can make for confusing analysis.  Long term climate data is often not sampled on a second by second data like weather.  Weather stations tend to cover a reasonably large geographic area and climate data even larger geographic contexts whereas some sensor data can be relevant only within a few meters of the sensors location.  

The platform should have the following data elements queryable at various levels of geograph and time fidelity:

geographic query fidelity:
* gps coordinates/lat long
* countinent, country, state, county, city, neighborhood, address

time query fidelity:
* century
* decade
* year
* month
* day
* day part
* hour
* minute
* second

data values/elements:
* air temp (at different heights)
* ground temp
* air composition (PPM by chemical)
* wind speed
* seismic activity
* air quality / AQI
* topological height
* precipitation
* rain/snow
* wind chill
* heat index
* traffic
* animal/human population density
* vegetation/terrain make up
* ground composition (PPM by chemical/metal)
* sea levels
* ice levels
* life diversity measurements

and more... (too be extended)


# example data sources
This is a growing list of data sources that should be aggregated into the overall data collection and synthesis efforts

* Global Footprint Network	http://www.footprintnetwork.org/resources/data/		
* NOAA Climate Data	https://www.ncdc.noaa.gov/cdo-web/	General NOAA data	
* Climate.gov	https://www.climate.gov/maps-data	More general NOAA data	
* Wolfram Alpha	http://products.wolframalpha.com/api/	Mega load of lots of useful data for climate, history, geo etc	
* Climate Action	http://www.dataforclimateaction.org/home/data/	Company provided climate data	
* University of Oregon, PRISM	http://www.prism.oregonstate.edu/	General Climate data	
* GDelt Project	http://gdeltproject.org/data.html	World Event Data and News/History/Content	
* WRI	http://cait.wri.org/	More general climate data	
* EPA	https://www.epa.gov/outdoor-air-quality-data	Air Quality Data	
* Berkeley	http://berkeleyearth.org/data/	Longer History of Climate Data	
* Snow and Ice Center	http://nsidc.org/data	Histories of Snow and Ice Data	
* Data.gov	https://catalog.data.gov/dataset?tags=recycling	Recycling Data	
* Plume Labs	air.plumelabs.com	Global Air quality readings	
* Vital Signs 	http://vitalsigns.org/overview	Africa focussed	
* Columbia University	http://www.ciesin.org/index.html		
		

# normalization and synthesis 
Additional challenges arrive in maintaining a time/history sensitive ontology of geography.  Cities/States/Countries change names, dimensions often in the historical record and we need to be able to always have a sensitive map of that meta data in order to do large longitutidnal time studies on the data.

Sythesis will include producing summary metrics and descriptions for overall conditions. 

e.g.
* overall air quality
* overall "green" condition
* overall health

# example application interfaces
The following examples are applications that will be tied to these aggregated data sets:
[TO BE INSERTED]
