---
layout: category
author_profile: true
taxonomy: layered_intrusions
category: layered_intrusions
title: "Global layered intrusions"
permalink: /layeredintrusions/
header:
  image: "/images/bushmap.jpg"
---

<div id="wrap">
<iframe src="file:///C:/Users/Lenovo/Documents/layered-intrusions/index.html#2/-8.8/20.8" title="map" class="is-fullwidth" height="550px" width="800px"></iframe>
</div>

<html lang="en">
<head>
<meta charset="utf-8">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="viewport" content="initial-scale=1,user-scalable=no,maximum-scale=1,width=device-width">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-capable" content="yes">
<link rel="stylesheet" href="css/leaflet.css">
<link rel="stylesheet" href="css/qgis2web.css"><link rel="stylesheet" href="css/fontawesome-all.min.css">
<link rel="stylesheet" href="css/MarkerCluster.css">
<link rel="stylesheet" href="css/MarkerCluster.Default.css">
<link rel="stylesheet" href="css/leaflet-search.css">
<link rel="stylesheet" href="css/leaflet-measure.css">
<style>
        #map {
            width: 1336px;
            height: 866px;
        }
        </style>
        <title></title>
    </head>
    <body>
        <div id="map">
        </div>
        <script src="js/qgis2web_expressions.js"></script>
        <script src="js/leaflet.js"></script>
        <script src="js/leaflet.rotatedMarker.js"></script>
        <script src="js/leaflet.pattern.js"></script>
        <script src="js/leaflet-hash.js"></script>
        <script src="js/Autolinker.min.js"></script>
        <script src="js/rbush.min.js"></script>
        <script src="js/labelgun.min.js"></script>
        <script src="js/labels.js"></script>
        <script src="js/leaflet-measure.js"></script>
        <script src="js/leaflet.markercluster.js"></script>
        <script src="js/leaflet-search.js"></script>
        <script src="data/Craton_Outlines_1.js"></script>
        <script src="data/LMI_GI_2.js"></script>
        <script>
        var highlightLayer;
        function highlightFeature(e) {
            highlightLayer = e.target;
            highlightLayer.openPopup();
        }
        var map = L.map('map', {
            zoomControl:true, maxZoom:28, minZoom:1
        })
        var hash = new L.Hash(map);
        map.attributionControl.setPrefix('<a href="https://github.com/tomchadwin/qgis2web" target="_blank">qgis2web</a> &middot; <a href="https://leafletjs.com" title="A JS library for interactive maps">Leaflet</a> &middot; <a href="https://qgis.org">QGIS</a>');
        var autolinker = new Autolinker({truncate: {length: 30, location: 'smart'}});
        var measureControl = new L.Control.Measure({
            position: 'topleft',
            primaryLengthUnit: 'meters',
            secondaryLengthUnit: 'kilometers',
            primaryAreaUnit: 'sqmeters',
            secondaryAreaUnit: 'hectares'
        });
        measureControl.addTo(map);
        document.getElementsByClassName('leaflet-control-measure-toggle')[0]
        .innerHTML = '';
        document.getElementsByClassName('leaflet-control-measure-toggle')[0]
        .className += ' fas fa-ruler';
        var bounds_group = new L.featureGroup([]);
        function setBounds() {
            if (bounds_group.getLayers().length) {
                map.fitBounds(bounds_group.getBounds());
            }
        }
        map.createPane('pane_GoogleTerrane_0');
        map.getPane('pane_GoogleTerrane_0').style.zIndex = 400;
        var layer_GoogleTerrane_0 = L.tileLayer('http://mt0.google.com/vt/lyrs=s&hl=en&x={x}&y={y}&z={z}', {
            pane: 'pane_GoogleTerrane_0',
            opacity: 1.0,
            attribution: '',
            minZoom: 1,
            maxZoom: 28,
            minNativeZoom: 0,
            maxNativeZoom: 18
        });
        layer_GoogleTerrane_0;
        map.addLayer(layer_GoogleTerrane_0);
        function pop_Craton_Outlines_1(feature, layer) {
            layer.on({
                mouseout: function(e) {
                    if (typeof layer.closePopup == 'function') {
                        layer.closePopup();
                    } else {
                        layer.eachLayer(function(feature){
                            feature.closePopup()
                        });
                    }
                },
                mouseover: highlightFeature,
            });
            var popupContent = '<table>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['id'] !== null ? autolinker.link(feature.properties['id'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['InPoly_FID'] !== null ? autolinker.link(feature.properties['InPoly_FID'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['SmoPgnFlag'] !== null ? autolinker.link(feature.properties['SmoPgnFlag'].toLocaleString()) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_Craton_Outlines_1_0() {
            return {
                pane: 'pane_Craton_Outlines_1',
                opacity: 1,
                color: 'rgba(35,35,35,1.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1.0, 
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(196,60,57,0.0)',
                interactive: false,
            }
        }
        map.createPane('pane_Craton_Outlines_1');
        map.getPane('pane_Craton_Outlines_1').style.zIndex = 401;
        map.getPane('pane_Craton_Outlines_1').style['mix-blend-mode'] = 'normal';
        var layer_Craton_Outlines_1 = new L.geoJson(json_Craton_Outlines_1, {
            attribution: '',
            interactive: false,
            dataVar: 'json_Craton_Outlines_1',
            layerName: 'layer_Craton_Outlines_1',
            pane: 'pane_Craton_Outlines_1',
            onEachFeature: pop_Craton_Outlines_1,
            style: style_Craton_Outlines_1_0,
        });
        bounds_group.addLayer(layer_Craton_Outlines_1);
        map.addLayer(layer_Craton_Outlines_1);
        function pop_LMI_GI_2(feature, layer) {
            layer.on({
                mouseout: function(e) {
                    if (typeof layer.closePopup == 'function') {
                        layer.closePopup();
                    } else {
                        layer.eachLayer(function(feature){
                            feature.closePopup()
                        });
                    }
                },
                mouseover: highlightFeature,
            });
            var popupContent = '<table>\
                    <tr>\
                        <td colspan="2"><strong>Intrusion</strong><br />' + (feature.properties['Intrusion'] !== null ? autolinker.link(feature.properties['Intrusion'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Type'] !== null ? autolinker.link(feature.properties['Type'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Country'] !== null ? autolinker.link(feature.properties['Country'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Setting'] !== null ? autolinker.link(feature.properties['Setting'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Latitude'] !== null ? autolinker.link(feature.properties['Latitude'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Longitude'] !== null ? autolinker.link(feature.properties['Longitude'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">Extent</th>\
                        <td>' + (feature.properties['Extent'] !== null ? autolinker.link(feature.properties['Extent'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">Thickness</th>\
                        <td>' + (feature.properties['Thickness'] !== null ? autolinker.link(feature.properties['Thickness'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">Age</th>\
                        <td>' + (feature.properties['Age'] !== null ? autolinker.link(feature.properties['Age'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">Deposit</th>\
                        <td>' + (feature.properties['Deposit'] !== null ? autolinker.link(feature.properties['Deposit'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <th scope="row">Type_1</th>\
                        <td>' + (feature.properties['Type_1'] !== null ? autolinker.link(feature.properties['Type_1'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Tonnage'] !== null ? autolinker.link(feature.properties['Tonnage'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Grade'] !== null ? autolinker.link(feature.properties['Grade'].toLocaleString()) : '') + '</td>\
                    </tr>\
                    <tr>\
                        <td colspan="2">' + (feature.properties['Continent'] !== null ? autolinker.link(feature.properties['Continent'].toLocaleString()) : '') + '</td>\
                    </tr>\
                </table>';
            layer.bindPopup(popupContent, {maxHeight: 400});
        }

        function style_LMI_GI_2_0() {
            return {
                pane: 'pane_LMI_GI_2',
                radius: 4.0,
                opacity: 1,
                color: 'rgba(35,35,35,1.0)',
                dashArray: '',
                lineCap: 'butt',
                lineJoin: 'miter',
                weight: 1,
                fill: true,
                fillOpacity: 1,
                fillColor: 'rgba(213,180,60,1.0)',
                interactive: true,
            }
        }
        map.createPane('pane_LMI_GI_2');
        map.getPane('pane_LMI_GI_2').style.zIndex = 402;
        map.getPane('pane_LMI_GI_2').style['mix-blend-mode'] = 'normal';
        var layer_LMI_GI_2 = new L.geoJson(json_LMI_GI_2, {
            attribution: '',
            interactive: true,
            dataVar: 'json_LMI_GI_2',
            layerName: 'layer_LMI_GI_2',
            pane: 'pane_LMI_GI_2',
            onEachFeature: pop_LMI_GI_2,
            pointToLayer: function (feature, latlng) {
                var context = {
                    feature: feature,
                    variables: {}
                };
                return L.circleMarker(latlng, style_LMI_GI_2_0(feature));
            },
        });
        var cluster_LMI_GI_2 = new L.MarkerClusterGroup({showCoverageOnHover: false,
            spiderfyDistanceMultiplier: 2});
        cluster_LMI_GI_2.addLayer(layer_LMI_GI_2);

        bounds_group.addLayer(layer_LMI_GI_2);
        cluster_LMI_GI_2.addTo(map);
        setBounds();
        map.addControl(new L.Control.Search({
            layer: cluster_LMI_GI_2,
            initial: false,
            hideMarkerOnCollapse: true,
            propertyName: 'Intrusion'}));
        document.getElementsByClassName('search-button')[0].className +=
         ' fa fa-binoculars';
        </script>
    </body>
</html>