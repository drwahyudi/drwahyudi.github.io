---
title: Radar backscatter derived channel roughness analysis
layout: single
classes: wide
author_profile: true
header:
  image: /images/gee.jpg
  
---





This is a template code for the backscatter for channel roughness analysis using the _Google Earth Engine_. Please adjust it to your need. Or, you can go to  <a href="https://code.earthengine.google.com/024619a64d82577f307f86798bcc1cc3">*https://code.earthengine.google.com/024619a64d82577f307f86798bcc1cc3*</a>.



<h2>Calculate the NDVI for slecting windows in determining radar bounce values</h2>


First of all, generate an NDVI image which then will be draped above the Satellite image. This is to ensure that the polygons that we use in this analysis do not exceed the channel bank, hence resulting in distorded signal in radar bounce due to vegetation.


```java
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
// Let's centre the map view over the area
Map.centerObject(moh, 11);
Map.addLayer(ndvi_crop, colorizedVis, 'NDVI');
```


Create series of 'feature' rectangles that goes from the outlet of the channel, all the way upstream.
Each 'feature' properties must be set as:

Import as: Feature
Property: Label
Value: n (0,1,2,...)



Next, let's explore and import the Sentinel-1 data. We are going to use the VV polarisation since it demonstrated best response for channel bed roughness analysis (Purinton et al., 2020).

```java
//Filter the collection for the VV product from the Ascending track
var collectionVVas = ee.ImageCollection('COPERNICUS/S1_GRD')
    .filter(ee.Filter.eq('instrumentMode', 'IW'))
    .filter(ee.Filter.listContains('transmitterReceiverPolarisation', 'VV'))
    .filter(ee.Filter.eq('orbitProperties_pass', 'ASCENDING'))
    .filterBounds(mohand)
    .select(['VV']);
print(collectionVVas);
```
Now let's show the Sentinel 1 data to the map layer.
```java
var VVas = collectionVVas.median();
Map.addLayer(VVas, {min: -14, max: -1}, 'VVas');
```


Channel bed analysis works best during the dry season where no water flowing through the channel (that is where the channel bed exposed). In order to do that, we are going to filter our Sentinel-1 data to the desired time frame, the dry season. We are also going to create a '3 band stack' through different dry season periods.

```java
var VV1 = ee.Image(collectionVVas.filterDate('2017-10-30', '2018-05-01').median());
var VV2 = ee.Image(collectionVVas.filterDate('2018-10-30', '2019-05-01').median());
var VV3 = ee.Image(collectionVVas.filterDate('2019-10-30', '2020-05-01').median());
```


Apply Speckle filtering/smoothing.
Smooth the image by convolving with the boxcar kernel.

```java
var boxcar = ee.Kernel.square({radius: 1.5, units: 'pixels', normalize: true});

var VV1n = VV1.convolve(boxcar);
var VV2n = VV2.convolve(boxcar);
var VV3n = VV3.convolve(boxcar);
```


Create a band stack from different time frame.

```java
var st_vvasc = VV1n.addBands(VV2n).addBands(VV3n);
print('Stacked VV_ASC', st_vvasc);
Map.addLayer(st_vvasc, {min: -12, max: -7}, 'Sentinel-1 Dry Season');
```


Choose bands to include and define feature collection to use as the backscatter values collection windows.

```java
var subset = st_vvasc.select('VV', 'VV_1', 'VV_2');
var bs54 = ee.FeatureCollection([d1, d2, d3, d4, d5, d6, d7, d8, d9, d10, d11, d12, d13, d14, d15, d16, d17, d18, d19, d20, d21, d22, d23, d24, d25, d26, d28, d29, d30, d31, d32, d33, d34, d35, d36, d37, d38, d39, d40, d41, d42, d43, d44, d45, d46, d47, d48, d49, d50, d51, d52, d53, d54, d55, d56]);
```


Define the chart to present the radar backscatter values along the channel.

```java
var optionsvv = {
  title: 'Channel Roughness',
  hAxis: {title: 'Band'},
  vAxis: {title: 'Backscatter coefficient Sigma^0_VV (dB)'},
  lineWidth: 2,
  pointSize: 4,
  fontSize:20,
  series: {
    0: {color: '970F0F'},
    }};
```


Generate the chart.

```java
var plot54 = ui.Chart.image.regions(
    subset, bs54, ee.Reducer.median(), 10, 'label')
        .setChartType('LineChart')
        .setOptions(optionsvv);
// Display the chart.
print('bs54',plot54);
```
