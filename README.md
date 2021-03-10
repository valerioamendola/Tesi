# Tesi
setwd("TesiSGN")
###
library(sp)
###
library(raster)
###
library(rgdal)
###
library(rgeos)
###
library(maptools)
###
EU_parks <- rgdal::readOGR("WDPA_WDOECM_EU_shp-polygons.shp")
###
EU_parks_II <- EU_parks[EU_parks$IUCN_CAT == 'II',]
###
Ecoreg <- rgdal::readOGR("Ecoregions2017.shp")
###
Ecoreg <- rgdal::readOGR("Ecoregions2017.shp")
###
Inters <- intersect(EU_parks_II, Ecoreg)
###
Inters$area <- area(Inters) / 1000000
###
