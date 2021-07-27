---
title: Radar backscatter for channel roughness analysis
layout: single
classes: wide
author_profile: true
header:
  image: /images/gee.jpg
  
---

<h1>1.	Google Earth Engine code for backscatter analysis</h1>




This is a template code for the backscatter for channel roughness analysis using the _Google Earth Engine_. Please adjust it to your need. Or, you can go to  <a href="https://code.earthengine.google.com/3ac99827537c2cc616b107751ad7f26d">*https://code.earthengine.google.com/3ac99827537c2cc616b107751ad7f26d*</a>.






```java
var sentinel1 = ee.ImageCollection("COPERNICUS/S1_GRD"),
    moh = 
    /* color: #d63000 */
    /* shown: false */
    ee.Geometry.Point([77.91120247666541, 30.226142875619136]),
    d1 = 
    /* color: #d63000 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.97034760903712, 30.21685775828359],
              [77.97034760903712, 30.21657035455773],
              [77.97094842385646, 30.21657035455773],
              [77.97094842385646, 30.21685775828359]]], null, false),
        {
          "label": "distance1",
          "system:index": "0"
        }),
    d2 = 
    /* color: #98ff00 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.96908509776415, 30.216277210558104],
              [77.96908509776415, 30.21600834744684],
              [77.96972614571871, 30.21600834744684],
              [77.96972614571871, 30.216277210558104]]], null, false),
        {
          "label": "distance2",
          "system:index": "0"
        }),
    d3 = 
    /* color: #0b4a8b */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.96757007229532, 30.21541915981245],
              [77.96757007229532, 30.2151294340746],
              [77.96820843804086, 30.2151294340746],
              [77.96820843804086, 30.21541915981245]]], null, false),
        {
          "label": "distance3",
          "system:index": "0"
        }),
    d4 = 
    /* color: #ffc82d */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.96698022993964, 30.214593891949434],
              [77.96698022993964, 30.214067744964026],
              [77.9672967306034, 30.214067744964026],
              [77.9672967306034, 30.214593891949434]]], null, false),
        {
          "label": "distance4",
          "system:index": "0"
        }),
    d5 = 
    /* color: #00ffff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.96635259303015, 30.214305495439536],
              [77.96635259303015, 30.213828021563373],
              [77.96667177590292, 30.213828021563373],
              [77.96667177590292, 30.214305495439536]]], null, false),
        {
          "label": "distance5",
          "system:index": "0"
        }),
    d6 = 
    /* color: #bf04c2 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.96512880287241, 30.213737625762857],
              [77.96512880287241, 30.21347107355983],
              [77.96576180419993, 30.21347107355983],
              [77.96576180419993, 30.213737625762857]]], null, false),
        {
          "label": 6,
          "system:index": "0"
        }),
    d7 = 
    /* color: #ff0000 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.96389726797072, 30.2134429128796],
              [77.96389726797072, 30.213176359878204],
              [77.96452490488021, 30.213176359878204],
              [77.96452490488021, 30.2134429128796]]], null, false),
        {
          "label": 7,
          "system:index": "0"
        }),
    d8 = 
    /* color: #00ff00 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.96264735856978, 30.213401191587955],
              [77.96264735856978, 30.212884309673697],
              [77.96329377094237, 30.212884309673697],
              [77.96329377094237, 30.213401191587955]]], null, false),
        {
          "label": 8,
          "system:index": "0"
        }),
    d9 = 
    /* color: #0000ff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.96109972396819, 30.21284527079778],
              [77.96109972396819, 30.21252308729582],
              [77.9620572725865, 30.21252308729582],
              [77.9620572725865, 30.21284527079778]]], null, false),
        {
          "label": 9,
          "system:index": "0"
        }),
    d10 = 
    /* color: #999900 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.96112879461528, 30.21202511857886],
              [77.96112879461528, 30.211489686277027],
              [77.96144261307002, 30.211489686277027],
              [77.96144261307002, 30.21202511857886]]], null, false),
        {
          "label": 10,
          "system:index": "0"
        }),
    d11 = 
    /* color: #009999 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.96085520929576, 30.21067378383375],
              [77.96085520929576, 30.209862510492247],
              [77.9612038964677, 30.209862510492247],
              [77.9612038964677, 30.21067378383375]]], null, false),
        {
          "label": 11,
          "system:index": "0"
        }),
    d12 = 
    /* color: #ff00ff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.95997008032084, 30.20928766133305],
              [77.95997008032084, 30.209018779122047],
              [77.96080692953349, 30.209018779122047],
              [77.96080692953349, 30.20928766133305]]], null, false),
        {
          "label": 12,
          "system:index": "0"
        }),
    d13 = 
    /* color: #ff9999 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.95968495709805, 30.20846107037425],
              [77.95968495709805, 30.207951116445418],
              [77.96031259400753, 30.207951116445418],
              [77.96031259400753, 30.20846107037425]]], null, false),
        {
          "label": 13,
          "system:index": "0"
        }),
    d14 = 
    /* color: #99ff99 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.95847796304135, 30.207603419069777],
              [77.95847796304135, 30.2071120046839],
              [77.9590465913525, 30.2071120046839],
              [77.9590465913525, 30.207603419069777]]], null, false),
        {
          "label": 14,
          "system:index": "0"
        }),
    d15 = 
    /* color: #9999ff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.95723341805844, 30.206515703459402],
              [77.95723341805844, 30.20625144971182],
              [77.95787714822201, 30.20625144971182],
              [77.95787714822201, 30.206515703459402]]], null, false),
        {
          "label": 15,
          "system:index": "0"
        }),
    d16 = 
    /* color: #ffff99 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.95540587269105, 30.205920584355834],
              [77.95540587269105, 30.205684145395963],
              [77.95625613294877, 30.205684145395963],
              [77.95625613294877, 30.205920584355834]]], null, false),
        {
          "label": 16,
          "system:index": "0"
        }),
    d17 = 
    /* color: #99ffff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.95424715839661, 30.2055783701457],
              [77.95424715839661, 30.204887593501898],
              [77.95511619411744, 30.204887593501898],
              [77.95511619411744, 30.2055783701457]]], null, false),
        {
          "label": 17,
          "system:index": "0"
        }),
    d18 = 
    /* color: #ff99ff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.95327083431519, 30.204251886690727],
              [77.95327083431519, 30.20374654710686],
              [77.95389310680665, 30.20374654710686],
              [77.95389310680665, 30.204251886690727]]], null, false),
        {
          "label": 18,
          "system:index": "0"
        }),
    d19 = 
    /* color: #d63000 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.95239838711503, 30.20288801080554],
              [77.95239838711503, 30.202340938238663],
              [77.95301529518845, 30.202340938238663],
              [77.95301529518845, 30.20288801080554]]], null, false),
        {
          "label": 19,
          "system:index": "0"
        }),
    d20 = 
    /* color: #98ff00 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.95146497837784, 30.201673320139527],
              [77.95146497837784, 30.20093615322843],
              [77.95210334412339, 30.20093615322843],
              [77.95210334412339, 30.201673320139527]]], null, false),
        {
          "label": 20,
          "system:index": "0"
        }),
    d21 = 
    /* color: #0b4a8b */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.94975909344437, 30.200750701564125],
              [77.94975909344437, 30.199865165050056],
              [77.95117529980423, 30.199865165050056],
              [77.95117529980423, 30.200750701564125]]], null, false),
        {
          "label": 21,
          "system:index": "0"
        }),
    d22 = 
    /* color: #ffc82d */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.94746785159052, 30.200041345724273],
              [77.94746785159052, 30.199392257470752],
              [77.94873921866358, 30.199392257470752],
              [77.94873921866358, 30.200041345724273]]], null, false),
        {
          "label": 22,
          "system:index": "0"
        }),
    d23 = 
    /* color: #00ffff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.94603622035444, 30.198056399075597],
              [77.94603622035444, 30.197068836052605],
              [77.94630980567396, 30.197068836052605],
              [77.94630980567396, 30.198056399075597]]], null, false),
        {
          "label": 23,
          "system:index": "0"
        }),
    d24 = 
    /* color: #bf04c2 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.94578979653717, 30.19620457075276],
              [77.94578979653717, 30.195291174032253],
              [77.9468573157251, 30.195291174032253],
              [77.9468573157251, 30.19620457075276]]], null, false),
        {
          "label": 24,
          "system:index": "0"
        }),
    d25 = 
    /* color: #ff0000 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.94418821929034, 30.19593723700414],
              [77.94418821929034, 30.195663681787266],
              [77.94450203774508, 30.195663681787266],
              [77.94450203774508, 30.19593723700414]]], null, false),
        {
          "label": 25,
          "system:index": "0"
        }),
    d26 = 
    /* color: #00ff00 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.94484021164226, 30.19487206601878],
              [77.94484021164226, 30.194603144428132],
              [77.9454785773878, 30.194603144428132],
              [77.9454785773878, 30.19487206601878]]], null, false),
        {
          "label": 26,
          "system:index": "0"
        }),
    d28 = 
    /* color: #999900 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.94332744575786, 30.193740735752073],
              [77.94332744575786, 30.19293859617146],
              [77.94394971824931, 30.19293859617146],
              [77.94394971824931, 30.193740735752073]]], null, false),
        {
          "label": 28,
          "system:index": "0"
        }),
    d29 = 
    /* color: #009999 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.94400336242961, 30.191890704563622],
              [77.94400336242961, 30.191046819145413],
              [77.94433595634746, 30.191046819145413],
              [77.94433595634746, 30.191890704563622]]], null, false),
        {
          "label": 29,
          "system:index": "0"
        }),
    d30 = 
    /* color: #ff00ff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.94243158794688, 30.19209935643658],
              [77.94243158794688, 30.191830427273594],
              [77.94277491070079, 30.191830427273594],
              [77.94277491070079, 30.19209935643658]]], null, false),
        {
          "label": 30,
          "system:index": "0"
        }),
    d31 = 
    /* color: #ff9999 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.93997051764865, 30.191541726658727],
              [77.93997051764865, 30.191300616422726],
              [77.94060888339419, 30.191300616422726],
              [77.94060888339419, 30.191541726658727]]], null, false),
        {
          "label": 31,
          "system:index": "0"
        }),
    d32 = 
    /* color: #99ff99 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.93870451499362, 30.191476812422508],
              [77.93870451499362, 30.191203244813938],
              [77.93932142306704, 30.191203244813938],
              [77.93932142306704, 30.191476812422508]]], null, false),
        {
          "label": 32,
          "system:index": "0"
        }),
    d33 = 
    /* color: #9999ff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.93847384501834, 30.190261980965218],
              [77.93847384501834, 30.1891676924726],
              [77.93968620349307, 30.1891676924726],
              [77.93968620349307, 30.190261980965218]]], null, false),
        {
          "label": 33,
          "system:index": "0"
        }),
    d34 = 
    /* color: #ffff99 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.93660166312594, 30.190085782791922],
              [77.93660166312594, 30.18946908670288],
              [77.93752434302706, 30.18946908670288],
              [77.93752434302706, 30.190085782791922]]], null, false),
        {
          "label": 34,
          "system:index": "0"
        }),
    d35 = 
    /* color: #99ffff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.93597402621646, 30.189232608230906],
              [77.93597402621646, 30.18736394464829],
              [77.93632807780642, 30.18736394464829],
              [77.93632807780642, 30.189232608230906]]], null, false),
        {
          "label": 35,
          "system:index": "0"
        }),
    d36 = 
    /* color: #ff99ff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.93452563334841, 30.18676897696823],
              [77.93452563334841, 30.186047927929703],
              [77.93508353282351, 30.186047927929703],
              [77.93508353282351, 30.18676897696823]]], null, false),
        {
          "label": 36,
          "system:index": "0"
        }),
    d37 = 
    /* color: #d63000 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.93202316522625, 30.186206611972906],
              [77.93202316522625, 30.185645535696764],
              [77.93321138381985, 30.185645535696764],
              [77.93321138381985, 30.186206611972906]]], null, false),
        {
          "label": 37,
          "system:index": "0"
        }),
    d38 = 
    /* color: #98ff00 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.9305134682368, 30.185281514376552],
              [77.9305134682368, 30.18429846030667],
              [77.93158635184275, 30.18429846030667],
              [77.93158635184275, 30.185281514376552]]], null, false),
        {
          "label": 38,
          "system:index": "0"
        }),
    d39 = 
    /* color: #0b4a8b */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.92806729361521, 30.18424281544329],
              [77.92806729361521, 30.182833135086643],
              [77.92988046690928, 30.182833135086643],
              [77.92988046690928, 30.18424281544329]]], null, false),
        {
          "label": 39,
          "system:index": "0"
        }),
    d40 = 
    /* color: #ffc82d */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.92585715338694, 30.18250853477882],
              [77.92585715338694, 30.18186860532496],
              [77.92695149466502, 30.18186860532496],
              [77.92695149466502, 30.18250853477882]]], null, false),
        {
          "label": 40,
          "system:index": "0"
        }),
    d41 = 
    /* color: #00ffff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.92445167586314, 30.181180216006446],
              [77.92445167586314, 30.18004872845872],
              [77.92564257666575, 30.18004872845872],
              [77.92564257666575, 30.181180216006446]]], null, false),
        {
          "label": 41,
          "system:index": "0"
        }),
    d42 = 
    /* color: #bf04c2 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.92443021819102, 30.179269663904854],
              [77.92443021819102, 30.1783329233681],
              [77.92568549200999, 30.1783329233681],
              [77.92568549200999, 30.179269663904854]]], null, false),
        {
          "label": 42,
          "system:index": "0"
        }),
    d43 = 
    /* color: #ff0000 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.92323931738841, 30.17760021911722],
              [77.92323931738841, 30.17678403581517],
              [77.92449459120738, 30.17678403581517],
              [77.92449459120738, 30.17760021911722]]], null, false),
        {
          "label": 43,
          "system:index": "0"
        }),
    d44 = 
    /* color: #00ff00 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.91920527503001, 30.177776439624576],
              [77.91920527503001, 30.176672737568367],
              [77.92043909117686, 30.176672737568367],
              [77.92043909117686, 30.177776439624576]]], null, false),
        {
          "label": 44,
          "system:index": "0"
        }),
    d45 = 
    /* color: #0000ff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.9175101189326, 30.176190443712798],
              [77.9175101189326, 30.172851421510803],
              [77.91890486762034, 30.172851421510803],
              [77.91890486762034, 30.176190443712798]]], null, false),
        {
          "label": 45,
          "system:index": "0"
        }),
    d46 = 
    /* color: #999900 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.91788674105804, 30.17154526963074],
              [77.91788674105804, 30.16894813972787],
              [77.91938877810638, 30.16894813972787],
              [77.91938877810638, 30.17154526963074]]], null, false),
        {
          "label": 46,
          "system:index": "0"
        }),
    d47 = 
    /* color: #009999 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.91914411455001, 30.167273592610425],
              [77.91914411455001, 30.16382295555336],
              [77.9209251013359, 30.16382295555336],
              [77.9209251013359, 30.167273592610425]]], null, false),
        {
          "label": 47,
          "system:index": "0"
        }),
    d48 = 
    /* color: #ff00ff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.91947441808117, 30.162451963824353],
              [77.91947441808117, 30.159910252974687],
              [77.9207404207362, 30.159910252974687],
              [77.9207404207362, 30.162451963824353]]], null, false),
        {
          "label": 48,
          "system:index": "0"
        }),
    d49 = 
    /* color: #ff9999 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.91612702123058, 30.157238603060165],
              [77.91612702123058, 30.155327586842827],
              [77.91745739690197, 30.155327586842827],
              [77.91745739690197, 30.157238603060165]]], null, false),
        {
          "label": 49,
          "system:index": "0"
        }),
    d50 = 
    /* color: #99ff99 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.9150326799525, 30.154214356443422],
              [77.9150326799525, 30.151876531703653],
              [77.91629868260753, 30.151876531703653],
              [77.91629868260753, 30.154214356443422]]], null, false),
        {
          "label": 50,
          "system:index": "0"
        }),
    d51 = 
    /* color: #9999ff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.91205415438635, 30.15042239118723],
              [77.91205415438635, 30.149383324864917],
              [77.91394242953284, 30.149383324864917],
              [77.91394242953284, 30.15042239118723]]], null, false),
        {
          "label": 51,
          "system:index": "0"
        }),
    d52 = 
    /* color: #ffff99 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.91086325358374, 30.14826074984197],
              [77.91086325358374, 30.146952609112315],
              [77.9118824930094, 30.146952609112315],
              [77.9118824930094, 30.14826074984197]]], null, false),
        {
          "label": 52,
          "system:index": "0"
        }),
    d53 = 
    /* color: #99ffff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.90878425459722, 30.14611915471664],
              [77.90878425459722, 30.145121793300696],
              [77.91024874071935, 30.145121793300696],
              [77.91024874071935, 30.14611915471664]]], null, false),
        {
          "label": 53,
          "system:index": "0"
        }),
    d54 = 
    /* color: #ff99ff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.90570319902571, 30.144118711949822],
              [77.90570319902571, 30.14336719741923],
              [77.9068726421562, 30.14336719741923],
              [77.9068726421562, 30.144118711949822]]], null, false),
        {
          "label": 54,
          "system:index": "0"
        }),
    d55 = 
    /* color: #d63000 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.90265670428028, 30.141397823586733],
              [77.90265670428028, 30.14088752249476],
              [77.90478101382007, 30.14088752249476],
              [77.90478101382007, 30.141397823586733]]], null, false),
        {
          "label": 55,
          "system:index": "0"
        }),
    d56 = 
    /* color: #98ff00 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.9014761347537, 30.139141481587018],
              [77.9014761347537, 30.138111574941814],
              [77.90255974719571, 30.138111574941814],
              [77.90255974719571, 30.139141481587018]]], null, false),
        {
          "label": 56,
          "system:index": "0"
        }),
    mohand = 
    /* color: #0b4a8b */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Geometry.Polygon(
        [[[77.55826851778767, 30.445681587191803],
          [77.55826851778767, 29.935267689017614],
          [78.27169320040485, 29.935267689017614],
          [78.27169320040485, 30.445681587191803]]], null, false),
    a0 = 
    /* color: #d63000 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.70989001622173, 30.26747100368939],
              [77.70989001622173, 30.266247844339862],
              [77.71249712338421, 30.266247844339862],
              [77.71249712338421, 30.26747100368939]]], null, false),
        {
          "label": "a0",
          "system:index": "0"
        }),
    a1 = 
    /* color: #98ff00 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71115601887676, 30.270158194198984],
              [77.71115601887676, 30.2681845062727],
              [77.71228254666302, 30.2681845062727],
              [77.71228254666302, 30.270158194198984]]], null, false),
        {
          "label": "a1",
          "system:index": "0"
        }),
    a2 = 
    /* color: #0b4a8b */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71084488263104, 30.271984736605074],
              [77.71084488263104, 30.270706037535017],
              [77.71240056385967, 30.270706037535017],
              [77.71240056385967, 30.271984736605074]]], null, false),
        {
          "label": "a2",
          "system:index": "0"
        }),
    a3 = 
    /* color: #ffc82d */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7105873905656, 30.27490344381638],
              [77.7105873905656, 30.272512890055747],
              [77.71127403607342, 30.272512890055747],
              [77.71127403607342, 30.27490344381638]]], null, false),
        {
          "label": "a3",
          "system:index": "0"
        }),
    a4 = 
    /* color: #00ffff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71045864453289, 30.27709936631159],
              [77.71045864453289, 30.275598361312362],
              [77.71217525830242, 30.275598361312362],
              [77.71217525830242, 30.27709936631159]]], null, false),
        {
          "label": "a4",
          "system:index": "0"
        }),
    a5 = 
    /* color: #bf04c2 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71072686543438, 30.278739327011504],
              [77.71072686543438, 30.277627492240534],
              [77.711917766237, 30.277627492240534],
              [77.711917766237, 30.278739327011504]]], null, false),
        {
          "label": "a5",
          "system:index": "0"
        }),
    a6 = 
    /* color: #ff0000 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71006167759869, 30.28092589864671],
              [77.71081269612286, 30.279100670599856],
              [77.71133840908978, 30.279174792197107],
              [77.71049083104107, 30.28107413902787]]]),
        {
          "label": "a6",
          "system:index": "0"
        }),
    a7 = 
    /* color: #00ff00 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.70953596463177, 30.281250174189623],
              [77.7104050003526, 30.28149106389922],
              [77.71042645802471, 30.283001243603092],
              [77.70932138791058, 30.28296418425667]]]),
        {
          "label": "a7",
          "system:index": "0"
        }),
    a8 = 
    /* color: #0000ff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7111452900407, 30.282890065521794],
              [77.71196068158123, 30.285965945965124],
              [77.71104873051617, 30.285910358619965],
              [77.70932138791058, 30.283501543409983]]]),
        {
          "label": "a8",
          "system:index": "0"
        }),
    a9 = 
    /* color: #999900 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71219671597454, 30.286429172616515],
              [77.7137738548753, 30.287791046303347],
              [77.71367729535076, 30.29006079376717],
              [77.71153152813885, 30.286901661547773]]]),
        {
          "label": "a9",
          "system:index": "0"
        }),
    a10 = 
    /* color: #009999 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71451414456341, 30.290347982560334],
              [77.7141171776292, 30.291283656344135],
              [77.71374166836712, 30.291302184447755],
              [77.71358073582623, 30.290301661844108]]]),
        {
          "label": "a10",
          "system:index": "0"
        }),
    a11 = 
    /* color: #ff00ff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71354854931805, 30.29150599335653],
              [77.71381677021954, 30.29163568971433],
              [77.7132159554002, 30.292441656093555],
              [77.71288336148235, 30.292284168930884]]]),
        {
          "label": "a11",
          "system:index": "0"
        }),
    a12 = 
    /* color: #ff9999 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71322247569123, 30.292587198611365],
              [77.71329757754364, 30.29410647129205],
              [77.71258947436371, 30.29407867992994],
              [77.71287915293732, 30.292522351083008]]]),
        {
          "label": "a12",
          "system:index": "0"
        }),
    a13 = 
    /* color: #99ff99 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7134692389206, 30.295218119318506],
              [77.71558281962433, 30.296051847069094],
              [77.71493908946076, 30.296663242914644],
              [77.71313664500275, 30.295542347619314]]]),
        {
          "label": "a13",
          "system:index": "0"
        }),
    a14 = 
    /* color: #9999ff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71567937914887, 30.29645018115878],
              [77.7169990259842, 30.297200527026074],
              [77.7161729056076, 30.297867496310356],
              [77.71515366618195, 30.296820723045386]]]),
        {
          "label": "a14",
          "system:index": "0"
        }),
    a15 = 
    /* color: #ffff99 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71683587513957, 30.298282222878488],
              [77.71798386059794, 30.29954203604288],
              [77.71755470715556, 30.299755091080804],
              [77.71663202725443, 30.298680547908194]]]),
        {
          "label": "a15",
          "system:index": "0"
        }),
    a16 = 
    /* color: #99ffff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71825822730949, 30.299389866580746],
              [77.71935256858757, 30.300075347419558],
              [77.71913799186638, 30.300353243691703],
              [77.71794709106376, 30.299927135752373]]]),
        {
          "label": "a16",
          "system:index": "0"
        }),
    a17 = 
    /* color: #ff99ff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.71964766555274, 30.30040376593773],
              [77.72011973433936, 30.30075113499131],
              [77.71962620788062, 30.30136713308671],
              [77.71942772441352, 30.300834503381033]]]),
        {
          "label": "a17",
          "system:index": "0"
        }),
    a18 = 
    /* color: #d63000 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7196583943888, 30.302603749158674],
              [77.7196583943888, 30.30233049076992],
              [77.72069909148658, 30.30233049076992],
              [77.72069909148658, 30.302603749158674]]], null, false),
        {
          "label": "a18",
          "system:index": "0"
        }),
    a19 = 
    /* color: #98ff00 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72044084136282, 30.304013804292726],
              [77.72044084136282, 30.303254247642737],
              [77.72073051993642, 30.303254247642737],
              [77.72073051993642, 30.304013804292726]]], null, false),
        {
          "label": "a19",
          "system:index": "0"
        }),
    a20 = 
    /* color: #0b4a8b */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72106311385427, 30.304805774776547],
              [77.72106311385427, 30.304291689401683],
              [77.72169611518179, 30.304291689401683],
              [77.72169611518179, 30.304805774776547]]], null, false),
        {
          "label": "a20",
          "system:index": "0"
        }),
    a21 = 
    /* color: #ffc82d */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72102556292806, 30.305041975261148],
              [77.72034964625631, 30.305454166900507],
              [77.72021017138754, 30.305301332000464],
              [77.72088608805929, 30.30485208864193]]]),
        {
          "label": "a21",
          "system:index": "0"
        }),
    a22 = 
    /* color: #00ffff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7201672560433, 30.306417484422706],
              [77.7201672560433, 30.30564868370144],
              [77.72039792601858, 30.30564868370144],
              [77.72039792601858, 30.306417484422706]]], null, false),
        {
          "label": "a22",
          "system:index": "0"
        }),
    a23 = 
    /* color: #bf04c2 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72093973223959, 30.306334120780527],
              [77.72152981822286, 30.30588488215504],
              [77.72215745513235, 30.30607476677372],
              [77.72219500605856, 30.306334120780527]]]),
        {
          "label": "a23",
          "system:index": "0"
        }),
    a24 = 
    /* color: #ff0000 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72245786254202, 30.306162761960078],
              [77.72315523688589, 30.306440640977378],
              [77.7229245669106, 30.306774094758357],
              [77.72236666743551, 30.30639432786253]]]),
        {
          "label": "a24",
          "system:index": "0"
        }),
    a25 = 
    /* color: #00ff00 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72334835593496, 30.306584211494368],
              [77.72435150210653, 30.30665831232407],
              [77.72493622367178, 30.30700565921666],
              [77.72453925673757, 30.30729279838523]]]),
        {
          "label": "a25",
          "system:index": "0"
        }),
    a26 = 
    /* color: #0000ff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7251937157372, 30.307075128447476],
              [77.72579989497457, 30.307547517911363],
              [77.72581598822866, 30.308385772042012],
              [77.72560141150747, 30.30862196390032],
              [77.7246894604424, 30.307408580070074]]]),
        {
          "label": "a26",
          "system:index": "0"
        }),
    a27 = 
    /* color: #999900 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72530636851583, 30.309552832152907],
              [77.72530636851583, 30.308747006418418],
              [77.72581598822866, 30.308747006418418],
              [77.72581598822866, 30.309552832152907]]], null, false),
        {
          "label": "a27",
          "system:index": "0"
        }),
    a28 = 
    /* color: #009999 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72502741877828, 30.310057046778446],
              [77.72373995845113, 30.31072392860045],
              [77.72352001731191, 30.31053868410506],
              [77.72478065554891, 30.309936637076955]]]),
        {
          "label": "a28",
          "system:index": "0"
        }),
    a29 = 
    /* color: #ff00ff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72348783080373, 30.310913803844862],
              [77.72421739007477, 30.31200905117803],
              [77.72402427260671, 30.312159561568034],
              [77.72335908477102, 30.31134449510885]]]),
        {
          "label": "a29",
          "system:index": "0"
        }),
    a30 = 
    /* color: #ff9999 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72395721738134, 30.31322962782319],
              [77.72395721738134, 30.31222932896376],
              [77.72423616711889, 30.31222932896376],
              [77.72423616711889, 30.31322962782319]]], null, false),
        {
          "label": "a30",
          "system:index": "0"
        }),
    a31 = 
    /* color: #99ff99 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72456669487097, 30.313208611445823],
              [77.72611701168158, 30.31397272191526],
              [77.72562884964087, 30.314357090383883],
              [77.72440576233008, 30.31344942266098]]]),
        {
          "label": "a31",
          "system:index": "0"
        }),
    a32 = 
    /* color: #9999ff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7262833086405, 30.314463601861437],
              [77.72560739196875, 30.315695421842282],
              [77.72528552688696, 30.315607435214336],
              [77.7259399858866, 30.314241316907644]]]),
        {
          "label": "a32",
          "system:index": "0"
        }),
    a33 = 
    /* color: #ffff99 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72553765453436, 30.31577877752216],
              [77.72541963733771, 30.31683924081607],
              [77.72515141643622, 30.31688091817838],
              [77.72521042503455, 30.31572320707694]]]),
        {
          "label": "a33",
          "system:index": "0"
        }),
    a34 = 
    /* color: #99ffff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72536599315741, 30.317010580969946],
              [77.72547328042756, 30.317684360017644],
              [77.72573077358344, 30.318182169128395],
              [77.72542500175574, 30.318219215165772],
              [77.72528552602446, 30.317758452549814],
              [77.72512459434607, 30.317093935531055]]]),
        {
          "label": "a34",
          "system:index": "0"
        }),
    a35 = 
    /* color: #ff99ff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72647642768958, 30.318196061394055],
              [77.72647642768958, 30.317876538785473],
              [77.72705042041876, 30.317876538785473],
              [77.72705042041876, 30.318196061394055]]], null, false),
        {
          "label": "a35",
          "system:index": "0"
        }),
    a36 = 
    /* color: #d63000 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72806429542639, 30.31704299664101],
              [77.72806429542639, 30.316566022113054],
              [77.72882604278662, 30.316566022113054],
              [77.72882604278662, 30.31704299664101]]], null, false),
        {
          "label": "a36",
          "system:index": "0"
        }),
    a37 = 
    /* color: #98ff00 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72958242572882, 30.318562320336497],
              [77.72958242572882, 30.31765932234688],
              [77.72989892639258, 30.31765932234688],
              [77.72989892639258, 30.318562320336497]]], null, false),
        {
          "label": "a37",
          "system:index": "0"
        }),
    a38 = 
    /* color: #0b4a8b */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.72990429081061, 30.319747781985615],
              [77.72990429081061, 30.318807749120914],
              [77.7302100626383, 30.318807749120914],
              [77.7302100626383, 30.319747781985615]]], null, false),
        {
          "label": "a38",
          "system:index": "0"
        }),
    a39 = 
    /* color: #ffc82d */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7300074980385, 30.321977429780823],
              [77.7300074980385, 30.321653288913108],
              [77.73030254103014, 30.321653288913108],
              [77.73030254103014, 30.321977429780823]]], null, false),
        {
          "label": "a39",
          "system:index": "0"
        }),
    a40 = 
    /* color: #00ffff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.73006820031382, 30.323318825699054],
              [77.73006820031382, 30.32300395032553],
              [77.7303337390063, 30.32300395032553],
              [77.7303337390063, 30.323318825699054]]], null, false),
        {
          "label": "a40",
          "system:index": "0"
        }),
    b0 = 
    /* color: #bf04c2 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.76863615209304, 30.261399304701246],
              [77.76863615209304, 30.25962004877523],
              [77.76927988225661, 30.25962004877523],
              [77.76927988225661, 30.261399304701246]]], null, false),
        {
          "label": "b0",
          "system:index": "0"
        }),
    b1 = 
    /* color: #ff0000 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.76937644178115, 30.26174681186158],
              [77.7694408147975, 30.262117484810194],
              [77.76965002710067, 30.262186985832308],
              [77.76981364172104, 30.26233757100944],
              [77.76982168847762, 30.262608624311977],
              [77.76972512895308, 30.262733725490648],
              [77.76952664548598, 30.262942227100925],
              [77.76906530553542, 30.26324339531198],
              [77.7685020416423, 30.263600162612896],
              [77.76829819375716, 30.263030260980994],
              [77.76885609323226, 30.26276615910333],
              [77.76890973741256, 30.2621499186264],
              [77.76860396558486, 30.261714377911737]]]),
        {
          "label": "b1",
          "system:index": "0"
        }),
    b2 = 
    /* color: #d63000 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.76825896263806, 30.263798401626765],
              [77.76605955124585, 30.26500305842482],
              [77.76587716103283, 30.26476212824755],
              [77.76622048378674, 30.264261732913514],
              [77.76666036606518, 30.263835468210168],
              [77.76695004463879, 30.263372134912004],
              [77.76719680786816, 30.263186800980588],
              [77.767529401786, 30.263196067685477],
              [77.76809803009716, 30.26308486716921]]]),
        {
          "label": "b2",
          "system:index": "0"
        }),
    b3 = 
    /* color: #98ff00 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7657806015083, 30.265382985580068],
              [77.76576987267224, 30.26605943760775],
              [77.76620975495068, 30.266559823780078],
              [77.76645651818005, 30.266949011262113],
              [77.76580205918042, 30.26715287075604],
              [77.76513687134472, 30.266671020360935],
              [77.76524415970532, 30.265855575843467],
              [77.76544800759045, 30.26539225207768]]]),
        {
          "label": "b3",
          "system:index": "0"
        }),
    b4 = 
    /* color: #0b4a8b */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.76805511475293, 30.268579875361247],
              [77.76816240311352, 30.267671783921443],
              [77.76890269280163, 30.267959038244335],
              [77.76899925232617, 30.268709602024103],
              [77.76972881317822, 30.26950649062092],
              [77.76924601555554, 30.269821537816966],
              [77.76876321793286, 30.26906171638791],
              [77.76802292824475, 30.268765199112977]]]),
        {
          "label": "b4",
          "system:index": "0"
        }),
    b5 = 
    /* color: #ffc82d */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.76996918859439, 30.26973814306937],
              [77.77032324018435, 30.270423831112723],
              [77.77096697034793, 30.271406024560562],
              [77.77097769918399, 30.271887851715505],
              [77.77077385129886, 30.27249013233334],
              [77.77088113965945, 30.272814435750703],
              [77.77039834203677, 30.27291635946059],
              [77.7696473235126, 30.272434537354158],
              [77.76995845975833, 30.27219362541406],
              [77.7702052229877, 30.27148015196909],
              [77.76992627325015, 30.2712299717409],
              [77.76936837377505, 30.270238510492206]]]),
        {
          "label": "b5",
          "system:index": "0"
        }),
    b6 = 
    /* color: #00ffff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77114936056094, 30.27302754884159],
              [77.77162142934756, 30.27376880816273],
              [77.7718252772327, 30.274065310323735],
              [77.77209349813418, 30.274361811589053],
              [77.7722758883472, 30.274667577580825],
              [77.7727264994617, 30.274936280241754],
              [77.77327367010074, 30.275242044443868],
              [77.77262993993716, 30.275575604305246],
              [77.77188965024905, 30.27511232641385],
              [77.77151414098697, 30.274676843202062],
              [77.7712137335773, 30.27425988938013],
              [77.77062364759402, 30.273889262273663],
              [77.77058073224978, 30.273333318989863]]]),
        {
          "label": "b6",
          "system:index": "0"
        }),
    b7 = 
    /* color: #bf04c2 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7737350100513, 30.275557073231575],
              [77.77390667142825, 30.275760914849485],
              [77.77409979047732, 30.27589063202228],
              [77.77430363836245, 30.275992552537744],
              [77.77455040159182, 30.27612226940439],
              [77.7746362322803, 30.27653921531452],
              [77.77481862249331, 30.277252651985417],
              [77.77489372434573, 30.27765106241492],
              [77.77434655370669, 30.277725185107098],
              [77.77440019788699, 30.27742869400256],
              [77.77422853651004, 30.277113671222537],
              [77.77409979047732, 30.27678011658854],
              [77.77390667142825, 30.27651141897563],
              [77.77343460264163, 30.276020349023625]]]),
        {
          "label": "b7",
          "system:index": "0"
        }),
    b8 = 
    /* color: #ff0000 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77490445318179, 30.277873430323464],
              [77.77494736852603, 30.27812359361825],
              [77.77495809736209, 30.278327429905502],
              [77.7747971648212, 30.278698040252124],
              [77.77470060529666, 30.27900379273443],
              [77.77445384206729, 30.27933733981046],
              [77.77405687513308, 30.279207627193394],
              [77.77434655370669, 30.278864814451467],
              [77.7745825881, 30.278484939473827],
              [77.77456113042788, 30.278021675315863]]]),
        {
          "label": "b8",
          "system:index": "0"
        }),
    b9 = 
    /* color: #00ff00 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77389057817416, 30.280291648793643],
              [77.77389057817416, 30.27930491167228],
              [77.77424462976413, 30.27930491167228],
              [77.77424462976413, 30.280291648793643]]], null, false),
        {
          "label": "b9",
          "system:index": "0"
        }),
    b10 = 
    /* color: #0000ff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77476497831302, 30.280967998084325],
              [77.77470060529666, 30.28142198334959],
              [77.77466305437045, 30.281764787158025],
              [77.7745825881, 30.281871334043704],
              [77.77437337579684, 30.28184817168711],
              [77.77435191812472, 30.281667505117884],
              [77.77439483346896, 30.281505368169963],
              [77.7743841046329, 30.28132933346603],
              [77.77438946905093, 30.281144033436505],
              [77.77437874021487, 30.28095873305704],
              [77.7743841046329, 30.280838287622757],
              [77.77465232553439, 30.280870715254206]]]),
        {
          "label": "b10",
          "system:index": "0"
        }),
    b11 = 
    /* color: #999900 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77464159669833, 30.282058948931002],
              [77.7746174568172, 30.28216549549725],
              [77.77450212182956, 30.28221413628252],
              [77.77433850707965, 30.28231141778072],
              [77.77418293895678, 30.28238553695268],
              [77.7739871376987, 30.282431861406742],
              [77.77375914993243, 30.28243881007295],
              [77.77357675971942, 30.282406382959724],
              [77.77336754741626, 30.28239711806826],
              [77.77315297069507, 30.282443442516847],
              [77.77304300012545, 30.28248513450187],
              [77.77287938537555, 30.282580099512764],
              [77.77275332155185, 30.282702859024738],
              [77.77245827856021, 30.2825152453689],
              [77.7725467914577, 30.28243881007295],
              [77.77267553749041, 30.28231605023037],
              [77.77286597433047, 30.282253512138414],
              [77.77293571176486, 30.282209503827605],
              [77.77306177558856, 30.282207187600157],
              [77.7731583351131, 30.282223401191033],
              [77.77332731428103, 30.28223034987202],
              [77.77351775112109, 30.28221413628229],
              [77.77364381494479, 30.282140016980843],
              [77.77387180271106, 30.28206358139256],
              [77.77425535860019, 30.282096008619092]]]),
        {
          "label": "b11",
          "system:index": "0"
        }),
    b12 = 
    /* color: #009999 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77246096076922, 30.282997749644366],
              [77.77240731658893, 30.28317841376423],
              [77.77237244787173, 30.283273378104102],
              [77.77230539264636, 30.283384555751063],
              [77.772420727634, 30.2834656227059],
              [77.77247168960528, 30.283623124026647],
              [77.77246900739627, 30.2837759927138],
              [77.77245827856021, 30.283831581268284],
              [77.7722222441669, 30.283794522235468],
              [77.77204521837191, 30.283755146997766],
              [77.7720076674457, 30.28361849163847],
              [77.77196743431048, 30.283391504349815],
              [77.77200230302768, 30.28325716468673],
              [77.77206399383502, 30.283148303100685],
              [77.77217664661364, 30.283018595521334]]]),
        {
          "label": "b12",
          "system:index": "0"
        }),
    b13 = 
    /* color: #ff00ff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7725280159946, 30.284500957638535],
              [77.77281233015017, 30.284371251847393],
              [77.77305909337954, 30.284542648749287],
              [77.77319320383029, 30.284695516003737],
              [77.77320393266635, 30.284945661906363],
              [77.77318783941226, 30.285135587073167],
              [77.77309127988772, 30.285302350331072],
              [77.77253874483065, 30.285320879564452],
              [77.77232416810946, 30.285311614948192],
              [77.772420727634, 30.285112425487135],
              [77.77247973623233, 30.284922500275524],
              [77.77254947366671, 30.284653824957974]]]),
        {
          "label": "b13",
          "system:index": "0"
        }),
    b14 = 
    /* color: #ff9999 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77151414098697, 30.28565903745898],
              [77.77151414098697, 30.285140219389692],
              [77.77214714231448, 30.285140219389692],
              [77.77214714231448, 30.28565903745898]]], null, false),
        {
          "label": "b14",
          "system:index": "0"
        }),
    b15 = 
    /* color: #99ff99 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77152486982303, 30.28645578843755],
              [77.77152486982303, 30.28570072807761],
              [77.7718252772327, 30.28570072807761],
              [77.7718252772327, 30.28645578843755]]], null, false),
        {
          "label": "b15",
          "system:index": "0"
        }),
    b16 = 
    /* color: #9999ff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77145431637155, 30.286434716209765],
              [77.77158574461328, 30.28661769012409],
              [77.77137653231011, 30.286728863981335],
              [77.77116463779794, 30.286844669948643],
              [77.7710305273472, 30.286914153463428],
              [77.77086423038827, 30.28698132081425],
              [77.77078912853585, 30.287034591439106],
              [77.77078376411782, 30.287157345377558],
              [77.7707623064457, 30.287259254190975],
              [77.7705262720524, 30.287256938082763],
              [77.77055577635156, 30.28713186815777],
              [77.77064965366708, 30.287106390931267],
              [77.77071670889245, 30.287069333135456],
              [77.77078912853585, 30.28694194685562],
              [77.77082399725305, 30.286849302184585],
              [77.77086423038827, 30.2867983475782],
              [77.77095006107675, 30.286749709065628],
              [77.77106271385537, 30.286710335013975],
              [77.7711565911709, 30.286645483600303],
              [77.7711941420971, 30.286538941899078],
              [77.77127997278558, 30.286494935510472],
              [77.77138457893716, 30.28647640649884]]]),
        {
          "label": "b16",
          "system:index": "0"
        }),
    b17 = 
    /* color: #ffff99 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77132923078786, 30.28837932575157],
              [77.77136141729603, 30.28851365840087],
              [77.77121657800923, 30.288747582057976],
              [77.77109051418553, 30.288881914202992],
              [77.7708517975832, 30.28901856223071],
              [77.77078474235783, 30.28915752613148],
              [77.77050579262028, 30.289162158258236],
              [77.77060235214482, 30.28899076942704],
              [77.77078474235783, 30.288851805290044],
              [77.77085984421025, 30.2887522142041],
              [77.77096176815282, 30.28870126058613],
              [77.77107978534947, 30.288668835542733],
              [77.77109051418553, 30.28857850857983],
              [77.77111733627568, 30.28841638305282],
              [77.77113074732075, 30.288370061424466]]]),
        {
          "label": "b17",
          "system:index": "0"
        }),
    b18 = 
    /* color: #99ffff */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77293562987796, 30.290590785676102],
              [77.77293562987796, 30.290317493810736],
              [77.77446985343448, 30.290317493810736],
              [77.77446985343448, 30.290590785676102]]], null, false),
        {
          "label": "b18",
          "system:index": "0"
        }),
    b19 = 
    /* color: #ff99ff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77531887294904, 30.29277614387113],
              [77.77563000919477, 30.29280856755676],
              [77.77565683128492, 30.293730322136135],
              [77.77547980548994, 30.29419738622649],
              [77.77512038948194, 30.294109380301045],
              [77.77534033062116, 30.293641558003277],
              [77.77534569503919, 30.293331219208245],
              [77.7752384066786, 30.29309035857108]]]),
        {
          "label": "b19",
          "system:index": "0"
        }),
    b20 = 
    /* color: #d63000 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77531252058945, 30.295189535716815],
              [77.77572021635972, 30.295161744661613],
              [77.77602062376938, 30.29538407288263],
              [77.77631566676102, 30.295601768777303],
              [77.77651415022812, 30.295754618797577],
              [77.77668044718705, 30.295981577479047],
              [77.77683065089188, 30.296449388614345],
              [77.77666971835099, 30.296671713916126],
              [77.77630493792496, 30.296708768084066],
              [77.77630493792496, 30.296328962198764],
              [77.77616009863816, 30.29580556875137],
              [77.77520523222886, 30.29541649570608]]]),
        {
          "label": "b20",
          "system:index": "0"
        }),
    b21 = 
    /* color: #98ff00 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77570948752366, 30.297270724937864],
              [77.77574167403183, 30.29700208344244],
              [77.77591333540879, 30.29693723883327],
              [77.7760957256218, 30.29670101882301],
              [77.77636931094132, 30.29683070831086],
              [77.7760420814415, 30.297496326327042],
              [77.77606890353165, 30.2978437056808],
              [77.77579531821213, 30.297820547095508]]]),
        {
          "label": "b21",
          "system:index": "0"
        }),
    b22 = 
    /* color: #0b4a8b */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7762566581627, 30.297996141827486],
              [77.77648196371995, 30.298292570775434],
              [77.77670190485917, 30.298561208735485],
              [77.77694866808854, 30.298862267643706],
              [77.7770505920311, 30.29906606084159],
              [77.77733490618668, 30.299260590317157],
              [77.77749047430954, 30.299394908063135],
              [77.77763531359635, 30.299561647078043],
              [77.77736172827683, 30.29968206952358],
              [77.77682528647385, 30.29908921913272],
              [77.77667508276902, 30.298894689317166],
              [77.77627275141678, 30.29841299477957],
              [77.77605817469559, 30.298121197899174]]]),
        {
          "label": "b22",
          "system:index": "0"
        }),
    b23 = 
    /* color: #ffc82d */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77754948290787, 30.300284179532824],
              [77.7774636522194, 30.3005342856805],
              [77.77737782153092, 30.3007149175015],
              [77.77760312708817, 30.300923338419906],
              [77.7772490754982, 30.3008399701057],
              [77.77708814295731, 30.300423127471408],
              [77.77731344851456, 30.300182284252717]]]),
        {
          "label": "b23",
          "system:index": "0"
        }),
    b24 = 
    /* color: #00ffff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.7778069749733, 30.3022888502622],
              [77.77810738238297, 30.302279587248712],
              [77.77795717867814, 30.3026315811468],
              [77.7779142633339, 30.302830735029335],
              [77.77786598357163, 30.303090097618735],
              [77.7778606191536, 30.303261461810273],
              [77.77754411848984, 30.303090097618735],
              [77.77758703383408, 30.302728842395805],
              [77.7777694240471, 30.302617686674772],
              [77.77786598357163, 30.302460215854275]]]),
        {
          "label": "b24",
          "system:index": "0"
        }),
    b25 = 
    /* color: #bf04c2 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77760312708817, 30.303398533181674],
              [77.7778069749733, 30.303430953355107],
              [77.7776621356865, 30.303611579839394],
              [77.77764604243241, 30.303782943119387],
              [77.77794644984208, 30.304079354572252],
              [77.778112746801, 30.304181245802187],
              [77.77839169653855, 30.304417447791522],
              [77.77812884005509, 30.304574915468258],
              [77.77777478846512, 30.3041858772192],
              [77.77757094057999, 30.304093248837106],
              [77.77745828780137, 30.30399598894172],
              [77.77737782153092, 30.30378757455523],
              [77.77751193198166, 30.303546739601277]]]),
        {
          "label": "b25",
          "system:index": "0"
        }),
    b26 = 
    /* color: #ff0000 */
    /* shown: false */
    /* displayProperties: [
      {
        "type": "rectangle"
      }
    ] */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.77804300936661, 30.305306673705992],
              [77.77804300936661, 30.304746277064364],
              [77.77840242537461, 30.304746277064364],
              [77.77840242537461, 30.305306673705992]]], null, false),
        {
          "label": "b26",
          "system:index": "0"
        }),
    x0 = 
    /* color: #d63000 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.88318948571387, 30.14444780349723],
              [77.88340406243506, 30.145375588223732],
              [77.88237409417334, 30.145384866026948],
              [77.88230972115699, 30.14455913812505]]]),
        {
          "label": "x0",
          "system:index": "0"
        }),
    x1 = 
    /* color: #98ff00 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.88294647264884, 30.14734391890152],
              [77.88431976366446, 30.146527485091806],
              [77.88539264727042, 30.14827167639288],
              [77.88363311815665, 30.148865436608403]]]),
        {
          "label": "x1",
          "system:index": "0"
        }),
    x2 = 
    /* color: #0b4a8b */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.88466308641837, 30.15075802344382],
              [77.88590763140128, 30.150424040170257],
              [77.88689468431876, 30.151834184077206],
              [77.886036377434, 30.15239081428036]]]),
        {
          "label": "x2",
          "system:index": "0"
        }),
    x3 = 
    /* color: #ffc82d */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.88620803881095, 30.15367097580658],
              [77.88753841448234, 30.153448326992145],
              [77.88788173723624, 30.15597165079075],
              [77.8865942769091, 30.156120079591865]]]),
        {
          "label": "x3",
          "system:index": "0"
        }),
    x4 = 
    /* color: #00ffff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.88736675310538, 30.157648161305772],
              [77.8883967213671, 30.15746262814438],
              [77.88994167375968, 30.159429261894037],
              [77.88865421343253, 30.160208483285018]]]),
        {
          "label": "x4",
          "system:index": "0"
        }),
    x5 = 
    /* color: #bf04c2 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.8915295414965, 30.160542433424656],
              [77.89320323992179, 30.160505327909434],
              [77.89470527697013, 30.1617298025387],
              [77.89294574785636, 30.16228637688864]]]),
        {
          "label": "x5",
          "system:index": "0"
        }),
    x6 = 
    /* color: #ff0000 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.8947911076586, 30.163571211969575],
              [77.89569232988761, 30.164016463384716],
              [77.89564941454337, 30.165723241847154],
              [77.89504859972403, 30.165760345398603]]]),
        {
          "label": "x6",
          "system:index": "0"
        }),
    x7 = 
    /* color: #00ff00 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.89528144649462, 30.166984754761696],
              [77.89622558406786, 30.166873445448037],
              [77.89751304439501, 30.16887699386328],
              [77.8964830761333, 30.169210914639834]]]),
        {
          "label": "x7",
          "system:index": "0"
        }),
    x8 = 
    /* color: #0000ff */
    /* shown: false */
    ee.Feature(
        ee.Geometry.Polygon(
            [[[77.89768470577197, 30.170472382919815],
              [77.89948715022997, 30.170175568306433],
              [77.90090335658984, 30.172401656118975],
              [77.89991630367236, 30.17277266586602]]]),
        {
          "label": "x8",
          "system:index": "0"
        }),
    f1 = 
    /* color: #8506d6 */
    /* shown: false */
    ee.Feature(
        ee.Geometry.MultiPolygon(
            [[[[77.60338231398663, 30.327556936868106],
               [77.60733052565655, 30.325334361694964],
               [77.60767384841046, 30.321333599293293],
               [77.61024876906475, 30.316739929858826],
               [77.61402531935772, 30.315406243553415],
               [77.61831685378155, 30.311108686423957],
               [77.61419698073468, 30.307403744537403],
               [77.61179372145733, 30.29836309862339],
               [77.61711522414288, 30.29406479426515],
               [77.6210634358128, 30.289618074266983],
               [77.63050481154522, 30.289173391179382],
               [77.63136311842999, 30.282651140966685],
               [77.62964650466046, 30.277462677762045],
               [77.63033315016827, 30.274201217623546],
               [77.63874455763897, 30.27464596856981],
               [77.6485292561253, 30.275387215668456],
               [77.65470906569561, 30.27716618586443],
               [77.65251347546283, 30.287446460083267],
               [77.64942357067767, 30.293227284752728],
               [77.64908024792376, 30.302268404208284],
               [77.65474507336322, 30.30582533744286],
               [77.65834996227923, 30.316196601241774],
               [77.65320012097064, 30.314418338940506],
               [77.65011021618548, 30.316789348170815],
               [77.648221941039, 30.32227208727195],
               [77.63672062878314, 30.31738209151413],
               [77.63517567639056, 30.31901211721882],
               [77.64341542248431, 30.326420983172266],
               [77.6459903431386, 30.331014198645676],
               [77.64169880871478, 30.33056970333736],
               [77.63242909435931, 30.326717326155034],
               [77.62899586682025, 30.32953253977204],
               [77.62418934826556, 30.331606855918345],
               [77.61903950695697, 30.33471824775292],
               [77.61612126354876, 30.334570088478834],
               [77.61097142224017, 30.333681128126326],
               [77.6075381947011, 30.330273372010968],
               [77.60358998303118, 30.333236644923584]]],
             [[[77.50931187941632, 30.32829778405139],
               [77.5115434773167, 30.321629957667202],
               [77.50639363600811, 30.31851815002818],
               [77.50244542433819, 30.31466529887344],
               [77.50484868361553, 30.3093303317964],
               [77.50776692702374, 30.312294238248978],
               [77.51188680007061, 30.31244243121872],
               [77.51480504347882, 30.310071316812635],
               [77.5163499958714, 30.314072539095612],
               [77.51549168898663, 30.317036302128173],
               [77.52046986891827, 30.319259065573796],
               [77.52270146681866, 30.323111736088705],
               [77.51497670485577, 30.329186793274058]]],
             [[[77.6608437665488, 30.26265064902877],
               [77.65243235907809, 30.25775768001314],
               [77.64453593573825, 30.248712459165052],
               [77.63732615790622, 30.243373905260878],
               [77.62479487738864, 30.23595876592777],
               [77.61930171332614, 30.231806043557743],
               [77.62385059123194, 30.22876572800096],
               [77.6288715809072, 30.23243650223764],
               [77.63389293036715, 30.235810457435132],
               [77.64110270819918, 30.24189092214877],
               [77.65226069770114, 30.244708570928083],
               [77.6551788867069, 30.241149616799213],
               [77.6666802533652, 30.246191511520294],
               [77.67045680365817, 30.244411980124124],
               [77.66650859198825, 30.242335819432128],
               [77.66462031684176, 30.237293532292554],
               [77.67543498358981, 30.24278071470143],
               [77.67897745756721, 30.238279883564875],
               [77.67805665327064, 30.236596811881775],
               [77.67467020614153, 30.234713776032173],
               [77.67287561061663, 30.23124438920225],
               [77.67220477002535, 30.227123678702178],
               [77.67051999500406, 30.223331975571988],
               [77.66560613517622, 30.220198393344283],
               [77.66401860428371, 30.2157115148792],
               [77.66393367133395, 30.21207821713151],
               [77.66702146625799, 30.215044592037938],
               [77.66659167902371, 30.217269498763994],
               [77.66989595293967, 30.217937096414076],
               [77.67180582999026, 30.22220159214135],
               [77.67602266438405, 30.22722625265319],
               [77.68087807530753, 30.22825538625333],
               [77.68822375617282, 30.23247345719757],
               [77.69311610541598, 30.235365530614732],
               [77.69775096259372, 30.233882426669663],
               [77.70307246527926, 30.229877934259797],
               [77.71337214789645, 30.227356503512546],
               [77.71697703681247, 30.231509413819108],
               [77.72109690985934, 30.236255382241787],
               [77.71423045478122, 30.248119300832276],
               [77.70719233832614, 30.25301274998228],
               [77.69174281440036, 30.259981787059505],
               [77.6889962323691, 30.260723144882114],
               [77.67852488837497, 30.264281584525047],
               [77.67337504706637, 30.268284674982766]]],
             [[[77.67852488837497, 30.166674364232197],
               [77.68178645453708, 30.169790983797867],
               [77.68367472968356, 30.172907504817818],
               [77.68178645453708, 30.177804695874805],
               [77.67903987250583, 30.176172325897557],
               [77.67080012641208, 30.16993939179535],
               [77.67080012641208, 30.164151314315244]]],
             [[[77.8069275983359, 30.13743270727621],
               [77.81568232856051, 30.130009587757314],
               [77.82100383124606, 30.137878076694562],
               [77.82615367255465, 30.15168353168457],
               [77.83542338691012, 30.15673020502469],
               [77.85224620185153, 30.166822776922192],
               [77.84297648749606, 30.16340922852125],
               [77.83593837104098, 30.161034516444296],
               [77.83353511176364, 30.163706063509142],
               [77.84297648749606, 30.168900531120222],
               [77.84640971503512, 30.17201708029671],
               [77.83834163031833, 30.17112664773073],
               [77.83834163031833, 30.17409472499806],
               [77.8428048261191, 30.180772572003836],
               [77.84452143988864, 30.183295196420303],
               [77.84005824408786, 30.18774672898369],
               [77.83044520697848, 30.19531387261133],
               [77.82272044501559, 30.199913224778392],
               [77.82151881537692, 30.186114523736045],
               [77.81774226508395, 30.18121774571227],
               [77.80383769355075, 30.175578730110246],
               [77.80006114325778, 30.173797921293854],
               [77.80212107978122, 30.165190225042632],
               [77.80606929145114, 30.159253444851775],
               [77.80486766181247, 30.150792915465374]]],
             [[[77.78495348944395, 30.018850161588663],
               [77.79696978583067, 30.031334704376118],
               [77.80589617743223, 30.04292608619983],
               [77.80314959540098, 30.048869858561165],
               [77.79696978583067, 30.048275497374622],
               [77.78632678045958, 30.041737288930555],
               [77.78117693915098, 30.03014576803887],
               [77.77911700262754, 30.02212007475108]]],
             [[[77.84407443312445, 30.146119924439013],
               [77.8471643379096, 30.141369610458646],
               [77.84709490790098, 30.128481979459636],
               [77.8539613629791, 30.13145134020472],
               [77.8697542096588, 30.12670032014327],
               [77.86769427313536, 30.143327889975566],
               [77.86220110907286, 30.146593690587117],
               [77.8536180402252, 30.152828100648467]]],
             [[[77.51226281714312, 30.21198442306129],
               [77.51758431982867, 30.21168773353823],
               [77.5247940976607, 30.219401370383405],
               [77.52925729346148, 30.223109634349857],
               [77.53200387549273, 30.229784157161244],
               [77.52633905005328, 30.231267322930215],
               [77.52548074316852, 30.23527175875033],
               [77.53509378027789, 30.252622428935492],
               [77.54367684912555, 30.268190934535127],
               [77.53148889136187, 30.262260366281996],
               [77.52496575903766, 30.255588048849386],
               [77.51878594946734, 30.248025541135885],
               [77.51535279174252, 30.244985491951628],
               [77.51260613989703, 30.241352256787682],
               [77.51432275366656, 30.23556837713728],
               [77.50419473242633, 30.21391288315541]]]]),
        {
          "lable": "potential1",
          "system:index": "0"
        }),
    shed = ee.FeatureCollection("users/donnywahyudi/mohand_mn_basin"),
    vil = ee.FeatureCollection("users/donnywahyudi/Villages"),
    agr = ee.FeatureCollection("users/donnywahyudi/agriculture"),
    ch1 = ee.FeatureCollection("users/donnywahyudi/mb27"),
    ch2 = ee.FeatureCollection("users/donnywahyudi/mb29"),
    ch3 = ee.FeatureCollection("users/donnywahyudi/mb34"),
    ch4 = ee.FeatureCollection("users/donnywahyudi/mb41"),
    ch5 = ee.FeatureCollection("users/donnywahyudi/mb44"),
    ch6 = ee.FeatureCollection("users/donnywahyudi/mb46"),
    ch7 = ee.FeatureCollection("users/donnywahyudi/mb54"),
    ch8 = ee.FeatureCollection("users/donnywahyudi/mb63"),
    channel = 
    /* color: #d63000 */
    /* shown: false */
    ee.FeatureCollection(
        [ee.Feature(
            ee.Geometry.Point([77.74847218517962, 30.233908949932076]),
            {
              "channel": 0,
              "system:index": "0"
            }),
        ee.Feature(
            ee.Geometry.Point([77.8243465137929, 30.195043666577188]),
            {
              "channel": 0,
              "system:index": "1"
            }),
        ee.Feature(
            ee.Geometry.Point([77.79756733898822, 30.220708342754488]),
            {
              "channel": 0,
              "system:index": "2"
            }),
        ee.Feature(
            ee.Geometry.Point([77.85747715954486, 30.177534441803854]),
            {
              "channel": 0,
              "system:index": "3"
            }),
        ee.Feature(
            ee.Geometry.Point([77.87704655651751, 30.17797963014353]),
            {
              "channel": 0,
              "system:index": "4"
            }),
        ee.Feature(
            ee.Geometry.Point([77.7379546950401, 30.217430643847923]),
            {
              "channel": 0,
              "system:index": "5"
            }),
        ee.Feature(
            ee.Geometry.Point([77.74567945700299, 30.22929683415664]),
            {
              "channel": 0,
              "system:index": "6"
            }),
        ee.Feature(
            ee.Geometry.Point([77.70413740378034, 30.263720364479205]),
            {
              "channel": 0,
              "system:index": "7"
            }),
        ee.Feature(
            ee.Geometry.Point([77.68285139303815, 30.25393428926861]),
            {
              "channel": 0,
              "system:index": "8"
            }),
        ee.Feature(
            ee.Geometry.Point([77.62019499045026, 30.232282840951296]),
            {
              "channel": 0,
              "system:index": "9"
            }),
        ee.Feature(
            ee.Geometry.Point([77.62946470480573, 30.310783684165497]),
            {
              "channel": 0,
              "system:index": "10"
            }),
        ee.Feature(
            ee.Geometry.Point([77.60047092519254, 30.331721713342393]),
            {
              "channel": 0,
              "system:index": "11"
            }),
        ee.Feature(
            ee.Geometry.Point([77.64338626943082, 30.325202293724306]),
            {
              "channel": 0,
              "system:index": "12"
            }),
        ee.Feature(
            ee.Geometry.Point([77.63308658681363, 30.314236836679672]),
            {
              "channel": 0,
              "system:index": "13"
            }),
        ee.Feature(
            ee.Geometry.Point([77.66759052358121, 30.28177782225145]),
            {
              "channel": 0,
              "system:index": "14"
            }),
        ee.Feature(
            ee.Geometry.Point([77.71308078847379, 30.28859658877639]),
            {
              "channel": 0,
              "system:index": "15"
            }),
        ee.Feature(
            ee.Geometry.Point([77.81964095130125, 30.246111532711783]),
            {
              "channel": 0,
              "system:index": "16"
            }),
        ee.Feature(
            ee.Geometry.Point([77.81071455969969, 30.238251686173943]),
            {
              "channel": 0,
              "system:index": "17"
            }),
        ee.Feature(
            ee.Geometry.Point([77.91595797603905, 30.155259884324515]),
            {
              "channel": 0,
              "system:index": "18"
            }),
        ee.Feature(
            ee.Geometry.Point([77.92042117183983, 30.1398219579826]),
            {
              "channel": 0,
              "system:index": "19"
            }),
        ee.Feature(
            ee.Geometry.Point([77.88711886471093, 30.15674417299554]),
            {
              "channel": 0,
              "system:index": "20"
            }),
        ee.Feature(
            ee.Geometry.Point([77.89501528805077, 30.164462113946364]),
            {
              "channel": 0,
              "system:index": "21"
            }),
        ee.Feature(
            ee.Geometry.Point([77.89879183834374, 30.16832085786349]),
            {
              "channel": 0,
              "system:index": "22"
            }),
        ee.Feature(
            ee.Geometry.Point([77.89450030391991, 30.12423313959465]),
            {
              "channel": 0,
              "system:index": "23"
            }),
        ee.Feature(
            ee.Geometry.Point([78.00435992288068, 29.99304044457234]),
            {
              "channel": 0,
              "system:index": "24"
            }),
        ee.Feature(
            ee.Geometry.Point([78.04229708718732, 29.983673569829413]),
            {
              "channel": 0,
              "system:index": "25"
            }),
        ee.Feature(
            ee.Geometry.Point([78.15679522561506, 30.038226907792847]),
            {
              "channel": 0,
              "system:index": "26"
            }),
        ee.Feature(
            ee.Geometry.Point([78.17035647439435, 30.02589185750698]),
            {
              "channel": 0,
              "system:index": "27"
            }),
        ee.Feature(
            ee.Geometry.Point([78.13035937356427, 30.024702855885824]),
            {
              "channel": 0,
              "system:index": "28"
            }),
        ee.Feature(
            ee.Geometry.Point([78.11113329934552, 30.037186661625913]),
            {
              "channel": 0,
              "system:index": "29"
            }),
        ee.Feature(
            ee.Geometry.Point([78.02530261086896, 30.001365813522778]),
            {
              "channel": 0,
              "system:index": "30"
            }),
        ee.Feature(
            ee.Geometry.Point([78.02375765847638, 30.036146404538457]),
            {
              "channel": 0,
              "system:index": "31"
            }),
        ee.Feature(
            ee.Geometry.Point([78.0273625473924, 30.049520306044265]),
            {
              "channel": 0,
              "system:index": "32"
            }),
        ee.Feature(
            ee.Geometry.Point([77.98513384866193, 30.056652315222415]),
            {
              "channel": 0,
              "system:index": "33"
            })]),
    forest = 
    /* color: #98ff00 */
    /* shown: false */
    ee.FeatureCollection(
        [ee.Feature(
            ee.Geometry.Point([77.96007128762677, 30.18538572340673]),
            {
              "forest": 1,
              "system:index": "0"
            }),
        ee.Feature(
            ee.Geometry.Point([78.06924792336896, 30.13195277973465]),
            {
              "forest": 1,
              "system:index": "1"
            }),
        ee.Feature(
            ee.Geometry.Point([78.07199450540021, 30.229297776489116]),
            {
              "forest": 1,
              "system:index": "2"
            }),
        ee.Feature(
            ee.Geometry.Point([78.2086369614549, 30.130765052187414]),
            {
              "forest": 1,
              "system:index": "3"
            }),
        ee.Feature(
            ee.Geometry.Point([78.08984728860334, 30.11354139704993]),
            {
              "forest": 1,
              "system:index": "4"
            }),
        ee.Feature(
            ee.Geometry.Point([77.9229924302049, 30.126013999098706]),
            {
              "forest": 1,
              "system:index": "5"
            }),
        ee.Feature(
            ee.Geometry.Point([77.85982104348615, 30.066012297693756]),
            {
              "forest": 1,
              "system:index": "6"
            }),
        ee.Feature(
            ee.Geometry.Point([77.92492342715305, 30.264406060401015]),
            {
              "forest": 1,
              "system:index": "7"
            }),
        ee.Feature(
            ee.Geometry.Point([77.75257540469211, 30.352732479320288]),
            {
              "forest": 1,
              "system:index": "8"
            }),
        ee.Feature(
            ee.Geometry.Point([77.80750704531711, 30.324287022303757]),
            {
              "forest": 1,
              "system:index": "9"
            }),
        ee.Feature(
            ee.Geometry.Point([77.95856905703586, 30.258475263544067]),
            {
              "forest": 1,
              "system:index": "10"
            }),
        ee.Feature(
            ee.Geometry.Point([77.7079434466843, 30.392423771529167]),
            {
              "forest": 1,
              "system:index": "11"
            }),
        ee.Feature(
            ee.Geometry.Point([77.91373126911441, 30.374831120447208]),
            {
              "forest": 1,
              "system:index": "12"
            }),
        ee.Feature(
            ee.Geometry.Point([77.84781330036441, 30.416882023479875]),
            {
              "forest": 1,
              "system:index": "13"
            }),
        ee.Feature(
            ee.Geometry.Point([77.65829914020816, 30.41214479866669]),
            {
              "forest": 1,
              "system:index": "14"
            }),
        ee.Feature(
            ee.Geometry.Point([77.53126972126284, 30.416882023479875]),
            {
              "forest": 1,
              "system:index": "15"
            }),
        ee.Feature(
            ee.Geometry.Point([77.50998371052066, 30.449444218450243]),
            {
              "forest": 1,
              "system:index": "16"
            }),
        ee.Feature(
            ee.Geometry.Point([77.82309406208316, 30.45773104102936]),
            {
              "forest": 1,
              "system:index": "17"
            }),
        ee.Feature(
            ee.Geometry.Point([77.85330646442691, 30.478445013969424]),
            {
              "forest": 1,
              "system:index": "18"
            }),
        ee.Feature(
            ee.Geometry.Point([77.92540424274722, 30.35528017347018]),
            {
              "forest": 1,
              "system:index": "19"
            }),
        ee.Feature(
            ee.Geometry.Point([77.73520343708316, 30.34876232266268]),
            {
              "forest": 1,
              "system:index": "20"
            }),
        ee.Feature(
            ee.Geometry.Point([77.75442951130191, 30.266956051502646]),
            {
              "forest": 1,
              "system:index": "21"
            }),
        ee.Feature(
            ee.Geometry.Point([77.81485431598941, 30.221280864368204]),
            {
              "forest": 1,
              "system:index": "22"
            }),
        ee.Feature(
            ee.Geometry.Point([77.7262770454816, 30.25568752385585]),
            {
              "forest": 1,
              "system:index": "23"
            }),
        ee.Feature(
            ee.Geometry.Point([77.78189533161441, 30.224840732435464]),
            {
              "forest": 1,
              "system:index": "24"
            }),
        ee.Feature(
            ee.Geometry.Point([77.95081012653628, 30.107891112755386]),
            {
              "forest": 1,
              "system:index": "25"
            }),
        ee.Feature(
            ee.Geometry.Point([78.0723463814191, 30.084722206230044]),
            {
              "forest": 1,
              "system:index": "26"
            }),
        ee.Feature(
            ee.Geometry.Point([78.19182269977847, 30.038368109017632]),
            {
              "forest": 1,
              "system:index": "27"
            }),
        ee.Feature(
            ee.Geometry.Point([78.1437575142316, 30.02112835969684]),
            {
              "forest": 1,
              "system:index": "28"
            }),
        ee.Feature(
            ee.Geometry.Point([78.09225910114566, 29.967606604852563]),
            {
              "forest": 1,
              "system:index": "29"
            }),
        ee.Feature(
            ee.Geometry.Point([78.0119215767316, 30.030045845777902]),
            {
              "forest": 1,
              "system:index": "30"
            }),
        ee.Feature(
            ee.Geometry.Point([77.95630329059878, 30.075215443177495]),
            {
              "forest": 1,
              "system:index": "31"
            }),
        ee.Feature(
            ee.Geometry.Point([77.96316974567691, 30.128679096872826]),
            {
              "forest": 1,
              "system:index": "32"
            }),
        ee.Feature(
            ee.Geometry.Point([77.97415607380191, 30.10551506457395]),
            {
              "forest": 1,
              "system:index": "33"
            }),
        ee.Feature(
            ee.Geometry.Point([77.85673969196597, 30.20051239966234]),
            {
              "forest": 1,
              "system:index": "34"
            }),
        ee.Feature(
            ee.Geometry.Point([77.76953571247378, 30.240858544046638]),
            {
              "forest": 1,
              "system:index": "35"
            }),
        ee.Feature(
            ee.Geometry.Point([77.61730405583596, 30.350276356388296]),
            {
              "forest": 1,
              "system:index": "36"
            }),
        ee.Feature(
            ee.Geometry.Point([77.68047544255471, 30.40122173457448]),
            {
              "forest": 1,
              "system:index": "37"
            })]),
    agriculture = 
    /* color: #0b4a8b */
    /* shown: false */
    ee.FeatureCollection(
        [ee.Feature(
            ee.Geometry.Point([77.66883230651828, 30.235305678740584]),
            {
              "agriculture": 2,
              "system:index": "0"
            }),
        ee.Feature(
            ee.Geometry.Point([77.68728590454074, 30.23715952833569]),
            {
              "agriculture": 2,
              "system:index": "1"
            }),
        ee.Feature(
            ee.Geometry.Point([77.64202444299907, 30.264315706073663]),
            {
              "agriculture": 2,
              "system:index": "2"
            }),
        ee.Feature(
            ee.Geometry.Point([77.6474317763731, 30.274641084198116]),
            {
              "agriculture": 2,
              "system:index": "3"
            }),
        ee.Feature(
            ee.Geometry.Point([77.6518091414854, 30.26715417434187]),
            {
              "agriculture": 2,
              "system:index": "4"
            }),
        ee.Feature(
            ee.Geometry.Point([77.60419762799333, 30.275329381459677]),
            {
              "agriculture": 2,
              "system:index": "5"
            }),
        ee.Feature(
            ee.Geometry.Point([77.6097766227443, 30.287336811538196]),
            {
              "agriculture": 2,
              "system:index": "6"
            }),
        ee.Feature(
            ee.Geometry.Point([77.59754865759196, 30.3150204095142]),
            {
              "agriculture": 2,
              "system:index": "7"
            }),
        ee.Feature(
            ee.Geometry.Point([77.61694639318766, 30.316502287901326]),
            {
              "agriculture": 2,
              "system:index": "8"
            }),
        ee.Feature(
            ee.Geometry.Point([77.61625974767985, 30.325244914190925]),
            {
              "agriculture": 2,
              "system:index": "9"
            }),
        ee.Feature(
            ee.Geometry.Point([77.6270744144279, 30.32079960848833]),
            {
              "agriculture": 2,
              "system:index": "10"
            }),
        ee.Feature(
            ee.Geometry.Point([77.64218061559977, 30.30761068143884]),
            {
              "agriculture": 2,
              "system:index": "11"
            }),
        ee.Feature(
            ee.Geometry.Point([77.6376809349628, 30.250708401264202]),
            {
              "agriculture": 2,
              "system:index": "12"
            }),
        ee.Feature(
            ee.Geometry.Point([77.67656855295463, 30.227431913775646]),
            {
              "agriculture": 2,
              "system:index": "13"
            }),
        ee.Feature(
            ee.Geometry.Point([77.66008906076713, 30.224020466001814]),
            {
              "agriculture": 2,
              "system:index": "14"
            }),
        ee.Feature(
            ee.Geometry.Point([77.71450571726128, 30.236034169593278]),
            {
              "agriculture": 2,
              "system:index": "15"
            }),
        ee.Feature(
            ee.Geometry.Point([77.72223047922417, 30.23232639299711]),
            {
              "agriculture": 2,
              "system:index": "16"
            }),
        ee.Feature(
            ee.Geometry.Point([77.71828226755424, 30.230398293903455]),
            {
              "agriculture": 2,
              "system:index": "17"
            }),
        ee.Feature(
            ee.Geometry.Point([77.75775960316561, 30.21771845816927]),
            {
              "agriculture": 2,
              "system:index": "18"
            }),
        ee.Feature(
            ee.Geometry.Point([77.71415761341952, 30.2055541630658]),
            {
              "agriculture": 2,
              "system:index": "19"
            }),
        ee.Feature(
            ee.Geometry.Point([77.71364262928866, 30.19709760863252]),
            {
              "agriculture": 2,
              "system:index": "20"
            }),
        ee.Feature(
            ee.Geometry.Point([77.72291234364413, 30.20332882443922]),
            {
              "agriculture": 2,
              "system:index": "21"
            }),
        ee.Feature(
            ee.Geometry.Point([77.77750066151522, 30.21208153277226]),
            {
              "agriculture": 2,
              "system:index": "22"
            }),
        ee.Feature(
            ee.Geometry.Point([77.78436711659334, 30.204070609571744]),
            {
              "agriculture": 2,
              "system:index": "23"
            }),
        ee.Feature(
            ee.Geometry.Point([77.79192021717928, 30.19947145163777]),
            {
              "agriculture": 2,
              "system:index": "24"
            }),
        ee.Feature(
            ee.Geometry.Point([77.77561238636873, 30.206147578202156]),
            {
              "agriculture": 2,
              "system:index": "25"
            }),
        ee.Feature(
            ee.Geometry.Point([77.78642705311678, 30.19932308812686]),
            {
              "agriculture": 2,
              "system:index": "26"
            }),
        ee.Feature(
            ee.Geometry.Point([77.78471043934725, 30.191014374683736]),
            {
              "agriculture": 2,
              "system:index": "27"
            }),
        ee.Feature(
            ee.Geometry.Point([77.77870229115389, 30.197691074749887]),
            {
              "agriculture": 2,
              "system:index": "28"
            }),
        ee.Feature(
            ee.Geometry.Point([77.77252248158358, 30.210301383972052]),
            {
              "agriculture": 2,
              "system:index": "29"
            }),
        ee.Feature(
            ee.Geometry.Point([77.76977589955233, 30.200658351675802]),
            {
              "agriculture": 2,
              "system:index": "30"
            }),
        ee.Feature(
            ee.Geometry.Point([77.78144887318514, 30.205257454155934]),
            {
              "agriculture": 2,
              "system:index": "31"
            }),
        ee.Feature(
            ee.Geometry.Point([77.7761273704996, 30.204070609571744]),
            {
              "agriculture": 2,
              "system:index": "32"
            }),
        ee.Feature(
            ee.Geometry.Point([77.8097730003824, 30.18700813734585]),
            {
              "agriculture": 2,
              "system:index": "33"
            }),
        ee.Feature(
            ee.Geometry.Point([77.8090863548746, 30.195910665665963]),
            {
              "agriculture": 2,
              "system:index": "34"
            }),
        ee.Feature(
            ee.Geometry.Point([77.81440785756014, 30.183150125152096]),
            {
              "agriculture": 2,
              "system:index": "35"
            }),
        ee.Feature(
            ee.Geometry.Point([77.79947331776522, 30.185969456619887]),
            {
              "agriculture": 2,
              "system:index": "36"
            }),
        ee.Feature(
            ee.Geometry.Point([77.8068054614661, 30.18346745214358]),
            {
              "agriculture": 2,
              "system:index": "37"
            }),
        ee.Feature(
            ee.Geometry.Point([77.80302891117313, 30.18361583954402]),
            {
              "agriculture": 2,
              "system:index": "38"
            }),
        ee.Feature(
            ee.Geometry.Point([77.85389480620749, 30.14362056208772]),
            {
              "agriculture": 2,
              "system:index": "39"
            }),
        ee.Feature(
            ee.Geometry.Point([77.84754333526023, 30.158909469622177]),
            {
              "agriculture": 2,
              "system:index": "40"
            }),
        ee.Feature(
            ee.Geometry.Point([77.82908973723777, 30.149261405783292]),
            {
              "agriculture": 2,
              "system:index": "41"
            }),
        ee.Feature(
            ee.Geometry.Point([77.80703125029929, 30.15475349630034]),
            {
              "agriculture": 2,
              "system:index": "42"
            }),
        ee.Feature(
            ee.Geometry.Point([77.84805303353461, 30.127840140648114]),
            {
              "agriculture": 2,
              "system:index": "43"
            }),
        ee.Feature(
            ee.Geometry.Point([77.86103703672381, 30.12135085086428]),
            {
              "agriculture": 2,
              "system:index": "44"
            }),
        ee.Feature(
            ee.Geometry.Point([77.88073999253574, 30.123653375549058]),
            {
              "agriculture": 2,
              "system:index": "45"
            }),
        ee.Feature(
            ee.Geometry.Point([77.8537891563541, 30.11073498551908]),
            {
              "agriculture": 2,
              "system:index": "46"
            }),
        ee.Feature(
            ee.Geometry.Point([77.89571579733887, 30.102198897367142]),
            {
              "agriculture": 2,
              "system:index": "47"
            }),
        ee.Feature(
            ee.Geometry.Point([77.88919266501465, 30.09425330478295]),
            {
              "agriculture": 2,
              "system:index": "48"
            }),
        ee.Feature(
            ee.Geometry.Point([77.9206054255721, 30.099599942045568]),
            {
              "agriculture": 2,
              "system:index": "49"
            })]),
    urban = 
    /* color: #ffc82d */
    /* shown: false */
    ee.FeatureCollection(
        [ee.Feature(
            ee.Geometry.Point([78.05408455228329, 29.962428008928455]),
            {
              "urban": 3,
              "system:index": "0"
            }),
        ee.Feature(
            ee.Geometry.Point([78.05236793851375, 29.943092611293434]),
            {
              "urban": 3,
              "system:index": "1"
            }),
        ee.Feature(
            ee.Geometry.Point([78.06326843595028, 29.939373834560485]),
            {
              "urban": 3,
              "system:index": "2"
            }),
        ee.Feature(
            ee.Geometry.Point([78.07210899686336, 29.96279980664609]),
            {
              "urban": 3,
              "system:index": "3"
            }),
        ee.Feature(
            ee.Geometry.Point([78.04387070035457, 29.967633050405148]),
            {
              "urban": 3,
              "system:index": "4"
            }),
        ee.Feature(
            ee.Geometry.Point([78.03640343045711, 29.933572265269685]),
            {
              "urban": 3,
              "system:index": "5"
            }),
        ee.Feature(
            ee.Geometry.Point([78.0628392825079, 29.9306713537688]),
            {
              "urban": 3,
              "system:index": "6"
            }),
        ee.Feature(
            ee.Geometry.Point([78.07356811856747, 29.934613597488536]),
            {
              "urban": 3,
              "system:index": "7"
            }),
        ee.Feature(
            ee.Geometry.Point([78.07090736722469, 29.931712716345082]),
            {
              "urban": 3,
              "system:index": "8"
            }),
        ee.Feature(
            ee.Geometry.Point([78.08034874295711, 29.92791912879021]),
            {
              "urban": 3,
              "system:index": "9"
            }),
        ee.Feature(
            ee.Geometry.Point([78.09390999173641, 29.924571725569457]),
            {
              "urban": 3,
              "system:index": "10"
            }),
        ee.Feature(
            ee.Geometry.Point([78.10738540982723, 29.92702649893872]),
            {
              "urban": 3,
              "system:index": "11"
            }),
        ee.Feature(
            ee.Geometry.Point([78.1331346163702, 29.932159011256147]),
            {
              "urban": 3,
              "system:index": "12"
            }),
        ee.Feature(
            ee.Geometry.Point([78.12060333585262, 29.924422949480178]),
            {
              "urban": 3,
              "system:index": "13"
            }),
        ee.Feature(
            ee.Geometry.Point([78.14085937833309, 29.92278639782227]),
            {
              "urban": 3,
              "system:index": "14"
            }),
        ee.Feature(
            ee.Geometry.Point([78.14489342069149, 29.926282634613866]),
            {
              "urban": 3,
              "system:index": "15"
            }),
        ee.Feature(
            ee.Geometry.Point([78.06798912381649, 29.956032870501332]),
            {
              "urban": 3,
              "system:index": "16"
            }),
        ee.Feature(
            ee.Geometry.Point([78.10300804471493, 29.92330712172277]),
            {
              "urban": 3,
              "system:index": "17"
            }),
        ee.Feature(
            ee.Geometry.Point([78.07657219266414, 29.95038101038629]),
            {
              "urban": 3,
              "system:index": "18"
            }),
        ee.Feature(
            ee.Geometry.Point([77.62263366462933, 30.257922471394263]),
            {
              "urban": 3,
              "system:index": "19"
            }),
        ee.Feature(
            ee.Geometry.Point([77.62160369636761, 30.256143152478835]),
            {
              "urban": 3,
              "system:index": "20"
            }),
        ee.Feature(
            ee.Geometry.Point([77.64391967537152, 30.271414590682124]),
            {
              "urban": 3,
              "system:index": "21"
            }),
        ee.Feature(
            ee.Geometry.Point([77.57783004524457, 30.24680119937182]),
            {
              "urban": 3,
              "system:index": "22"
            }),
        ee.Feature(
            ee.Geometry.Point([77.601862638018, 30.266225533437503]),
            {
              "urban": 3,
              "system:index": "23"
            }),
        ee.Feature(
            ee.Geometry.Point([77.58418151619183, 30.234492190882392]),
            {
              "urban": 3,
              "system:index": "24"
            }),
        ee.Feature(
            ee.Geometry.Point([77.56838866951215, 30.228559588158838]),
            {
              "urban": 3,
              "system:index": "25"
            }),
        ee.Feature(
            ee.Geometry.Point([77.56495544197308, 30.220995000549085]),
            {
              "urban": 3,
              "system:index": "26"
            }),
        ee.Feature(
            ee.Geometry.Point([77.60649749519574, 30.226483092637206]),
            {
              "urban": 3,
              "system:index": "27"
            }),
        ee.Feature(
            ee.Geometry.Point([77.60924407722699, 30.224703204433943]),
            {
              "urban": 3,
              "system:index": "28"
            }),
        ee.Feature(
            ee.Geometry.Point([77.63053008796918, 30.244725089158003]),
            {
              "urban": 3,
              "system:index": "29"
            }),
        ee.Feature(
            ee.Geometry.Point([77.61372912878161, 30.171234354753828]),
            {
              "urban": 3,
              "system:index": "30"
            }),
        ee.Feature(
            ee.Geometry.Point([77.61750567907458, 30.170121303949763]),
            {
              "urban": 3,
              "system:index": "31"
            }),
        ee.Feature(
            ee.Geometry.Point([77.63844836706286, 30.173163613037204]),
            {
              "urban": 3,
              "system:index": "32"
            }),
        ee.Feature(
            ee.Geometry.Point([77.65123713964587, 30.175315433490248]),
            {
              "urban": 3,
              "system:index": "33"
            }),
        ee.Feature(
            ee.Geometry.Point([77.66625751012927, 30.18599963908113]),
            {
              "urban": 3,
              "system:index": "34"
            }),
        ee.Feature(
            ee.Geometry.Point([77.67037738317615, 30.172421595089936]),
            {
              "urban": 3,
              "system:index": "35"
            }),
        ee.Feature(
            ee.Geometry.Point([77.67488036784812, 30.189311684299856]),
            {
              "urban": 3,
              "system:index": "36"
            }),
        ee.Feature(
            ee.Geometry.Point([77.68990073833152, 30.193911316833447]),
            {
              "urban": 3,
              "system:index": "37"
            }),
        ee.Feature(
            ee.Geometry.Point([77.7108434263198, 30.190053575045976]),
            {
              "urban": 3,
              "system:index": "38"
            }),
        ee.Feature(
            ee.Geometry.Point([77.70157371196433, 30.190276141180018]),
            {
              "urban": 3,
              "system:index": "39"
            }),
        ee.Feature(
            ee.Geometry.Point([77.71959815654441, 30.18478602972918]),
            {
              "urban": 3,
              "system:index": "40"
            }),
        ee.Feature(
            ee.Geometry.Point([77.70454507661786, 30.16422896124635]),
            {
              "urban": 3,
              "system:index": "41"
            }),
        ee.Feature(
            ee.Geometry.Point([77.7465162832829, 30.170165441824434]),
            {
              "urban": 3,
              "system:index": "42"
            }),
        ee.Feature(
            ee.Geometry.Point([77.79981714082685, 30.149608853832838]),
            {
              "urban": 3,
              "system:index": "43"
            }),
        ee.Feature(
            ee.Geometry.Point([77.79209602747676, 30.173139856567875]),
            {
              "urban": 3,
              "system:index": "44"
            }),
        ee.Feature(
            ee.Geometry.Point([77.7721833077502, 30.17618207247349]),
            {
              "urban": 3,
              "system:index": "45"
            }),
        ee.Feature(
            ee.Geometry.Point([77.59674275806844, 30.305171228948783]),
            {
              "urban": 3,
              "system:index": "46"
            }),
        ee.Feature(
            ee.Geometry.Point([77.58232320240438, 30.290201497231283]),
            {
              "urban": 3,
              "system:index": "47"
            }),
        ee.Feature(
            ee.Geometry.Point([77.56968071631213, 30.227020226796245]),
            {
              "urban": 3,
              "system:index": "48"
            }),
        ee.Feature(
            ee.Geometry.Point([77.57347685300589, 30.19960359421261]),
            {
              "urban": 3,
              "system:index": "49"
            }),
        ee.Feature(
            ee.Geometry.Point([77.60077101194143, 30.204796169257126]),
            {
              "urban": 3,
              "system:index": "50"
            }),
        ee.Feature(
            ee.Geometry.Point([77.85461495602914, 30.36085233818477]),
            {
              "urban": 3,
              "system:index": "51"
            }),
        ee.Feature(
            ee.Geometry.Point([77.84637520993539, 30.35611239609627]),
            {
              "urban": 3,
              "system:index": "52"
            }),
        ee.Feature(
            ee.Geometry.Point([77.8525550195057, 30.36085233818477]),
            {
              "urban": 3,
              "system:index": "53"
            }),
        ee.Feature(
            ee.Geometry.Point([77.8528983422596, 30.353742338926196]),
            {
              "urban": 3,
              "system:index": "54"
            }),
        ee.Feature(
            ee.Geometry.Point([77.83744881833383, 30.377440326572202]),
            {
              "urban": 3,
              "system:index": "55"
            }),
        ee.Feature(
            ee.Geometry.Point([77.86148141110726, 30.374478392188514]),
            {
              "urban": 3,
              "system:index": "56"
            }),
        ee.Feature(
            ee.Geometry.Point([78.0718415696456, 30.345915575310254]),
            {
              "urban": 3,
              "system:index": "57"
            }),
        ee.Feature(
            ee.Geometry.Point([78.00695356915732, 30.313318862431355]),
            {
              "urban": 3,
              "system:index": "58"
            }),
        ee.Feature(
            ee.Geometry.Point([78.04025587628622, 30.31539352192294]),
            {
              "urban": 3,
              "system:index": "59"
            }),
        ee.Feature(
            ee.Geometry.Point([78.01999983380576, 30.323395368491852]),
            {
              "urban": 3,
              "system:index": "60"
            }),
        ee.Feature(
            ee.Geometry.Point([78.044719072087, 30.29938786843009]),
            {
              "urban": 3,
              "system:index": "61"
            }),
        ee.Feature(
            ee.Geometry.Point([78.02137312482138, 30.292866297423625]),
            {
              "urban": 3,
              "system:index": "62"
            }),
        ee.Feature(
            ee.Geometry.Point([78.06772169659872, 30.289012437981423]),
            {
              "urban": 3,
              "system:index": "63"
            }),
        ee.Feature(
            ee.Geometry.Point([78.03647932599326, 30.281600744257418]),
            {
              "urban": 3,
              "system:index": "64"
            })]),
    river = 
    /* color: #00ffff */
    /* shown: false */
    ee.FeatureCollection(
        [ee.Feature(
            ee.Geometry.Point([77.74221631813259, 30.47986521287128]),
            {
              "river": 4,
              "system:index": "0"
            }),
        ee.Feature(
            ee.Geometry.Point([77.73020002174587, 30.470026768551893]),
            {
              "river": 4,
              "system:index": "1"
            }),
        ee.Feature(
            ee.Geometry.Point([77.7191278629324, 30.463220646488146]),
            {
              "river": 4,
              "system:index": "2"
            }),
        ee.Feature(
            ee.Geometry.Point([77.70659658241482, 30.45789378444122]),
            {
              "river": 4,
              "system:index": "3"
            }),
        ee.Feature(
            ee.Geometry.Point([77.69432279396267, 30.4484970817386]),
            {
              "river": 4,
              "system:index": "4"
            }),
        ee.Feature(
            ee.Geometry.Point([77.6772106868522, 30.446374540894624]),
            {
              "river": 4,
              "system:index": "5"
            }),
        ee.Feature(
            ee.Geometry.Point([77.65645989888591, 30.439367628253393]),
            {
              "river": 4,
              "system:index": "6"
            }),
        ee.Feature(
            ee.Geometry.Point([77.65336999410076, 30.436111561489177]),
            {
              "river": 4,
              "system:index": "7"
            }),
        ee.Feature(
            ee.Geometry.Point([77.6506234120695, 30.43440948331932]),
            {
              "river": 4,
              "system:index": "8"
            }),
        ee.Feature(
            ee.Geometry.Point([77.63028153890056, 30.43115325100334]),
            {
              "river": 4,
              "system:index": "9"
            }),
        ee.Feature(
            ee.Geometry.Point([77.6184962715135, 30.433897007576924]),
            {
              "river": 4,
              "system:index": "10"
            }),
        ee.Feature(
            ee.Geometry.Point([77.6104281867967, 30.43056675121861]),
            {
              "river": 4,
              "system:index": "11"
            }),
        ee.Feature(
            ee.Geometry.Point([77.6078532661424, 30.428938584503246]),
            {
              "river": 4,
              "system:index": "12"
            }),
        ee.Feature(
            ee.Geometry.Point([77.59415704541773, 30.424580960378442]),
            {
              "river": 4,
              "system:index": "13"
            }),
        ee.Feature(
            ee.Geometry.Point([77.57705634871792, 30.41988295875361]),
            {
              "river": 4,
              "system:index": "14"
            }),
        ee.Feature(
            ee.Geometry.Point([77.57877296248745, 30.41233313006861]),
            {
              "river": 4,
              "system:index": "15"
            }),
        ee.Feature(
            ee.Geometry.Point([77.57697051802944, 30.405318659567097]),
            {
              "river": 4,
              "system:index": "16"
            }),
        ee.Feature(
            ee.Geometry.Point([77.57619804183315, 30.40169131280578]),
            {
              "river": 4,
              "system:index": "17"
            }),
        ee.Feature(
            ee.Geometry.Point([77.57619804183315, 30.397249480196894]),
            {
              "river": 4,
              "system:index": "18"
            }),
        ee.Feature(
            ee.Geometry.Point([77.58217223267039, 30.38972719291154]),
            {
              "river": 4,
              "system:index": "19"
            }),
        ee.Feature(
            ee.Geometry.Point([77.58277304748972, 30.38284142296393]),
            {
              "river": 4,
              "system:index": "20"
            }),
        ee.Feature(
            ee.Geometry.Point([77.58603461365183, 30.376621600801045]),
            {
              "river": 4,
              "system:index": "21"
            }),
        ee.Feature(
            ee.Geometry.Point([77.59188396595391, 30.359054196351895]),
            {
              "river": 4,
              "system:index": "22"
            }),
        ee.Feature(
            ee.Geometry.Point([77.59402973316583, 30.34957390825857]),
            {
              "river": 4,
              "system:index": "23"
            }),
        ee.Feature(
            ee.Geometry.Point([77.59093982838067, 30.332140689277356]),
            {
              "river": 4,
              "system:index": "24"
            }),
        ee.Feature(
            ee.Geometry.Point([77.5871632780877, 30.323398678454677]),
            {
              "river": 4,
              "system:index": "25"
            }),
        ee.Feature(
            ee.Geometry.Point([77.58527500294122, 30.31828646315213]),
            {
              "river": 4,
              "system:index": "26"
            }),
        ee.Feature(
            ee.Geometry.Point([77.58381588123711, 30.315545020434012]),
            {
              "river": 4,
              "system:index": "27"
            }),
        ee.Feature(
            ee.Geometry.Point([77.56209501041482, 30.294463841258125]),
            {
              "river": 4,
              "system:index": "28"
            }),
        ee.Feature(
            ee.Geometry.Point([77.5610650421531, 30.292388738790105]),
            {
              "river": 4,
              "system:index": "29"
            }),
        ee.Feature(
            ee.Geometry.Point([77.54801877750467, 30.28141961072203]),
            {
              "river": 4,
              "system:index": "30"
            }),
        ee.Feature(
            ee.Geometry.Point([77.53008016361306, 30.258143210704176]),
            {
              "river": 4,
              "system:index": "31"
            }),
        ee.Feature(
            ee.Geometry.Point([78.29062751964966, 30.093025724062574]),
            {
              "river": 4,
              "system:index": "32"
            }),
        ee.Feature(
            ee.Geometry.Point([78.31225685314575, 30.121835095702142]),
            {
              "river": 4,
              "system:index": "33"
            }),
        ee.Feature(
            ee.Geometry.Point([78.29200081066529, 30.085896336054702]),
            {
              "river": 4,
              "system:index": "34"
            }),
        ee.Feature(
            ee.Geometry.Point([78.29062751964966, 30.07861788896655]),
            {
              "river": 4,
              "system:index": "35"
            }),
        ee.Feature(
            ee.Geometry.Point([78.28873924450318, 30.075201290334125]),
            {
              "river": 4,
              "system:index": "36"
            }),
        ee.Feature(
            ee.Geometry.Point([78.3062487049524, 30.102976301912495]),
            {
              "river": 4,
              "system:index": "37"
            }),
        ee.Feature(
            ee.Geometry.Point([78.27964119152466, 30.061350854538183]),
            {
              "river": 4,
              "system:index": "38"
            }),
        ee.Feature(
            ee.Geometry.Point([78.27569297985474, 30.052881938335265]),
            {
              "river": 4,
              "system:index": "39"
            }),
        ee.Feature(
            ee.Geometry.Point([78.26184786843162, 30.032083834355372]),
            {
              "river": 4,
              "system:index": "40"
            }),
        ee.Feature(
            ee.Geometry.Point([78.21275271462302, 29.986597205947277]),
            {
              "river": 4,
              "system:index": "41"
            }),
        ee.Feature(
            ee.Geometry.Point([78.18465121920624, 29.96964587607253]),
            {
              "river": 4,
              "system:index": "42"
            }),
        ee.Feature(
            ee.Geometry.Point([78.1822479599289, 29.962656327764314]),
            {
              "river": 4,
              "system:index": "43"
            }),
        ee.Feature(
            ee.Geometry.Point([78.18207629855195, 29.957302298718748]),
            {
              "river": 4,
              "system:index": "44"
            }),
        ee.Feature(
            ee.Geometry.Point([78.17057498629609, 29.944659697050486]),
            {
              "river": 4,
              "system:index": "45"
            }),
        ee.Feature(
            ee.Geometry.Point([78.1631747385744, 29.927481992609856]),
            {
              "river": 4,
              "system:index": "46"
            }),
        ee.Feature(
            ee.Geometry.Point([78.16197310893573, 29.91944800048141]),
            {
              "river": 4,
              "system:index": "47"
            }),
        ee.Feature(
            ee.Geometry.Point([78.16214477031268, 29.907618998896776]),
            {
              "river": 4,
              "system:index": "48"
            })]),
    image = ee.ImageCollection("LANDSAT/LC08/C01/T2_TOA"),
    channels = ee.FeatureCollection("users/donnywahyudi/channel");

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
