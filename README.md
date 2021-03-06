# Leaflet Environmental Layers

## The library is integrated to following places : 

https://mapknitter.org/

https://publiclab.org/maps/

##### NPM : 

https://www.npmjs.com/package/leaflet-environmental-layers

##### Bower :
Seach leaflet-environmental-layers here : https://bower.io/search/



## About :

The information of each layer can be found here :
https://publiclab.org/notes/sagarpreet/06-06-2018/leaflet-environmental-layer-library



| Layer Name | Color |
| --- | --- |
| PurpleAirLayer-HeatMap | #8b0000 |
| PurpleAirLayer-Markers | #800080 |
| SkyTruth | #ff0000 |
| Fractracker | #ffff00 |
| ToxicRelease | #008000 |
| OdorReport | #ff00ff |
| MapKnitter | #D50039 |
| OpenInfraMap_Power | #ffc0cb |
| OpenInfraMap_Telecom | #0000ff |
| OpenInfraMap_Petroleum | #a52a2a |
| OpenInfraMap_Water | #4B0082 |
| Justicemap_income | #006400 |
| JusticeMap_americanIndian | #800000 |
| JusticeMap_asian | #ffa500 |
| JusticeMap_black | #FFD700 |
| JusticeMap_multi | #ffc0cb |
| JusticeMap_hispanic | #DCDCDC |
| JusticeMap_nonWhite | #808080 |
| JusticeMap_white | #a52a2a |
| JusticeMap_plurality | #800000 |
| Clouds | #80dfff |
| clouds (classic) | #b3f0ff |
| precipitation | #00ff55 |
| precipitation (classic) | #00008b |
| rain | #8080ff |
| rain (classic) | #1a1aff |
| snow | #80ffe5 |
| pressure | #e62e00 |
| pressure contour (zoom in) | #ff3300 |
| temp | #ff3300 |
| wind | #00008b |
| Cities (zoom in) | #b3ffff |
| windrose (zoom in) | #008000 |


## Quick Setup : 

To set up the library first clone this repo to your local environment; then run 'npm install' to install all the neccessary packages required. Open examples/index.html to look at the preview of the library.


## Demo : 

Checkout this demo : https://publiclab.github.io/leaflet-environmental-layers/example/index.html#3/43.00/-46.23

## Features : 

#### Zoom or Pan

Click and drag the map to pan it. 

#### Change the Base Map and Overlay layers

Use the button on right-most corner to change the way the background of the map looks .

#### See More Data

Toggle certain layers on and off using the Layers button in the toolbar .

#### Click on a Point

Click on a point or marker on the map to learn more about it .

## Dependencies : 

### General (required for all layers) :

           <script src="../dist/LeafletEnvironmentalLayers.js"></script> 
           <link href="../node_modules/leaflet/dist/leaflet.css" rel="stylesheet">

### To use Wind Rose Layer : 

            <script src="../dist/windRoseLayer.js"></script> 
            <link href="../dist/LeafletEnvironmentalLayers.css" rel="stylesheet">

### To use Purple Layer :
			
			<script src="../node_modules/heatmap.js/build/heatmap.min.js"></script>
			<script src="../node_modules/leaflet-heatmap/leaflet-heatmap.js"></script>

  			
## Real Time Layers : 

1.) city (by openWeather) 
     
        var city = L.OWM.current({intervall: 15, minZoom: 3});

2.) WindRose (by openWeather)

        var windrose = L.OWM.current({intervall: 15, minZoom: 3, markerFunction: myWindroseMarker, popup: false, clusterSize:       50,imageLoadingBgUrl: 'https://openweathermap.org/img/w0/iwind.png' });
    windrose.on('owmlayeradd', windroseAdded, windrose); 
   
## Open Infra Map : 

##### OpenInfraMap_Power Layer : 
    
    var OpenInfraMap_Power = L.tileLayer('https://tiles-{s}.openinframap.org/power/{z}/{x}/{y}.png',{
        maxZoom: 18,
        attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>, <a href="http://www.openinframap.org/about.html">About OpenInfraMap</a>'
    });

##### OpenInfraMap_Petroleum Layer : 

    var OpenInfraMap_Petroleum = L.tileLayer('https://tiles-{s}.openinframap.org/petroleum/{z}/{x}/{y}.png', {
      maxZoom: 18,
      attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>, <a href="http://www.openinframap.org/about.html">About OpenInfraMap</a>'
    });

##### OpenInfraMap_Telecom Layer : 

    var OpenInfraMap_Telecom = L.tileLayer('https://tiles-{s}.openinframap.org/telecoms/{z}/{x}/{y}.png', {
      maxZoom: 18,
      attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>, <a href="http://www.openinframap.org/about.html">About OpenInfraMap</a>'
    });

##### OpenInfraMap_Water Layer : 

    var OpenInfraMap_Water = L.tileLayer('https://tiles-{s}.openinframap.org/water/{z}/{x}/{y}.png',{
      maxZoom: 18,
      attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>, <a href="http://www.openinframap.org/about.html">About OpenInfraMap</a>'
    });   

## Add Leaflet-Hash for easy sharing of map :    

### Steps To add : 

1.) Add link : 
    
    <script src="../node_modules/leaflet-hash/leaflet-hash.js"></script>

2.) Once you have initialized the map (an instance of L.Map), add the following code :

    // Assuming your map instance is in a variable called map
    var hash = new L.Hash(map);    

  Read more about Leaflet-Hash here : https://github.com/mlevans/leaflet-hash

