---
title: Radar backscatter for channel roughness analysis
layout: single
classes: wide
author_profile: true
header:
  image: /images/gee.jpg
  
---

<h1>1.	Google Earth Engine code for backscatter analysis</h1>




This is a template code for the backscatter for channel roughness analysis using the _Google Earth Engine_. Please adjust it to your need. Or, you can go to  <a href="https://code.earthengine.google.com/024619a64d82577f307f86798bcc1cc3">*https://code.earthengine.google.com/024619a64d82577f307f86798bcc1cc3*</a>.




First of all, generate an NDVI image which then will be draped above the Satellite image. This is to ensure that the polygons that we use in this analysis do not exceed the channel bank, hence resulting in distorded signal in radar bounce due to vegetation.


```java

// Calculate the NDVI from Landsat 8 data
var dataset = ee.ImageCollection('LANDSAT/LC08/C01/T1_8DAY_NDVI')
                  .filterDate('2018-01-01', '2020-01-31');
var colorized = dataset.select('NDVI');
print(colorized);
var ndvi=colorized.reduce(ee.Reducer.mean());
print(ndvi);

var ndvi_crop=ndvi.clip(mohand);

var colorizedVis = {
  min: 0.0,
  max: 1.0,
  palette: [
    'FFFFFF', 'CE7E45', 'DF923D', 'F1B555', 'FCD163', '99B718', '74A901',
    '66A000', '529400', '3E8601', '207401', '056201', '004C00', '023B01',
    '012E01', '011D01', '011301'
  ],
};
// Let's centre the map view over Mohand
Map.centerObject(moh, 11);
Map.addLayer(ndvi_crop, colorizedVis, 'NDVI');
```

```java
// Now let's explore Sentinel-1 data
// Filter the collection for the VV product from the Ascending track
var collectionVVas = ee.ImageCollection('COPERNICUS/S1_GRD')
    .filter(ee.Filter.eq('instrumentMode', 'IW'))
    .filter(ee.Filter.listContains('transmitterReceiverPolarisation', 'VV'))
    .filter(ee.Filter.eq('orbitProperties_pass', 'ASCENDING'))
    .filterBounds(mohand)
    .select(['VV']);
print(collectionVVas);

// Filter the collection for the VV product from the descending track
var collectionVVdes = ee.ImageCollection('COPERNICUS/S1_GRD')
    .filter(ee.Filter.eq('instrumentMode', 'IW'))
    .filter(ee.Filter.listContains('transmitterReceiverPolarisation', 'VV'))
    .filter(ee.Filter.eq('orbitProperties_pass', 'DESCENDING'))
    .filterBounds(mohand)
    .select(['VV']);
print(collectionVVdes);

// Adding the VV Ascending layer to the map
var VVas = collectionVVas.median();
//Map.addLayer(VVas, {min: -14, max: -1}, 'VVas');

// Adding the VV Descending layer to the map
var VVdes = collectionVVdes.median();
//Map.addLayer(VVdes, {min: -20, max: -7}, 'VVdes');

// Create a 3 band stack by selecting from different periods (in my case this is the dry season so the channel will exposed)
var VV1 = ee.Image(collectionVVas.filterDate('2017-10-30', '2018-05-01').median());
var VV2 = ee.Image(collectionVVas.filterDate('2018-10-30', '2019-05-01').median());
var VV3 = ee.Image(collectionVVas.filterDate('2019-10-30', '2020-05-01').median());
var VV41 = ee.Image(collectionVVas.filterDate('2016-10-30', '2017-05-01').median());
var VV51 = ee.Image(collectionVVas.filterDate('2015-10-30', '2016-05-01').median());
var VV61 = ee.Image(collectionVVas.filterDate('2014-10-30', '2015-05-01').median());

//Speckle filtering/smoothing
// Smooth the image by convolving with the boxcar kernel.
// Define a boxcar or low-pass kernel.
//A 3X3 Boxcar filter
var boxcar = ee.Kernel.square({radius: 1.5, units: 'pixels', normalize: true});

var VV1n = VV1.convolve(boxcar);
var VV2n = VV2.convolve(boxcar);
var VV3n = VV3.convolve(boxcar);
var VV41n = VV41.convolve(boxcar);
var VV51n = VV51.convolve(boxcar);
var VV61n = VV61.convolve(boxcar);

var s1 = ee.ImageCollection([VV1n, VV2n, VV3n, VV41n, VV51n, VV61n]).median();
//Map.addLayer(s1, {min: -14, max: -1}, 'S1');


// Create a 3 band stack by selecting from different periods (months)
var VV4 = ee.Image(collectionVVdes.filterDate('2021-06-01', '2021-06-30').median());
//var VV5 = ee.Image(collectionVVdes.filterDate('2013-06-01', '2013-06-30').median());
//var VV6 = ee.Image(collectionVVdes.filterDate('2013-06-01', '2013-06-30').median());
// Speckle filtering/smoothing
// Smooth the image by convolving with the boxcar kernel.
// Define a boxcar or low-pass kernel.
// A 3X3 Boxcar filter
var boxcar = ee.Kernel.square({radius: 1.5, units: 'pixels', normalize: true});

var VV4n = VV4.convolve(boxcar);
//var VV5n = VV5.convolve(boxcar);
//var VV6n = VV6.convolve(boxcar);

// Create band stack
var st_vvasc = VV1n.addBands(VV2n).addBands(VV3n);
print('Stacked VV_ASC', st_vvasc);

//var st_vvdes = VV4n.addBands(VV5n).addBands(VV6n);
//print('Stacked VV_DES', st_vvdes);

//------------------------------------------------------------------------------------------------------

//Add to map
Map.addLayer(VV4n, {min: -12, max: -7}, 'Sentinel-1 Flooding event');
//Map.addLayer(st_vvasc, {min: -12, max: -7}, 'Sentinel-1 Dry Season');

//Add mn basin to map
//var mn_basin = ee.FeatureCollection('users/donnywahyudi/mohand_mn_basin');
//mn_basin = mn_basin.geometry();
Map.addLayer(shed, {color: '#F1FF99', pointRadius: 3, strokeWidth: 10, opacity: 0.1}, 'Watershed');

//add agriculture
//var agriculture = ee.FeatureCollection('users/donnywahyudi/agriculture');
//a1 = agriculture.geometry();
Map.addLayer(agr, {color: '#A9FF99', pointRadius: 3, strokeWidth: 10}, 'Agricultures');

//villages
//var villa = ee.FeatureCollection('users/donnywahyudi/Villages');
//vil = villa.geometry();
Map.addLayer(vil, {color: 'red', pointRadius: 3, strokeWidth: 10}, 'Villages');

//Add channel to map
Map.addLayer(channels, {color: '#3399ff', pointRadius: 3, strokeWidth: 10}, 'Channels');
Map.addLayer(ch1, {color: 'blue', pointRadius: 3, strokeWidth: 10}, 'Channel 1');
Map.addLayer(ch2, {color: 'blue', pointRadius: 3, strokeWidth: 10}, 'Channel 2');
Map.addLayer(ch3, {color: 'blue', pointRadius: 3, strokeWidth: 10}, 'Channel 3');
Map.addLayer(ch4, {color: 'blue', pointRadius: 3, strokeWidth: 10}, 'Channel 4');
Map.addLayer(ch5, {color: 'blue', pointRadius: 3, strokeWidth: 10}, 'Channel 5');
Map.addLayer(ch6, {color: 'blue', pointRadius: 3, strokeWidth: 10}, 'Channel 6');
Map.addLayer(ch7, {color: 'blue', pointRadius: 3, strokeWidth: 10}, 'Channel 7');
Map.addLayer(ch8, {color: 'blue', pointRadius: 3, strokeWidth: 10}, 'Channel 8');

//var ss = ee.FeatureCollection([ch1, ch2, ch3, ch4, ch5, ch6, ch7, ch8]);
//Map.addLayer(ss, {color: 'red', pointRadius: 3, strokeWidth: 10}, 'All Channels');

Map.addLayer(f1, {color: '#8D10FC', pointRadius: 3, strokeWidth: 10}, 'Potentially flood');


var optionsvv = {
  title: 'Backscatter Mohand',
  hAxis: {title: 'Band'},
  vAxis: {title: 'Backscatter coefficient Sigma^0_VV (dB)'},
  lineWidth: 2,
  pointSize: 4,
  fontSize:20,
  series: {
    0: {color: '970F0F'},
    }};

//var loc = [uppersiwalik, midsiwalik, outlet]; XXX

// Choose bands to include and define feature collection to use
var subset = st_vvasc.select('VV', 'VV_1', 'VV_2');
var bs54 = ee.FeatureCollection([d1, d2, d3, d4, d5, d6, d7, d8, d9, d10, d11, d12, d13, d14, d15, d16, d17, d18, d19, d20, d21, d22, d23, d24, d25, d26, d28, d29, d30, d31, d32, d33, d34, d35, d36, d37, d38, d39, d40, d41, d42, d43, d44, d45, d46, d47, d48, d49, d50, d51, d52, d53, d54, d55, d56]);
var bs27 = ee.FeatureCollection([a0, a1, a2, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12, a13, a14, a15, a16, a17, a18, a19, a20, a21, a22, a23, a24, a25, a26, a27, a28, a29, a30, a31, a32, a33, a34, a35, a36, a37, a38, a39, a40]);
var bs34 = ee.FeatureCollection([b0, b1, b2, b3, b4, b5, b6, b7, b8, b9, b10, b11, b12, b13, b14, b15, b16, b17, b18, b19, b20, b21, b22, b23, b24, b25, b26]);

// Create the chart and set options.
// VV Plot
//var plot= ui.Chart.image.regions(
//    st_vvasc, loc, ee.Reducer.mean(), 30, 'label')
//        .setChartType('LineChart')
//        .setOptions(optionsvv);
// Display the chart.
//print('Backscatter VV Asc',plot);

//VV plot
//var plot1 = ui.Chart.image.regions(
//    st_vvdes, loc, ee.Reducer.mean(), 30, 'label')
//        .setChartType('LineChart')
//        .setOptions(optionsvv);
// Display the chart.
//print('Backscatter VV Des',plot1);

// Create the chart and set options.
// VV Plot
var plot27 = ui.Chart.image.regions(
    subset, bs27, ee.Reducer.median(), 10, 'label')
        .setChartType('LineChart')
        .setOptions(optionsvv);
// Display the chart.
print('BS27',plot27);

//VV plot
var plot271 = ui.Chart.image.regions(
    subset, bs27, ee.Reducer.count(), 10, 'label')
        .setChartType('LineChart')
        .setOptions(optionsvv);
// Display the chart.
print('BS27 count',plot271);

var plot34 = ui.Chart.image.regions(
    subset, bs34, ee.Reducer.median(), 10, 'label')
        .setChartType('LineChart')
        .setOptions(optionsvv);
// Display the chart.
print('bs34',plot34);

//VV plot
var plot341 = ui.Chart.image.regions(
    subset, bs34, ee.Reducer.count(), 10, 'label')
        .setChartType('LineChart')
        .setOptions(optionsvv);
// Display the chart.
print('bs34 count',plot341);

var plot54 = ui.Chart.image.regions(
    subset, bs54, ee.Reducer.median(), 10, 'label')
        .setChartType('LineChart')
        .setOptions(optionsvv);
// Display the chart.
print('bs54',plot54);

//VV plot
var plot541 = ui.Chart.image.regions(
    subset, bs54, ee.Reducer.count(), 10, 'label')
        .setChartType('LineChart')
        .setOptions(optionsvv);
// Display the chart.
print('bs54 count',plot541);



// set position of panel
var legend = ui.Panel({
  style: {
    position: 'bottom-left',
    padding: '10px 20px'
  }
});

// Create legend title
var legendTitle = ui.Label({
  value: 'Legend',
  style: {
    fontWeight: 'bold',
    fontSize: '18px',
    margin: '0 0 4px 0',
    padding: '0'
    }
});

// Add the title to the panel
legend.add(legendTitle);
    
// Creates and styles 1 row of the legend.
var makeRow = function(color, name) {
      
      // Create the label that is actually the colored box.
      var colorBox = ui.Label({
        style: {
          backgroundColor: '#' + color,
          // Use padding to give the box height and width.
          padding: '8px',
          margin: '0 0 4px 0'
        }
      });
      
      // Create the label filled with the description text.
      var description = ui.Label({
        value: name,
        style: {margin: '0 0 4px 6px'}
      });
      
      // return the panel
      return ui.Panel({
        widgets: [colorBox, description],
        layout: ui.Panel.Layout.Flow('horizontal')
      });
};


//  Palette with the colors
var palette =['FF0000', 'A9FF99', '1500ff', 'F1FF99', '8610FC'];

// name of the legend
var names = ['Villages','Agricultures','Channels', 'Watersheds', 'Flood potential'];

// Add color and and names
for (var i = 0; i < 5; i++) {
  legend.add(makeRow(palette[i], names[i]));
  }  

// add legend to map (alternatively you can also print the legend to the console)  
Map.add(legend);  
  
```
