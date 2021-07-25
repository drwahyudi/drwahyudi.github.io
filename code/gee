<h1>1.	Google Earth Engine code for backscatter analysis</h1>


// Calculate the NDVI from Landsat 8 data
var dataset = ee.ImageCollection('LANDSAT/LC08/C01/T1_8DAY_NDVI')
                  .filterDate('2018-01-01', '2020-01-31');
var colorized = dataset.select('NDVI');
print(colorized)
var ndvi=colorized.reduce(ee.Reducer.mean());
print(ndvi)
var ndvi_crop=ndvi.clip(Area_of_interest);
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
Map.centerObject(Area_of_interest, 11);
Map.addLayer(ndvi_crop, colorizedVis, 'NDVI');
// Explore Sentinel-1 data
// Filter the collection for the VV product from the Ascending track
var collectionVVas = ee.ImageCollection('COPERNICUS/S1_GRD')
    .filter(ee.Filter.eq('instrumentMode', 'IW'))
    .filter(ee.Filter.listContains('transmitterReceiverPolarisation', 'VV'))
    .filter(ee.Filter.eq('orbitProperties_pass', 'ASCENDING'))
    .filterBounds(Area_of_interest)
    .select(['VV']);
print(collectionVVas);
// Filter the collection for the VV product from the descending track
var collectionVVdes = ee.ImageCollection('COPERNICUS/S1_GRD')
    .filter(ee.Filter.eq('instrumentMode', 'IW'))
    .filter(ee.Filter.listContains('transmitterReceiverPolarisation', 'VV'))
    .filter(ee.Filter.eq('orbitProperties_pass', 'DESCENDING'))
    .filterBounds(Area_of_interest)
    .select(['VV']);
print(collectionVVdes);
// Adding the VV Ascending layer to the map
var VVas = collectionVVas.median();
//Map.addLayer(VVas, {min: -14, max: -1}, 'VVas');
// Adding the VV Descending layer to the map
var VVdes = collectionVVdes.median();
//Map.addLayer(VVdes, {min: -20, max: -7}, 'VVdes');
// Create a 3 band stack of VV decending by selecting from different periods (in my case this is the dry season so the channel will exposed). Please adjust to your own needs.
var VVdec1 = ee.Image(collectionVVas.filterDate('2017-10-30', '2018-05-01').median());
var VVdec2 = ee.Image(collectionVVas.filterDate('2018-10-30', '2019-05-01').median());
var VVdec3 = ee.Image(collectionVVas.filterDate('2019-10-30', '2020-05-01').median());
//Speckle filtering/smoothing
// Smooth the image by convolving with the boxcar kernel.
// Define a boxcar or low-pass kernel.
//A 3X3 Boxcar filter
var boxcar = ee.Kernel.square({radius: 1.5, units: 'pixels', normalize: true});
var VV1Speckled = VVdec1.convolve(boxcar);
var VV2Speckled = VVdec2.convolve(boxcar);
var VV3Speckled = VVdec3.convolve(boxcar);
var s1 = ee.ImageCollection([VV1n, VV2n, VV3n, VV41n, VV51n, VV61n]).median();
//Map.addLayer(s1, {min: -14, max: -1}, 'S1');
// Create a 3 band stack of VV ascending by selecting from different periods (months)
var VV1asc = ee.Image(collectionVVdes.filterDate('2017-10-30', '2018-05-01').median());
var VV2asc = ee.Image(collectionVVdes.filterDate('2018-10-30', '2019-05-01').median());
var VV3asc = ee.Image(collectionVVdes.filterDate('2019-10-30', '2020-05-01').median());
// Speckle filtering/smoothing
// Smooth the image by convolving with the boxcar kernel.
// Define a boxcar or low-pass kernel.
// A 3X3 Boxcar filter
var boxcar = ee.Kernel.square({radius: 1.5, units: 'pixels', normalize: true});
var VV1ascSpeckled = VV1asc.convolve(boxcar);
var VV2ascSpeckled = VV2asc.convolve(boxcar);
var VV3ascSpeckled = VV3asc.convolve(boxcar);
// Create band stack
var st_vvasc = VV1ascSpeckled.addBands(VV2ascSpeckled).addBands(VV3ascSpeckled);
print('Stacked VV_ASC', st_vvasc);
var st_vvdes = VV1Speckled.addBands(VV2Speckled).addBands(VV3Speckled);
print('Stacked VV_DES', st_vvdes);
//Add to map
Map.addLayer(st_vvdes, {min: -12, max: -7}, 'VVDESdryseason');
Map.addLayer(st_vvasc, {min: -12, max: -7}, 'VVASdryseason');
//Add .shp files to map
var mn_basin = ee.FeatureCollection('users/donnywahyudi/mohand_mn_basin');
mn_basin = mn_basin.geometry();
//Map.addLayer(mn_basin, {color: 'pink', pointRadius: 3, strokeWidth: 10}, 'mn_basin');
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
// Choose bands to include and define feature collection to use
var subset = st_vvasc.select('VV', 'VV_1', 'VV_2')
var selection_of_basin1 = ee.FeatureCollection([list_of_your_polygon_feature_along_the_channel such as: polygon1, polygon2, polygon3,...,polygon_n]);
var selection_of_basin2 = ee.FeatureCollection([list_of_your_polygon_feature_along_the_channel]);
var selection_of_basin3 = ee.FeatureCollection([list_of_your_polygon_feature_along_the_channel]);
// Create the chart and set options.
// VV Plot
var plot = ui.Chart.image.regions(
    subset, (your_basin_number), ee.Reducer.median(), 10, 'label')
        .setChartType('LineChart')
        .setOptions(optionsvv);
// Display the chart.
print('your_basin_number',plot);
-end-
