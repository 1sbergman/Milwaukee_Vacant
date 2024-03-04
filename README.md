# Milwaukee_Vacant

Vacant Buildings and Race in Census Tracts in Milwaukee, Wisconsin

## Project Contents



- [Data Source](#data-source)
- [Purpose](#purpose)
- [Mapmaking Process](#mapmaking-process)
- [Map Summary](#map-summary)
- [Final Map](#final-project-link) 

***

### Data Source

[Vacant Buildings Data](https://data.milwaukee.gov/dataset/accelavacantbuilding)

[TIGER/Line Census Tracts](https://www.census.gov/cgi-bin/geo/shapefiles/index.php)

[Census Data for Tracts](https://data.census.gov/table?g=050XX00US55079$1400000)

* Initial Data projection: NAD83 (EPSG: 4269)
* Final Map projection: NAD83(2011) Wisconsin Transverse Mercator (EPSG: 6610)


### Purpose

[Studies](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3665973/https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3665973/) have shown a clear link between vacant land/vacant buildings and a number of negative effects on the surrounding community, including crime, loss of tax revenue for schools, and rats. I wanted to study the racial component of those effects on the City of Milwaukee, Wisconsin. By demonstrating a link between communities of color and vacant building sites in the city, we can show the social injustices created by urban decay and the need for redevelopment to solve these problems.

### Mapmaking Process

After downloading the data, and deciding on my projection (I went with NAD83(2011) Wisconsin Transverse Mercator (EPSG: 6610)), the first thing I did was notice there was no spatial aspect of the vacant buildings data, but there were addresses, so I had to geocode. The geocoder in QGIS was not working for me, so I brought it into ArcGIS instead, which did the trick.
 [Geocoding](ScreenShots/geocodeservice.JPG)

 I copied the newly geocoded points file back into QGIS and added it to the [map](ScreenShots/vacantbuildingsgeocoded.JPG). I then used the Kernel Density heatmap tool to create a [heatmap](ScreenShots/heatmap.JPG) of all the vacant buildings. After that I went into excel and [fomatted](ScreenShots/excelpopfile.JPG) the census data with population by race for census tracts in Milwaukee county in order to join it to the census tract shapefile from the TIGER/Line data. I lined it up so that the "[Geography](ScreenShots/excelpopfileexplained.JPG)" field from the spreadsheet could be joined to the "GEOIDFQ20" field. I then created a variable equal to the proportion of people who answered the race question on the census with something other than "White Only" in order to look at the overlap between communities with people of color and these vacant buildings. I symbolized the racial data with a red-yellow color [ramp](ScreenShots/milwaukeetractssymbolized.JPG) and overlaid the heat map on that with 65% opacity to produce my final result.




### Map summary

The areas on the map with a high density of vacant buildings overlays strongly onto the areas of the map with a high proportion of the population identifying as something other than "White Only". More work would need to be done to establish a firm mathematical correlation, but it certainly looks as if there is a connection between the two variables.

## Final Project Link



Please view the [final map online](https://1sbergman.github.io/Milwaukee_Vacant/index.html)