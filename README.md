# Island Trails

[Island Trails](https://islandtrails.ca) is a not-for-profit, non-government, organization which actively supports the promotion,
development and enhancement of the trails on Prince Edward Island for healthy recreation and educational use.

This repository contains route maps and related information for the 11 trails that Island Trails manages or supports directly,
as well as other significant walking trails on Prince Edward Island managed by third parties.

The route maps are derived from [GIS data gathered in the field](https://arcg.is/1K1nDf2) by Recreation PEI and post-processed
by the PEI Department of Transportation and Infrastructure. Each trail's route was extraced from ESRI shapefiles extracted from
the Island-wide coverage of that project, and the name of trail segments and trail surface preserved in the metadata. Minor
edits to the Recreation PEI survey routes were made to connect trails to adjacent roads, to merge duplicate points, and to
remove artifacts.

## Updating OpenStreetMap

The process of updating OpenStreetMap proceeded, in March through May of 2023, with updates contracted to [Reinvented Inc.](https://reinvented.net) and carried out by Peter Rukavina.
 May 2023, used to update these trails' routes in OpenStreetMap, as follows, for each trail:

* Shapefiles were wxtracted from the [master Recreation PEI shapefile](https://github.com/islandtrails/trails/tree/main/recreation_pei/shp) and saved, preserving the T_Type, Trail, T_Name, and Manager tags.
* In the [JOSM Editor](https://josm.openstreetmap.de), OpenStreetMap data for each trail's area was downloaded, along with the extracted shapefile for the trail (as a separate JOSM layer, using the Open Data plugin).
* If the trail *already* existed in OpenStreetMap, existing ways in OpenStreetMap for the trail were deleted, with metadata and relation membership saved for later reference.
* In the shapefile layer for the trail, the ways for each were selected (Find > type:way) and the following metadata added:
  * foot:yes
  * for multi-use trails, bicycle:yes
  * highway:path
  * name:[trail segment name or trail name]
  * surface:
    * "T_Type=Natural*" becomes "surface:dirt"
    * "T_Type=Boardwalk" becomes "surface:wood"
    * "T_Type=Hard*" becomes "surface:asphalt"
    * "T_Type=Improved*" becomes "surface:gravel"
* The ways from the imported shapefile for each trail were copied and pasted into the OSM layer.
* If an existing trail relation was present in OpenStreetMap, metadata and relation membership for each trail were updated, with the following translations:
  * "Trail:[trail name]" becomes "name:[trail name]"
  * "network" was set to "lwn" (Local Walking Network)
  * "operator" was set to "Island Trails" or the trail manager (Island Nature Trust, Provincial Forestry, etc.)
  * For trails that form a loop, "roundtrip:yes" was set.
  * "source" set to "survey"
  * route:hiking
  * type:route
* If an existing trail relation was *not* present, then a *new* relation was created, with the following metadata:
  * "Trail:[trail name]" becomes "name:[trail name]"
  * "network" was set to "lwn" (Local Walking Network)
  * "operator" was set to "Island Trails" or the trail manager (Island Nature Trust, Provincial Forestry, etc.)
  * route:hiking
  * type:route
* The built-in JOSM warnings and errors were used to clean up inconsistencies from the imported shapefile; this mostly flagged situations in the Recreation PEI imported shapefiles where multiple points appeared at the same place.
* The resulting relation and its ways were uploaded to OSM, with a note indicating the update from Recreation PEI survey.

## Island Trails Managed Trails

These trails are managed by [Island Trails](https://islandtrails.ca) and more detailed information on each [is available on the Island Trails website](https://islandtrails.ca/trails/our-island-trails/).

These trails are collected together in an OpenStreetMap super-relation called [Island Trails](https://www.openstreetmap.org/relation/15803585) ([Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15803585)).

| Trail | Shapefile | GPX | OpenStreetMap | Waymarked Trails |
|----|---|---|---|---|
| [Black Marsh](https://islandtrails.ca/trail/north-cape-nature-trail/) | [Shapefile](https://github.com/islandtrails/trails/tree/main/black_marsh/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/black_marsh/gpx/black-marsh.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15648482) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15648482&type=relation&map=15.0/47.0494/-64.0048)
| [Bonshaw](https://islandtrails.ca/trail/bonshaw-trails/) | [Shapefile](https://github.com/islandtrails/trails/tree/main/bonshaw/shp)| [GPX](https://github.com/islandtrails/trails/blob/main/bonshaw/gpx/bonshaw.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5739225) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5739225&map=14.0/46.211/-63.3431)
| [Boughton River](https://islandtrails.ca/trails/boughton-river-trail) | [Shapefile](https://github.com/islandtrails/trails/tree/main/boughton_river/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/boughton_river/gpx/boughton_river.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5685388) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5685388&type=relation&map=14.0/46.2991/-62.5166)
| [Breadalbane](https://islandtrails.ca/trails/breadalbane-nature-trail) | [Shapefile](https://github.com/islandtrails/trails/tree/main/breadalbane/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/breadalbane/gpx/breadalbane.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5689854) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5689854&type=relation&map=15.0/46.3576/-63.4903)
| [Dromore](https://islandtrails.ca/trails/dromore-woodland-trail) | [Shapefile](https://github.com/islandtrails/trails/tree/main/dromore/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/dromore/gpx/dromore.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5689296) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5689296&map=14.0/46.2965/-62.8261)
| [Forest Hill](https://islandtrails.ca/trails/forest-hill-trail) | [Shapefile](https://github.com/islandtrails/trails/tree/main/forest_hill/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/forest_hill/gpx/forest_hill.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5689271) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5689271&map=15.0/46.3543/-62.5175)
| [Forestview](https://islandtrails.ca/trails/forestview-trail) | [Shapefile](https://github.com/islandtrails/trails/tree/main/forestview/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/forestview/gpx/forestview.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/12272586) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=12272586&map=15.0/46.7282/-64.2637)
| [Gairloch](https://islandtrails.ca/trails/gairloch-road-trail) | [Shapefile](https://github.com/islandtrails/trails/tree/main/gairloch/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/gairloch/gpx/gairloch.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5689883) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5689883&map=16.0/46.0367/-62.8138)
| [Selkirk Forest](https://islandtrails.ca/trail/selkirk-forest-walking-trail/) | [Shapefile](https://github.com/islandtrails/trails/tree/main/selkirk_forest/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/selkirk_forest/gpx/selkirk_forest.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5757133) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5757133&map=16.0/46.0522/-62.7981)
| [Strathgartney](https://islandtrails.ca/trails/bonshaw-trails) | [Shapefile](https://github.com/islandtrails/trails/tree/main/strathgartney/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/strathgartney/gpx/strathgartney.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5741285) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5741285&map=15.0/46.2063/-63.339)
| [Winter River](https://islandtrails.ca/trails/winter-river-trail) | [Shapefile](https://github.com/islandtrails/trails/tree/main/winter_river/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/winter_river/gpx/winter_river.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/12264597) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=12264597&map=15.0/46.3556/-63.0644)

## Other Prince Edward Island Trails — Updated in OpenStreetMap

These trails are not managed by Island Trails, but were also updated in OpenStreetMap from the Recreation PEI survey:

| Trail | Shapefile  | GPX | OpenStreetMap | Waymarked Trails |
|----|---|---|---|---|
| Andrews Pond | [Shapefile](https://github.com/islandtrails/trails/tree/main/andrews_pond/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/andrews_pond/gpx/andrews_pond.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15775284) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15775284&type=relation&map=15.0/46.2732/-63.1025) |
| Ardgowan | [Shapefile](https://github.com/islandtrails/trails/tree/main/ardgowan/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/ardgowan/gpx/ardgowan.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15771798) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15771798&type=relation&map=18.0/46.2517/-63.1265) |
| Auburn | [Shapefile](https://github.com/islandtrails/trails/tree/main/auburn/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/auburn/gpx/auburn.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5746789) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5746789&map=17.0/46.2906/-62.9144) |
| Barbara Green  | [Shapefile](https://github.com/islandtrails/trails/tree/main/barbara_green/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/barbara_green/gpx/barbara_green.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15771890) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15771890&type=relation&map=18.0/46.2421/-63.5484) |
| Beach Grove AT | [Shapefile](https://github.com/islandtrails/trails/tree/main/beach_grove_at/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/beach_grove_at/gpx/beach_grove_at.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15775459) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15775459&map=18.0/46.2546/-63.1695) |
| Beach Grove | [Shapefile](https://github.com/islandtrails/trails/tree/main/beach_grove/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/beach_grove/gpx/beach_grove.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15775458) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15775458&map=17.0/46.2549/-63.1728) |
| Beck Trail | [Shapefile](https://github.com/islandtrails/trails/tree/main/beck_trail/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/beck_trail/gpx/beck_trail.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5752497) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5752497&map=16.0/46.0369/-62.6155) |
| Brackley Commons | [Shapefile](https://github.com/islandtrails/trails/tree/main/brackley_commons/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/brackley_commons/gpx/brackley_commons.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15776261) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15776261&type=relation&map=18.0/46.2941/-63.1395) |
| Camp Tamawaby | [Shapefile](https://github.com/islandtrails/trails/tree/main/camp_tamawaby/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/camp_tamawaby/gpx/camp_tamawaby.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5746830) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5746830&type=relation&map=17.0/46.4786/-63.9578)
| Cardigan | [Shapefile](https://github.com/islandtrails/trails/tree/main/cardigan/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/cardigan/gpx/cardigan.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/12234572) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=12234572&type=relation&map=15.0/46.2382/-62.6275)
| Cedar Dunes | [Shapefile](https://github.com/islandtrails/trails/tree/main/cedar_dunes/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/cedar_dunes/gpx/cedar_dunes.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/12343425) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=12343425&type=relation&map=17.0/46.6197/-64.3798)
| Devil's Punchbowl | [Shapefile](https://github.com/islandtrails/trails/tree/main/devils_punchbowl/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/devils_punchbowl/gpx/devils_punchbowl.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5757169) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5757169&type=relation&map=17.0/46.4095/-63.4853)
| Dunk River | [Shapefile](https://github.com/islandtrails/trails/tree/main/dunk_river/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/dunk_river/gpx/dunk_river.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/12250332) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=12250332&map=16.0/46.3445/-63.6205)
| Foxley River | [Shapefile](https://github.com/islandtrails/trails/tree/main/foxley_river/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/foxley_river/gpx/foxley_river.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15766456) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15766456&map=17.0/46.6996/-64.0527)
| Glenaladale | [Shapefile](https://github.com/islandtrails/trails/tree/main/glenaladale/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/glenaladale/gpx/glenaladale.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15781607) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15781607&map=16.0/46.3607/-62.963)
| Gotjinaig Otaotioagl | [Shapefile](https://github.com/islandtrails/trails/tree/main/gotjinaig_otaotioagl/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/gotjinaig_otaotioagl/gpx/gotjinaig_otaotioagl.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/13909086) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=13909086&map=14.0/46.6171/-63.8596)
| Harvey Moore | [Shapefile](https://github.com/islandtrails/trails/tree/main/harvey_moore/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/harvey_moore/gpx/harvey_moore.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/12745136) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=12745136&map=17.0/46.1088/-62.6306)
| Heather Moyse| [Shapefile](https://github.com/islandtrails/trails/tree/main/heather_moyse/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/heather_moyse/gpx/heather_moyse.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15788726) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15788726&type=relation)
| Hermitage Creek | [Shapefile](https://github.com/islandtrails/trails/tree/main/hermitage_creek/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/hermitage_creek/gpx/hermitage_creek.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/6863918) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=6863918&map=16.0/46.2561/-63.1502)
| Hillsborough Park | [Shapefile](https://github.com/islandtrails/trails/tree/main/hillsborough_park/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/hillsborough_park/gpx/hillsborough_park.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15794210) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15794210&map=18.0/46.26/-63.0975)
| Hillsborough River | [Shapefile](https://github.com/islandtrails/trails/tree/main/hillsborough_river/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/hillsborough_river/gpx/hillsborough_river.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/8442984) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=8442984&map=16.0/46.2567/-63.0979)
| Hyde Pond | [Shapefile](https://github.com/islandtrails/trails/tree/main/hyde_pond/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/hyde_pond/gpx/hyde_pond.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15794246) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15794246&map=16.0/46.2224/-63.2171)
| John A Hogg | [Shapefile](https://github.com/islandtrails/trails/tree/main/john_a_hogg/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/john_a_hogg/gpx/john_a_hogg.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15794254) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15794254&map=16.0/46.4257/-63.6261)
| Kelly's | [Shapefile](https://github.com/islandtrails/trails/tree/main/kellys_trail/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/kellys_trail/gpx/kellys_trail.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15794856) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15794856&type=relation&map=17.0/46.2995/-62.8176)
| Kildare Forest  | [Shapefile](https://github.com/islandtrails/trails/tree/main/kildare_forest/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/kildare_forest/gpx/kildare_forest.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15794894) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15794894&map=16.0/46.8347/-64.0613)
| MacDonald's River | [Shapefile](https://github.com/islandtrails/trails/tree/main/macdonalds_river/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/macdonalds_river/gpx/macdonalds_river.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15766399) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15766399&map=14.0/46.68/-64.0552)
| MacPhail Woods | [Shapefile](https://github.com/islandtrails/trails/tree/main/macphail_woods/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/macphail_woods/gpx/macphail_woods.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/6845796) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=6845796&map=17.0/46.1596/-62.8225)
| Mark Arendz | [Shapefile](https://github.com/islandtrails/trails/tree/main/mark_arendz/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/mark_arendz/gpx/mark_arendz.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15795341) | [Waymarked Trails](https://cycling.waymarkedtrails.org/#route?id=15795341&map=15.0/46.2702/-63.4199)
| Mill River | [Shapefile](https://github.com/islandtrails/trails/tree/main/mill_river/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/mill_river/gpx/mill_river.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15795829) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15795829&type=relation&map=16.0/46.7417/-64.1635)
| Mooney's Pond | [Shapefile](https://github.com/islandtrails/trails/tree/main/mooneys_pond/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/mooneys_pond/gpx/mooneys_pond.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15795846) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15795846&type=relation&map=16.0/46.2952/-62.7727)
| New Harmony| [Shapefile](https://github.com/islandtrails/trails/tree/main/new_harmony/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/new_harmony/gpx/new_harmony.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/12239117) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=12239117&map=15.0/46.3884/-62.2079)
| North Rustico | [Shapefile](https://github.com/islandtrails/trails/tree/main/north_rustico/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/north_rustico/gpx/north_rustico.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15796218) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15796218&type=relation&map=18.0/46.4637/-63.3083)
| PEI National Park: Greenwich | [Shapefile](https://github.com/islandtrails/trails/tree/main/pei_national_park/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/pei_national_park/gpx/greenwich.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5757127) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5757127&map=15.0/46.4483/-62.6998)
| Queen Elizabeth Park | [Shapefile](https://github.com/islandtrails/trails/tree/main/queen_elizabeth_park/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/queen_elizabeth_park/gpx/queen_elizabeth_park.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/8455223) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=8455223&map=17.0/46.248/-63.1525)
| Rackham's Community Pond | [Shapefile](https://github.com/islandtrails/trails/tree/main/rackhams_community_pond/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/rackhams_community_pond/gpx/rackhams_community_pond.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/12490749) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=12490749&map=16.0/46.3675/-63.2875)
| Robert L. Cotton | [Shapefile](https://github.com/islandtrails/trails/tree/main/robertcotton/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/robertcotton/gpx/robertcotton.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15802968) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15802968&map=17.0/46.2339/-63.0953)
| Roma | [Shapefile](https://github.com/islandtrails/trails/tree/main/roma/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/roma/gpx/roma.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15803065) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15803065&map=16.0/46.1854/-62.5641)
| Roseville Pond | [Shapefile](https://github.com/islandtrails/trails/tree/main/roseville_pond/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/roseville_pond/gpx/roseville_pond.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15802904) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15802904&map=17.0/46.8247/-64.2636)
| Rotary Friendship Park | [Shapefile](https://github.com/islandtrails/trails/tree/main/rotary_friendship_park/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/rotary_friendship_park/gpx/rotary_friendship_park.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/12287872) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=12287872&type=relation&map=15.0/46.4086/-63.7648)
| Skmaqn | [Shapefile](https://github.com/islandtrails/trails/tree/main/skmaqn/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/skmaqn/gpx/skmaqn.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/6889080) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=6889080&map=16.0/46.1956/-63.1392)
| Slemon Park | [Shapefile](https://github.com/islandtrails/trails/tree/main/slemon_park/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/slemon_park/gpx/slemon_park.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15800189) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15800189&map=16.0/46.433/-63.827)
| Souris Striders | [Shapefile](https://github.com/islandtrails/trails/tree/main/souris_striders/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/souris_striders/gpx/souris_striders.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15803228) | [Waymarked Trails](https://slopes.waymarkedtrails.org/#route?id=15803228&map=15.0/46.4014/-62.2654)
| Summerside Connector | [Shapefile](https://github.com/islandtrails/trails/tree/main/summerside_connector/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/summerside_connector/gpx/summerside_connector.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15800880) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15800880&map=16.0/46.3931/-63.78)
| Townshend | [Shapefile](https://github.com/islandtrails/trails/tree/main/townshend/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/townshend/gpx/townshend.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/12303381) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=12303381&map=15.0/46.4182/-62.2766)
| Trout River Community | [Shapefile](https://github.com/islandtrails/trails/tree/main/trout_river_community/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/trout_river_community/gpx/trout_river_community.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15798311) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15798311&map=17.0/46.4212/-63.4392)
| Trout River | [Shapefile](https://github.com/islandtrails/trails/tree/main/trout_river/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/trout_river/gpx/trout_river.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/12346599) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=12346599&map=15.0/46.6975/-64.1709)
| Tryon River | [Shapefile](https://github.com/islandtrails/trails/tree/main/tryon_river/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/tryon_river/gpx/tryon_river.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15771889) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15771889&map=17.0/46.2405/-63.5448)
| Tryon Extension | [Shapefile](https://github.com/islandtrails/trails/tree/main/tryon_trail/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/tryon_trail/gpx/tryon_trail.gpx) | [OpenStreetMap](https://www.openstreetmap.org/way/1165983403) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15771888&map=16.0/46.2441/-63.5523)
| Upton | [Shapefile](https://github.com/islandtrails/trails/tree/main/upton/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/upton/gpx/upton.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/15775460) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=15775460&type=relation&map=16.0/46.2574/-63.1736)
| Valleyfield | [Shapefile](https://github.com/islandtrails/trails/tree/main/valleyfield/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/valleyfield/gpx/valleyfield.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/5746800) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=5746800&type=relation&map=16.0/46.1371/-62.7194)
| Victoria Park | [Shapefile](https://github.com/islandtrails/trails/tree/main/victoria_park/shp) | [GPX](https://github.com/islandtrails/trails/blob/main/victoria_park/gpx/victoria_park.gpx) | [OpenStreetMap](https://www.openstreetmap.org/relation/6888473) | [Waymarked Trails](https://hiking.waymarkedtrails.org/#route?id=6888473&map=16.0/46.23/-63.1398)

## Other Prince Edward Island Trails - Not Updated

These trails, part of the Recreation PEI survey, have *not* been updated in OpenStreetMap, as they are minor, short, urban trails, boardwalks, or because a more complete and annotated version already existing in OpenStreetMap:

| Trail |
|----|
| AA MacDonald |
| Airport AT |
| Allisary Creek |
| AT Path |
| Blackbush |
| Borden-Carleton |
| Brackley |
| Browns Court |
| Cabot Beach |
| Cavendish AT |
| Cavendish Boardwalk |
| Centennial Park |
| Charlottetown Waterfront |
| Community Garden Park |
| Confederation Landing |
| Connaught Square |
| Duvar Trail |
| Farm Centre  |
| Fishermen's Haven  |
| Founders' Hall |
| Frank MacAulay Park |
| Gateway Village  |
| Glen Stewart School |
| Grand River  |
| Hillsborough Park |
| Hillsborough Square |
| Holland College  |
| Hunter River |
| Jesse Street |
| Keppoch Rd  |
| Kings Square |
| Lowther Park |
| MacKinnon Dr |
| MacRae Dr  |
| Hillside Meadow |
| Main Street  |
| Memorial Square |
| Montague Marina |
| Montgomery Park |
| New Glasgow  |
| North River  |
| Old Mill Park |
| Old Protestant Burial Grounds |
| Orlebar Park |
| Park Corner  |
| Park Street  |
| Peakes Quay |
| Riverview Estates |
| Riverside Dr |
| Robinsons Island |
| Rochford Square |
| Rustico  |
| Scotchfort |
| Shore Access |
| Simmons |
| Skyewater  |
| Skyview Park |
| Slemon Park Pathways |
| St Peters  |
| St Peters Rd |
| Stanhope  |
| Stratford TCH |
| Stratford  |
| Summerside Baywalk |
| Sunshine Meadows |
| Terry Fox |
| UPEI  |
| Upton Rd AT |


