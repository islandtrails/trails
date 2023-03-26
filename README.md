# Island Trails

[Island Trails](https://islandtrails.ca) is a not-for-profit, non-government, organization which actively supports the promotion,
development and enhancement of the trails on Prince Edward Island for healthy recreation and educational use.

This repository contains route maps and related information for the 11 trails that Island Trails manages or supports directly.

The route maps are derived from [GIS data gathered in the field](https://arcg.is/1K1nDf2) by Recreation PEI and processed
by the PEI Department of Transportation and Infrastructure. Each trail's route was extraced from ESRI shapefiles extracted from
the Island-wide coverage of that project.

| Trail Website  | Shapefile  | OpenStreetMap |
|----|---|
| [Black Marsh](https://islandtrails.ca/trail/north-cape-nature-trail/) | [Shapefile](https://github.com/islandtrails/trails/tree/main/black_marsh/shp) | [OpenStreetMap](https://www.openstreetmap.org/relation/15648482#map=15/47.0494/-64.0048)
| [Bonshaw](https://islandtrails.ca/trail/bonshaw-trails/)
| [Boughton River](https://islandtrails.ca/trails/boughton-river-trail)
| [Breadalbane](https://islandtrails.ca/trails/breadalbane-nature-trail)
| [Dromore](https://islandtrails.ca/trails/dromore-woodland-trail)
| [Forest Hill](https://islandtrails.ca/trails/forest-hill-trail)
| [Forestview](https://islandtrails.ca/trails/forestview-trail)
| [Gairloch](https://islandtrails.ca/trails/gairloch-road-trail)
| [Selkirk Forest](https://islandtrails.ca/trail/selkirk-forest-walking-trail/)
| [Strathgartney](https://islandtrails.ca/trails/bonshaw-trails)
| [Winter River](https://islandtrails.ca/trails/winter-river-trail)

## Updating OpenStreetMap

These layers were, in March 2023, used to update these trails' routes in OpenStreetMap, as follows:

1. The JOSM editor, with the OpenData plugin, was used to download the OSM data and to open the shapefile for each trail.
2. Existing ways in OSM for each trail were deleted, with metadata and relation membership saved for later reference.
3. The ways from the shapefile for each trail were copied and pasted into the OSM layer.
4. Metadata and relation membership for each trail were updated.
5. The resulting layer was uploaded to OSM.
