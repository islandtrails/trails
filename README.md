# Island Trails

[Island Trails](https://islandtrails.ca) is a not-for-profit, non-government, organization which actively supports the promotion,
development and enhancement of the trails on Prince Edward Island for healthy recreation and educational use.

This repository contains route maps and related information for the 11 trails that Island Trails manages or supports directly.

The route maps are derived from [GIS data gathered in the field](https://arcg.is/1K1nDf2) by Recreation PEI and processed
by the PEI Department of Transportation and Infrastructure. Each trail's route was extraced from ESRI shapefiles extracted from
the Island-wide coverage of that project, and the name of trail segments and trail surface preserved in the metadata.

| Trail Website  | Shapefile  | OpenStreetMap | Waymwarked Trails |
|----|---|---|---|
| [Black Marsh](https://islandtrails.ca/trail/north-cape-nature-trail/) | [Shapefile](https://github.com/islandtrails/trails/tree/main/black_marsh/shp) | [OpenStreetMap](https://www.openstreetmap.org/relation/15648482#map=15/47.0494/-64.0048) | [Waymwarked Trails](https://hiking.waymarkedtrails.org/#route?id=15648482&type=relation&map=15.0/47.0494/-64.0048)
| [Bonshaw](https://islandtrails.ca/trail/bonshaw-trails/) | [Shapefile](https://github.com/islandtrails/trails/tree/main/bonshaw/shp)| [OpenStreetMap](https://www.openstreetmap.org/relation/5739225) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5739225&map=14.0/46.211/-63.3431)
| [Boughton River](https://islandtrails.ca/trails/boughton-river-trail) | [Shapefile](https://github.com/islandtrails/trails/tree/main/boughton-river/shp) | [OpenStreetMap](https://www.openstreetmap.org/relation/5685388) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5685388&type=relation&map=14.0/46.2991/-62.5166)
| [Breadalbane](https://islandtrails.ca/trails/breadalbane-nature-trail) | [Shapefile](https://github.com/islandtrails/trails/tree/main/breadalbane/shp) | [OpenStreetMap](https://www.openstreetmap.org/relation/5689854#map=15/46.3576/-63.4903) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5689854&type=relation&map=15.0/46.3576/-63.4903)
| [Dromore](https://islandtrails.ca/trails/dromore-woodland-trail) | [Shapefile](https://github.com/islandtrails/trails/tree/main/dromore/shp)  | [OpenStreetMap](https://www.openstreetmap.org/relation/5689296#map=14/46.2965/-62.8261) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5689296&map=14.0/46.2965/-62.8261)
| [Forest Hill](https://islandtrails.ca/trails/forest-hill-trail) | [Shapefile](https://github.com/islandtrails/trails/tree/main/forest-hill-trail/shp) | [OpenStreetMap](https://www.openstreetmap.org/relation/5689271#map=15/46.3543/-62.5175) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5689271&map=15.0/46.3543/-62.5175)
| [Forestview](https://islandtrails.ca/trails/forestview-trail) | [Shapefile](https://github.com/islandtrails/trails/tree/main/forestview-trail/shp) | [OpenStreetMap](https://www.openstreetmap.org/relation/12272586) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=12272586&map=15.0/46.7282/-64.2637)
| [Gairloch](https://islandtrails.ca/trails/gairloch-road-trail)
| [Selkirk Forest](https://islandtrails.ca/trail/selkirk-forest-walking-trail/) | [Shapefile](https://github.com/islandtrails/trails/tree/main/selkirk_forest/shp) | [OpenStreetMap](https://www.openstreetmap.org/relation/5757133#map=16/46.0513/-62.7981) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5757133&map=16.0/46.0522/-62.7981)
| [Strathgartney](https://islandtrails.ca/trails/bonshaw-trails) | [Shapefile](https://github.com/islandtrails/trails/tree/main/strathgartney/shp) | [OpenStreetMap](https://www.openstreetmap.org/relation/5741285#map=15/46.2063/-63.3390) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5741285&map=15.0/46.2063/-63.339)
| [Winter River](https://islandtrails.ca/trails/winter-river-trail)

## Updating OpenStreetMap

These layers were, in March 2023, used to update these trails' routes in OpenStreetMap, as follows:

1. Downloaded the OSM data for each trail, plus the shapefile for each trail (using the Open Data plugin) into JOSM.
2. Existing ways in OSM for each trail were deleted, with metadata and relation membership saved for later reference.
3. The ways from the shapefile for each trail were copied and pasted into the OSM layer.
4. Metadata and relation membership for each trail were updated, with the following translations:
 * "T_Type=Natural Walking" becomes "surface:dirt"
 * "T_Type=Boardwalk" becomes "surface:wood"
 * "Trail:[trail name]" becomes "name:[trail name]"
5. The built-in JOSM warnings and errors were used to clean up inconsistencies in the imported shapefile.
6. The resulting layer was uploaded to OSM, maintaining the original relation.
