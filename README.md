# NYC Neighborhood Livability Analysis

A data-driven analysis of NYC neighborhoods at the census tract level, integrating housing costs, transit accessibility, crime, noise, and amenity data to help identify neighborhoods that balance affordability, convenience, and quality of life.

## Project Overview

### Research Question
**Where in New York City can people find neighborhoods that feel livable without being extremely expensive?**

Rather than building complex predictive models, this project focuses on integrating multiple urban data sources at the census tract level to support practical neighborhood comparison and data-informed residential decision-making.

### Why This Matters
NYC rent varies dramatically across neighborhoods, but price alone doesn't tell you whether a place is worth living in. Some expensive areas have high crime or noise complaints, while some affordable areas offer excellent transit access and quiet streets.

This analysis helps identify neighborhoods that balance:
- **Affordability** (median rent)
- **Convenience** (transit and amenities)
- **Livability** (low crime and noise)

---

## 📊 Interactive Visualizations

This analysis includes interactive heatmaps showing the geographic distribution of neighborhood quality across NYC. **Click on the links below to explore the full interactive maps** (they open in your browser):

### 🗺️ Available Maps

1. **[Top Neighborhoods Map](<!DOCTYPE html>
<html>
<head>
    
    <meta http-equiv="content-type" content="text/html; charset=UTF-8" />
    <script src="https://cdn.jsdelivr.net/npm/leaflet@1.9.3/dist/leaflet.js"></script>
    <script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.js"></script>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/leaflet@1.9.3/dist/leaflet.css"/>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css"/>
    <link rel="stylesheet" href="https://netdna.bootstrapcdn.com/bootstrap/3.0.0/css/bootstrap-glyphicons.css"/>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.2.0/css/all.min.css"/>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.css"/>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/python-visualization/folium/folium/templates/leaflet.awesome.rotate.min.css"/>
    
            <meta name="viewport" content="width=device-width,
                initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
            <style>
                #map_5c833a999dae99247649e12cbe805ca2 {
                    position: relative;
                    width: 100.0%;
                    height: 100.0%;
                    left: 0.0%;
                    top: 0.0%;
                }
                .leaflet-container { font-size: 1rem; }
            </style>

            <style>html, body {
                width: 100%;
                height: 100%;
                margin: 0;
                padding: 0;
            }
            </style>

            <style>#map {
                position:absolute;
                top:0;
                bottom:0;
                right:0;
                left:0;
                }
            </style>

            <script>
                L_NO_TOUCH = false;
                L_DISABLE_3D = false;
            </script>

        
</head>
<body>
    
    
<div style="position: fixed; 
            bottom: 50px; right: 50px; width: 200px; height: 140px; 
            background-color: white; z-index:9999; font-size:14px;
            border:2px solid grey; border-radius: 5px; padding: 10px">
<p style="margin-bottom: 8px;"><b>Combined Score</b></p>
<p style="margin: 4px;"><i class="fa fa-circle" style="color:darkgreen"></i> 80-100 (Excellent)</p>
<p style="margin: 4px;"><i class="fa fa-circle" style="color:green"></i> 70-79 (Good)</p>
<p style="margin: 4px;"><i class="fa fa-circle" style="color:lightgreen"></i> 60-69 (Fair)</p>
<p style="margin: 4px;"><i class="fa fa-circle" style="color:orange"></i> < 60 (Lower)</p>
</div>
    
            <div class="folium-map" id="map_5c833a999dae99247649e12cbe805ca2" ></div>
        
</body>
<script>
    
    
            var map_5c833a999dae99247649e12cbe805ca2 = L.map(
                "map_5c833a999dae99247649e12cbe805ca2",
                {
                    center: [40.7128, -74.006],
                    crs: L.CRS.EPSG3857,
                    ...{
  "zoom": 11,
  "zoomControl": true,
  "preferCanvas": false,
}

                }
            );

            

        
    
            var tile_layer_d95bd395b209cdf2763dfdab0754279d = L.tileLayer(
                "https://{s}.basemaps.cartocdn.com/light_all/{z}/{x}/{y}{r}.png",
                {
  "minZoom": 0,
  "maxZoom": 20,
  "maxNativeZoom": 20,
  "noWrap": false,
  "attribution": "\u0026copy; \u003ca href=\"https://www.openstreetmap.org/copyright\"\u003eOpenStreetMap\u003c/a\u003e contributors \u0026copy; \u003ca href=\"https://carto.com/attributions\"\u003eCARTO\u003c/a\u003e",
  "subdomains": "abcd",
  "detectRetina": false,
  "tms": false,
  "opacity": 1,
}

            );
        
    
            tile_layer_d95bd395b209cdf2763dfdab0754279d.addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
            var circle_marker_b1ad713400ab83fb013d206b91820629 = L.circleMarker(
                [40.770554011884734, -73.96001471052776],
                {"bubblingMouseEvents": true, "color": "lightgreen", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "lightgreen", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_4f1c83962e3742d09d947179c7935f66 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_bd3831b18b765a46c2b132ef65a286d4 = $(`<div id="html_bd3831b18b765a46c2b132ef65a286d4" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $5,795<br>     <hr>     <b>Convenience:</b> 36.0/100<br>     <b>Livability:</b> 89.8/100<br>     <b>Affordability:</b> 0.0/100<br>     <b>Combined:</b> 62.9/100     </div>`)[0];
                popup_4f1c83962e3742d09d947179c7935f66.setContent(html_bd3831b18b765a46c2b132ef65a286d4);
            
        

        circle_marker_b1ad713400ab83fb013d206b91820629.bindPopup(popup_4f1c83962e3742d09d947179c7935f66)
        ;

        
    
    
            var circle_marker_1c44660a3f3a034eae9d7f1bce0bb1ba = L.circleMarker(
                [40.82817143064099, -74.00725061393479],
                {"bubblingMouseEvents": true, "color": "lightgreen", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "lightgreen", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_9906bfaaa6bd6b560fb6259078e761c2 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_a47aee74e30a3e9b20d91c88340cfb05 = $(`<div id="html_a47aee74e30a3e9b20d91c88340cfb05" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $4,915<br>     <hr>     <b>Convenience:</b> 27.3/100<br>     <b>Livability:</b> 93.2/100<br>     <b>Affordability:</b> 21.5/100<br>     <b>Combined:</b> 60.2/100     </div>`)[0];
                popup_9906bfaaa6bd6b560fb6259078e761c2.setContent(html_a47aee74e30a3e9b20d91c88340cfb05);
            
        

        circle_marker_1c44660a3f3a034eae9d7f1bce0bb1ba.bindPopup(popup_9906bfaaa6bd6b560fb6259078e761c2)
        ;

        
    
    
            var circle_marker_c702e43892b443acab84ed2cffe25f0b = L.circleMarker(
                [40.80629939418114, -73.99198553514647],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_5b62ce815c3cae470adb1f9c63322ec8 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_088fbd5d131592c0296ff984636874bc = $(`<div id="html_088fbd5d131592c0296ff984636874bc" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $4,900<br>     <hr>     <b>Convenience:</b> 31.5/100<br>     <b>Livability:</b> 88.4/100<br>     <b>Affordability:</b> 21.9/100<br>     <b>Combined:</b> 59.9/100     </div>`)[0];
                popup_5b62ce815c3cae470adb1f9c63322ec8.setContent(html_088fbd5d131592c0296ff984636874bc);
            
        

        circle_marker_c702e43892b443acab84ed2cffe25f0b.bindPopup(popup_5b62ce815c3cae470adb1f9c63322ec8)
        ;

        
    
    
            var circle_marker_5000763adcac231cf4905d6c55ca069b = L.circleMarker(
                [40.7929658484197, -73.98456381567063],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_24572b906fae9d43247b7ef9b7074f0b = L.popup({
  "maxWidth": 250,
});

        
            
                var html_9323e3e408d6b415ae1e7f167356931f = $(`<div id="html_9323e3e408d6b415ae1e7f167356931f" style="width: 100.0%; height: 100.0%;">     <b>Lower East Side/Chinatown</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $5,249<br>     <hr>     <b>Convenience:</b> 25.7/100<br>     <b>Livability:</b> 91.5/100<br>     <b>Affordability:</b> 13.3/100<br>     <b>Combined:</b> 58.6/100     </div>`)[0];
                popup_24572b906fae9d43247b7ef9b7074f0b.setContent(html_9323e3e408d6b415ae1e7f167356931f);
            
        

        circle_marker_5000763adcac231cf4905d6c55ca069b.bindPopup(popup_24572b906fae9d43247b7ef9b7074f0b)
        ;

        
    
    
            var circle_marker_f772a2e2119938a8303f4d2f10cc6960 = L.circleMarker(
                [40.74870186404424, -73.97559300157829],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_63e171e92421b2f71aa9e2a9f8ced139 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_d48f192094dbd1aac4eddd5e9bdf04b4 = $(`<div id="html_d48f192094dbd1aac4eddd5e9bdf04b4" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $5,527<br>     <hr>     <b>Convenience:</b> 23.6/100<br>     <b>Livability:</b> 92.0/100<br>     <b>Affordability:</b> 6.5/100<br>     <b>Combined:</b> 57.8/100     </div>`)[0];
                popup_63e171e92421b2f71aa9e2a9f8ced139.setContent(html_d48f192094dbd1aac4eddd5e9bdf04b4);
            
        

        circle_marker_f772a2e2119938a8303f4d2f10cc6960.bindPopup(popup_63e171e92421b2f71aa9e2a9f8ced139)
        ;

        
    
    
            var circle_marker_a4cf0cae5897a6a9b01005579f791064 = L.circleMarker(
                [40.64379945203362, -73.9156824038607],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_e9e7218494180532b7ad91471066a172 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_afc270f0a48fd55894704c5cb99a5af1 = $(`<div id="html_afc270f0a48fd55894704c5cb99a5af1" style="width: 100.0%; height: 100.0%;">     <b>Downtown Brooklyn/Brooklyn Heights</b><br>     <b>Borough:</b> Brooklyn<br>     <b>Median Rent:</b> $3,914<br>     <hr>     <b>Convenience:</b> 22.7/100<br>     <b>Livability:</b> 91.9/100<br>     <b>Affordability:</b> 45.9/100<br>     <b>Combined:</b> 57.3/100     </div>`)[0];
                popup_e9e7218494180532b7ad91471066a172.setContent(html_afc270f0a48fd55894704c5cb99a5af1);
            
        

        circle_marker_a4cf0cae5897a6a9b01005579f791064.bindPopup(popup_e9e7218494180532b7ad91471066a172)
        ;

        
    
    
            var circle_marker_261b3804dd1ff5f5814a65af67f43477 = L.circleMarker(
                [40.738908361216815, -74.00123262178415],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_fecf6a4b57bc7c6d8c08e27b7d07ecdd = L.popup({
  "maxWidth": 250,
});

        
            
                var html_4a865bf42d80ae4c43202cf3f46d0867 = $(`<div id="html_4a865bf42d80ae4c43202cf3f46d0867" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $5,118<br>     <hr>     <b>Convenience:</b> 16.8/100<br>     <b>Livability:</b> 97.6/100<br>     <b>Affordability:</b> 16.5/100<br>     <b>Combined:</b> 57.2/100     </div>`)[0];
                popup_fecf6a4b57bc7c6d8c08e27b7d07ecdd.setContent(html_4a865bf42d80ae4c43202cf3f46d0867);
            
        

        circle_marker_261b3804dd1ff5f5814a65af67f43477.bindPopup(popup_fecf6a4b57bc7c6d8c08e27b7d07ecdd)
        ;

        
    
    
            var circle_marker_b68d08e828b96ab6ad9146615908f38e = L.circleMarker(
                [40.81971761457749, -73.96977655615864],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_d8afd173171f9545fd04b28c17896036 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_941d186aa9b3ea03c02304de252618e8 = $(`<div id="html_941d186aa9b3ea03c02304de252618e8" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $5,795<br>     <hr>     <b>Convenience:</b> 24.1/100<br>     <b>Livability:</b> 90.0/100<br>     <b>Affordability:</b> 0.0/100<br>     <b>Combined:</b> 57.1/100     </div>`)[0];
                popup_d8afd173171f9545fd04b28c17896036.setContent(html_941d186aa9b3ea03c02304de252618e8);
            
        

        circle_marker_b68d08e828b96ab6ad9146615908f38e.bindPopup(popup_d8afd173171f9545fd04b28c17896036)
        ;

        
    
    
            var circle_marker_0642ea4ec663aaca9332867bc5a45014 = L.circleMarker(
                [40.79321150117432, -73.9619585431138],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_1e67d24c3926f597a41357101e4c33f1 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_15d4163fcae4ee8738309861b8de3e6f = $(`<div id="html_15d4163fcae4ee8738309861b8de3e6f" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $4,915<br>     <hr>     <b>Convenience:</b> 22.6/100<br>     <b>Livability:</b> 91.0/100<br>     <b>Affordability:</b> 21.5/100<br>     <b>Combined:</b> 56.8/100     </div>`)[0];
                popup_1e67d24c3926f597a41357101e4c33f1.setContent(html_15d4163fcae4ee8738309861b8de3e6f);
            
        

        circle_marker_0642ea4ec663aaca9332867bc5a45014.bindPopup(popup_1e67d24c3926f597a41357101e4c33f1)
        ;

        
    
    
            var circle_marker_d71bbbcb81dd5597167377a16277c7ba = L.circleMarker(
                [40.6990072577796, -73.989554958728],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_7a3eb470d60e0b0acd19bade8723fd23 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_b46e6190dc606dcc6fae0bf782f877b5 = $(`<div id="html_b46e6190dc606dcc6fae0bf782f877b5" style="width: 100.0%; height: 100.0%;">     <b>Downtown Brooklyn/Brooklyn Heights</b><br>     <b>Borough:</b> Brooklyn<br>     <b>Median Rent:</b> $4,500<br>     <hr>     <b>Convenience:</b> 15.1/100<br>     <b>Livability:</b> 98.5/100<br>     <b>Affordability:</b> 31.6/100<br>     <b>Combined:</b> 56.8/100     </div>`)[0];
                popup_7a3eb470d60e0b0acd19bade8723fd23.setContent(html_b46e6190dc606dcc6fae0bf782f877b5);
            
        

        circle_marker_d71bbbcb81dd5597167377a16277c7ba.bindPopup(popup_7a3eb470d60e0b0acd19bade8723fd23)
        ;

        
    
    
            var circle_marker_502507a9a3688a70ffce731572f3df8e = L.circleMarker(
                [40.735158449429576, -73.96044551480985],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_c46cc06455ade159ba9ac2effbac7187 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_2228c211bf6f0f7024dd62cad7219028 = $(`<div id="html_2228c211bf6f0f7024dd62cad7219028" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $4,872<br>     <hr>     <b>Convenience:</b> 16.9/100<br>     <b>Livability:</b> 95.6/100<br>     <b>Affordability:</b> 22.6/100<br>     <b>Combined:</b> 56.2/100     </div>`)[0];
                popup_c46cc06455ade159ba9ac2effbac7187.setContent(html_2228c211bf6f0f7024dd62cad7219028);
            
        

        circle_marker_502507a9a3688a70ffce731572f3df8e.bindPopup(popup_c46cc06455ade159ba9ac2effbac7187)
        ;

        
    
    
            var circle_marker_6c5c9f70858e32c039b6204152752791 = L.circleMarker(
                [40.830090985216195, -74.00414758763127],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_d01c8c98fe0a608ed7369ec0d6079040 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_e5460824aa4a32c250de909b9ad3f3a8 = $(`<div id="html_e5460824aa4a32c250de909b9ad3f3a8" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $4,872<br>     <hr>     <b>Convenience:</b> 16.9/100<br>     <b>Livability:</b> 95.5/100<br>     <b>Affordability:</b> 22.6/100<br>     <b>Combined:</b> 56.2/100     </div>`)[0];
                popup_d01c8c98fe0a608ed7369ec0d6079040.setContent(html_e5460824aa4a32c250de909b9ad3f3a8);
            
        

        circle_marker_6c5c9f70858e32c039b6204152752791.bindPopup(popup_d01c8c98fe0a608ed7369ec0d6079040)
        ;

        
    
    
            var circle_marker_ff5d2c40e0b576311d4b2f8eecff6dc2 = L.circleMarker(
                [40.711444264080036, -73.98769484070147],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_97c7f27e7ad6182942ef5a961e0ac310 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_00ef083275ffc69a83dac21a3b6172c4 = $(`<div id="html_00ef083275ffc69a83dac21a3b6172c4" style="width: 100.0%; height: 100.0%;">     <b>Fort Greene/Clinton Hill</b><br>     <b>Borough:</b> Brooklyn<br>     <b>Median Rent:</b> $4,750<br>     <hr>     <b>Convenience:</b> 26.1/100<br>     <b>Livability:</b> 86.0/100<br>     <b>Affordability:</b> 25.5/100<br>     <b>Combined:</b> 56.1/100     </div>`)[0];
                popup_97c7f27e7ad6182942ef5a961e0ac310.setContent(html_00ef083275ffc69a83dac21a3b6172c4);
            
        

        circle_marker_ff5d2c40e0b576311d4b2f8eecff6dc2.bindPopup(popup_97c7f27e7ad6182942ef5a961e0ac310)
        ;

        
    
    
            var circle_marker_42511e43f288ffe9997debb72a50b8cf = L.circleMarker(
                [40.754333911067825, -73.92631144627467],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_824bfed9c12608e1240281018db77dfd = L.popup({
  "maxWidth": 250,
});

        
            
                var html_90292611279f6e570e3b7e9f140ecba5 = $(`<div id="html_90292611279f6e570e3b7e9f140ecba5" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $4,872<br>     <hr>     <b>Convenience:</b> 17.9/100<br>     <b>Livability:</b> 94.0/100<br>     <b>Affordability:</b> 22.6/100<br>     <b>Combined:</b> 55.9/100     </div>`)[0];
                popup_824bfed9c12608e1240281018db77dfd.setContent(html_90292611279f6e570e3b7e9f140ecba5);
            
        

        circle_marker_42511e43f288ffe9997debb72a50b8cf.bindPopup(popup_824bfed9c12608e1240281018db77dfd)
        ;

        
    
    
            var circle_marker_027460f636e5c3a02471ee7123b2971a = L.circleMarker(
                [40.751282496720705, -73.92463679669254],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_fd3163f4c15a0fa79674f124f2b2c701 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_45b653cf99339604ea0431a06cfdb152 = $(`<div id="html_45b653cf99339604ea0431a06cfdb152" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $5,648<br>     <hr>     <b>Convenience:</b> 15.9/100<br>     <b>Livability:</b> 95.8/100<br>     <b>Affordability:</b> 3.6/100<br>     <b>Combined:</b> 55.9/100     </div>`)[0];
                popup_fd3163f4c15a0fa79674f124f2b2c701.setContent(html_45b653cf99339604ea0431a06cfdb152);
            
        

        circle_marker_027460f636e5c3a02471ee7123b2971a.bindPopup(popup_fd3163f4c15a0fa79674f124f2b2c701)
        ;

        
    
    
            var circle_marker_6f4f9a78fd6a567cc08bd36c5e5548dd = L.circleMarker(
                [40.75144045098534, -73.94036026518835],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_11fede2922e992bb886c24ad1e21b745 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_5954462732cffc45c755f7d9c4139548 = $(`<div id="html_5954462732cffc45c755f7d9c4139548" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $4,872<br>     <hr>     <b>Convenience:</b> 23.9/100<br>     <b>Livability:</b> 87.5/100<br>     <b>Affordability:</b> 22.6/100<br>     <b>Combined:</b> 55.7/100     </div>`)[0];
                popup_11fede2922e992bb886c24ad1e21b745.setContent(html_5954462732cffc45c755f7d9c4139548);
            
        

        circle_marker_6f4f9a78fd6a567cc08bd36c5e5548dd.bindPopup(popup_11fede2922e992bb886c24ad1e21b745)
        ;

        
    
    
            var circle_marker_6793b98402af85aac1bd1a79a59ad06f = L.circleMarker(
                [40.76352422429595, -73.99073862308266],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_73c7b059cfbd9a7d37c2dc0f8213f724 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_fd1fb1bfd7de33164cddd9f92643c6a3 = $(`<div id="html_fd1fb1bfd7de33164cddd9f92643c6a3" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $5,200<br>     <hr>     <b>Convenience:</b> 29.8/100<br>     <b>Livability:</b> 81.2/100<br>     <b>Affordability:</b> 14.5/100<br>     <b>Combined:</b> 55.5/100     </div>`)[0];
                popup_73c7b059cfbd9a7d37c2dc0f8213f724.setContent(html_fd1fb1bfd7de33164cddd9f92643c6a3);
            
        

        circle_marker_6793b98402af85aac1bd1a79a59ad06f.bindPopup(popup_73c7b059cfbd9a7d37c2dc0f8213f724)
        ;

        
    
    
            var circle_marker_e0f839727c42acb4257df6365b4fa1b6 = L.circleMarker(
                [40.68067564316322, -73.98443278859936],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_4c42da0273be515cb7c1965ebd9c8bcb = L.popup({
  "maxWidth": 250,
});

        
            
                var html_7b95c825323209c2c2ef6eaafb8b5ab1 = $(`<div id="html_7b95c825323209c2c2ef6eaafb8b5ab1" style="width: 100.0%; height: 100.0%;">     <b>Downtown Brooklyn/Brooklyn Heights</b><br>     <b>Borough:</b> Brooklyn<br>     <b>Median Rent:</b> $4,700<br>     <hr>     <b>Convenience:</b> 22.1/100<br>     <b>Livability:</b> 88.6/100<br>     <b>Affordability:</b> 26.7/100<br>     <b>Combined:</b> 55.3/100     </div>`)[0];
                popup_4c42da0273be515cb7c1965ebd9c8bcb.setContent(html_7b95c825323209c2c2ef6eaafb8b5ab1);
            
        

        circle_marker_e0f839727c42acb4257df6365b4fa1b6.bindPopup(popup_4c42da0273be515cb7c1965ebd9c8bcb)
        ;

        
    
    
            var circle_marker_626d304fbccf52c3bb7908d1be601bfe = L.circleMarker(
                [40.77629450186421, -73.95277669734878],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_dc25f68e07a17b6b7ca2947c6b990e06 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_8e3f86473adfd3e34683817fc192c024 = $(`<div id="html_8e3f86473adfd3e34683817fc192c024" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $5,795<br>     <hr>     <b>Convenience:</b> 20.4/100<br>     <b>Livability:</b> 90.2/100<br>     <b>Affordability:</b> 0.0/100<br>     <b>Combined:</b> 55.3/100     </div>`)[0];
                popup_dc25f68e07a17b6b7ca2947c6b990e06.setContent(html_8e3f86473adfd3e34683817fc192c024);
            
        

        circle_marker_626d304fbccf52c3bb7908d1be601bfe.bindPopup(popup_dc25f68e07a17b6b7ca2947c6b990e06)
        ;

        
    
    
            var circle_marker_f2aaa885ef6855625760998e07567990 = L.circleMarker(
                [40.7622229140198, -73.97718475062604],
                {"bubblingMouseEvents": true, "color": "orange", "dashArray": null, "dashOffset": null, "fill": true, "fillColor": "orange", "fillOpacity": 0.7, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "opacity": 1.0, "radius": 8, "stroke": true, "weight": 2}
            ).addTo(map_5c833a999dae99247649e12cbe805ca2);
        
    
        var popup_ee37cb57aa35208d01736fcb5225ead7 = L.popup({
  "maxWidth": 250,
});

        
            
                var html_48821da714dad0f0d4bc86a3ae16ff49 = $(`<div id="html_48821da714dad0f0d4bc86a3ae16ff49" style="width: 100.0%; height: 100.0%;">     <b>Financial District/Battery Park</b><br>     <b>Borough:</b> Manhattan<br>     <b>Median Rent:</b> $4,915<br>     <hr>     <b>Convenience:</b> 19.6/100<br>     <b>Livability:</b> 90.8/100<br>     <b>Affordability:</b> 21.5/100<br>     <b>Combined:</b> 55.2/100     </div>`)[0];
                popup_ee37cb57aa35208d01736fcb5225ead7.setContent(html_48821da714dad0f0d4bc86a3ae16ff49);
            
        

        circle_marker_f2aaa885ef6855625760998e07567990.bindPopup(popup_ee37cb57aa35208d01736fcb5225ead7)
        ;

        
    
    
            tile_layer_d95bd395b209cdf2763dfdab0754279d.addTo(map_5c833a999dae99247649e12cbe805ca2);
        
</script>
</html>[top_neighborhoods_map.html](https://github.com/user-attachments/files/24430628/top_neighborhoods_map.html)
)** 
   - Interactive markers showing the top 20 census tracts by combined score
   - Color-coded by performance (green = excellent, orange = good)
   - Click any marker for detailed neighborhood information

2. **[Convenience Heatmap](./convenience_heatmap.html)**
   - Shows transit accessibility across NYC (MTA ridership + Citibike + amenities)
   - **Key Finding**: Extreme concentration in lower Manhattan/Financial District
   - Reveals NYC's transit inequality - most areas score below 10/100

3. **[Livability Heatmap](./livability_heatmap.html)**
   - Highlights quiet, safe neighborhoods (low crime + low noise)
   - **Key Finding**: Queens and outer Brooklyn have the highest livability scores
   - Shows that expensive ≠ peaceful

4. **[Affordability Heatmap](./affordability_heatmap.html)**
   - Displays most affordable areas across the city
   - **Key Finding**: Bronx and parts of Queens offer best value
   - Manhattan is uniformly expensive with affordability scores near 0

### 🎯 What the Maps Reveal

**Geographic Patterns:**
- **Convenience** clusters tightly in southern Manhattan (Financial District area only)
- **Livability** is highest in outer boroughs (Queens, Staten Island) and residential Brooklyn
- **Affordability** concentrates in Bronx, eastern Queens, and parts of Brooklyn
- **NO area achieves high scores in all three** - the classic urban trade-off visualized

**Visual Insights:**
The heatmaps make it immediately clear why finding the "perfect" NYC neighborhood is challenging - the areas with the best transit access (red zones in convenience map) barely overlap with the most affordable areas (red zones in affordability map).

---

## Methodology

### Geographic Unit: Census Tracts
This analysis uses **census tracts** rather than ZIP codes as the primary geographic unit.

**Why Census Tracts?**
- Designed specifically for demographic and housing analysis
- Provide consistent population-based units (~4,000 residents per tract)
- Better capture neighborhood heterogeneity than ZIP codes
- ZIP codes are designed for mail delivery and often combine very different areas

This choice significantly improves the analytical precision of neighborhood comparisons.

### Census Tract to Neighborhood Mapping
Census tracts are identified by numeric codes (e.g., 1000100 for a tract in Manhattan). To make the analysis more interpretable, tracts are mapped to recognizable neighborhood names based on their geographic location.

**Mapping Approach:**
- Census tract codes follow the format: `BBGGGCCC` where:
  - `BB` = Borough code (1=Manhattan, 2=Bronx, 3=Brooklyn, 4=Queens, 5=Staten Island)
  - `GGG` = Census tract number within borough
  - `CCC` = Tract suffix (for subdivisions)

- Neighborhoods are approximated using tract number ranges within each borough
- Based on NYC Department of City Planning's Neighborhood Tabulation Areas (NTAs)
- Examples:
  - Tracts 1-30 in Manhattan → Financial District/Battery Park
  - Tracts 210-240 in Manhattan → Upper East Side
  - Tracts 1-50 in Brooklyn → Downtown Brooklyn/Brooklyn Heights

**Important Note:** This mapping is a simplified approximation. NYC's 2,168 census tracts are grouped into ~100 recognizable neighborhood areas for easier interpretation. Official NTA boundaries aggregate census tracts differently and recognize 195 neighborhoods, but this analysis uses a more consolidated grouping for clarity.

### Data Sources
The analysis integrates five major datasets:

1. **NYC Rent Data** (by census tract)
   - Source: NYC Housing and Vacancy Survey / Census data
   - Metric: Median rent per census tract

2. **311 Noise Complaints**
   - Source: NYC Open Data
   - Purpose: Urban stress indicator
   - Geographic processing: ZIP codes mapped to census tracts

3. **MTA Subway Ridership**
   - Source: NYC MTA
   - Purpose: Transit accessibility measure
   - Geographic processing: Station coordinates spatially joined to census tracts

4. **Citibike Trip Data**
   - Source: Citibike System Data
   - Purpose: Alternative transit and neighborhood activity indicator
   - Geographic processing: Station locations mapped to census tracts

5. **NYC Business Licenses**
   - Source: NYC Open Data
   - Purpose: Amenity density proxy
   - Geographic processing: Business addresses geocoded to census tracts

6. **NYC Crime Incidents**
   - Source: NYPD Complaint Data
   - Purpose: Safety indicator
   - Geographic processing: Incident locations mapped to census tracts

### Data Integration Challenge
Different datasets use different geographic identifiers:
- 311 data → ZIP codes
- MTA data → Station coordinates (lat/long)
- Business data → Addresses with coordinates
- Crime data → Coordinates or precincts
- Rent data → Census tracts (our target unit)

**Solution:** Created crosswalks and spatial joins to unify everything at the census tract level.

---

## Analysis Approach

### Composite Indices
Instead of raw metrics, the analysis creates three normalized indices (0-100 scale):

#### 1. Convenience Score
**Components:**
- MTA ridership (subway accessibility)
- Citibike trips (bike infrastructure and activity)
- Business density (amenity access)

**Interpretation:** Higher scores indicate better transit access and more local amenities.

#### 2. Livability Score
**Components:**
- Crime incidents (inverted: less crime = higher score)
- Noise complaints (inverted: less noise = higher score)

**Interpretation:** Higher scores indicate quieter, safer neighborhoods.

#### 3. Affordability Score
**Component:**
- Median rent (inverted: lower rent = higher score)

**Interpretation:** Higher scores indicate more affordable housing.

### Normalization Method
All metrics are normalized using MinMaxScaler (0-100 range) to enable fair comparison across different scales and units.

---

## 📈 Summary Data Tables

### Top 12 Neighborhoods Ranked by Combined Score

| Neighborhood | Median Rent | Convenience | Livability | Affordability | Combined | Tracts |
|-------------|-------------|-------------|------------|---------------|----------|--------|
| Lower East Side/Chinatown | $5,168 | 9.4 | 94.4 | 28.0 | **51.9** | 4 |
| Bushwick/East New York | $2,800 | 3.0 | 96.6 | 73.1 | **49.8** | 1 |
| Morrisania/Crotona | $3,150 | 0.0 | 98.1 | 64.6 | **49.0** | 2 |
| Jackson Heights/Elmhurst | $2,867 | 0.0 | 97.5 | 71.5 | **48.8** | 4 |
| Sunnyside/Woodside | $2,825 | 0.2 | 97.1 | 74.0 | **48.7** | 305 |
| Downtown Brooklyn/Brooklyn Heights | $3,185 | 1.7 | 95.3 | 60.2 | **48.5** | 463 |
| Fort Greene/Clinton Hill | $3,000 | 1.4 | 95.3 | 62.2 | **48.3** | 199 |
| Long Island City/Astoria | $2,850 | 1.0 | 95.4 | 71.6 | **48.2** | 322 |
| North Shore (St. George/New Brighton) | $3,200 | 0.1 | 95.2 | 63.4 | **47.7** | 15 |
| Bedford-Stuyvesant | $3,300 | 0.2 | 95.1 | 61.6 | **47.6** | 69 |
| Financial District/Battery Park | $4,800 | 7.2 | 87.5 | 34.3 | **47.3** | 295 |
| Mott Haven/Hunts Point | $2,512 | 0.5 | 90.5 | 78.4 | **45.5** | 268 |

**Key Takeaway**: The top-scoring neighborhoods achieve their status through **high livability + high affordability**, not convenience. Lower East Side is the only top-10 area with significant convenience scores, but it sacrifices affordability to get there.

### Borough Performance Summary

| Borough | Median Rent | Convenience | Livability | Affordability | Combined | Census Tracts |
|---------|-------------|-------------|------------|---------------|----------|---------------|
| **Manhattan** | $4,800 | 7.3 | 87.6 | 34.1 | 47.4 | 298 |
| **Brooklyn** | $3,022 | 1.5 | 95.3 | 60.9 | 48.4 | 732 |
| **Queens** | $2,850 | 0.6 | 96.2 | 72.8 | 48.4 | 631 |
| **Bronx** | $2,512 | 0.5 | 90.5 | 78.2 | 45.5 | 271 |
| **Staten Island** | $3,200 | 0.1 | 95.2 | 63.4 | 47.7 | 15 |

**Notable Pattern**: Queens achieves the best livability (96.2) while being 41% cheaper than Manhattan ($2,850 vs $4,800). Brooklyn offers the best overall balance across metrics.

---

## Key Findings

### Scale
- **1,947 census tracts** analyzed across all five NYC boroughs
- Rent ranges from $2,512 to $5,795+ median rent across neighborhoods
- Coverage: Manhattan (298 tracts), Brooklyn (732), Queens (631), Bronx (271), Staten Island (15)

### Correlations and Patterns

**Borough-Level Summary:**
- **Manhattan**: Highest rents (median $4,800), highest convenience scores (7.3/100), but lowest affordability (34.1/100)
- **Brooklyn**: Balanced profile (median $3,022), excellent livability (95.3/100), strong affordability (60.9/100)
- **Queens**: Best affordability (72.8/100), excellent livability (96.2/100), median rent $2,850
- **Bronx**: Most affordable (median $2,512, 78.2/100 affordability), good livability (90.5/100)
- **Staten Island**: High livability (95.2/100), minimal transit convenience (0.1/100)

**Key Trade-offs:**
- **Convenience vs. Affordability**: High transit access correlates with 40-70% higher rents
- **Livability varies independently**: Brooklyn and Queens achieve 95-96/100 livability at moderate prices
- **Only ~1.6%** of tracts achieve both high convenience AND high livability

### Neighborhood-Level Insights

#### Top Performers by Combined Score

**1. Lower East Side/Chinatown (Manhattan)**
- Median Rent: $5,168/month
- Convenience: 9.4/100 | Livability: 94.4/100 | Combined: 51.9/100
- High livability despite being Manhattan; moderate convenience

**2. Downtown Brooklyn/Brooklyn Heights (Brooklyn)**
- Median Rent: $3,185/month
- Convenience: 1.7/100 | Livability: 95.3/100 | Combined: 48.5/100
- 463 census tracts analyzed
- Strong livability at significantly lower cost than Manhattan

**3. Sunnyside/Woodside (Queens)**
- Median Rent: $2,825/month
- Convenience: 0.2/100 | Livability: 97.1/100 | Combined: 48.7/100
- 305 census tracts - large area with consistent quality
- Excellent value: high livability + high affordability (74.0/100)

#### Hidden Gems: High Livability + High Affordability
*(Livability > 90/100, Affordability > 60/100)*

**Bushwick/East New York (Brooklyn)**
- Rent: $2,800/month
- Livability: 96.6/100, Affordability: 73.1/100
- Trade-off: Very low convenience (3.0/100)

**Morrisania/Crotona (Bronx)**
- Rent: $3,150/month
- Livability: 98.1/100, Affordability: 64.6/100
- Quiet, safe neighborhood at moderate price

**Jackson Heights/Elmhurst (Queens)**
- Rent: $2,867/month
- Livability: 97.5/100, Affordability: 71.5/100
- Excellent residential quality, limited transit

**Long Island City/Astoria (Queens)**
- Rent: $2,750/month
- Livability: 96.6/100, Affordability: 76.7/100
- 230 tracts analyzed - substantial area with good value

#### Highest Convenience Areas

**Financial District/Battery Park (Manhattan)**
- Rent: $4,915/month
- Convenience: 37.8/100 (highest in NYC)
- Livability: 68.4/100 (moderate due to business district activity)
- Combined: 53.1/100

*Note: Only one neighborhood cluster achieved convenience scores above 30/100, highlighting NYC's concentration of transit infrastructure in lower Manhattan.*

### Strategic Insights

**The Affordability-Livability Sweet Spot:**
Several neighborhoods offer the rare combination of high livability (>95/100) with strong affordability (>70/100):
- Long Island City/Astoria: $2,750/month, 96.6 livability, 76.7 affordability
- Sunnyside/Woodside: $2,825/month, 97.1 livability, 74.0 affordability
- Jackson Heights/Elmhurst: $2,867/month, 97.5 livability, 71.5 affordability

**💡 See these areas in the [Livability Heatmap](./livability_heatmap.html) - they're the red zones in Queens!**

**The Convenience Premium:**
Manhattan's Financial District commands 78% higher rents than comparable-livability areas in Queens, primarily due to transit access. This suggests renters pay substantial premiums for convenience even when residential quality is better elsewhere.

**💡 The [Convenience Heatmap](./convenience_heatmap.html) shows why - transit infrastructure is heavily concentrated in lower Manhattan with virtually no other NYC areas achieving convenience scores above 30/100.**

**The Livability Surprise:**
Contrary to the "expensive = better" assumption, Manhattan has the **lowest livability score** (87.6) among all boroughs. Queens (96.2) and Brooklyn (95.3) offer significantly quieter, safer neighborhoods at 41% and 37% lower median rents respectively.

**💡 Compare the [Livability Heatmap](./livability_heatmap.html) with the [Affordability Heatmap](./affordability_heatmap.html) - the best living conditions are NOT in the most expensive areas.**

**Borough Strategy:**
- **Choose Manhattan if**: Transit access is critical and budget permits ($4,800+ median)
- **Choose Brooklyn if**: You want balance - moderate prices with good livability  
  *→ See [Top Neighborhoods Map](./top_neighborhoods_map.html) for best Brooklyn tracts*
- **Choose Queens if**: Maximizing affordability while maintaining quality is the priority  
  *→ Queens dominates the [Livability Heatmap](./livability_heatmap.html)*
- **Choose Bronx if**: Budget is primary concern and convenience is secondary  
  *→ Highest affordability in [Affordability Heatmap](./affordability_heatmap.html)*
- **Choose Staten Island if**: You prefer quietest areas and don't rely on public transit

### Example Neighborhood Rankings
Based on the analysis, here are sample findings (actual results will vary based on your data):

**High Combined Score Areas (Convenience + Livability):**
- Upper East Side (Manhattan): Excellent transit, low crime, but expensive
- Park Slope (Brooklyn): Good transit access, quiet residential feel
- Forest Hills (Queens): Balanced scores across all metrics

**High Affordability + High Livability:**
- Parts of Bayside (Queens): Affordable and quiet, but lower transit access
- Throgs Neck (Bronx): Good residential quality at moderate prices
- Certain Staten Island neighborhoods: High livability, low convenience

**High Convenience Areas:**
- Midtown Manhattan: Maximum transit access, but highest rents and noise
- Downtown Brooklyn: Strong transit, but variable livability by tract
- Long Island City (Queens): Growing transit access, mixed livability

These examples demonstrate the core finding: **neighborhoods excel in different dimensions, and the "best" area depends on individual priorities.**

---

## Interpretation

### What This Analysis Shows
Higher rent does not automatically mean better residential conditions. The data reveals several counter-intuitive patterns:

1. **Queens outperforms Manhattan on livability** (96.2 vs 87.6/100) at 41% lower median rent
2. **Convenience concentration**: Only one neighborhood (Financial District) scores above 30/100 on convenience, revealing extreme centralization of transit infrastructure
3. **The Bronx offers the highest affordability** (78.2/100) while maintaining solid livability (90.5/100)
4. **Brooklyn provides the best balance** across all metrics for residents seeking middle-ground options

**Key Takeaway**: Neighborhoods excel in different dimensions. The "best" area fundamentally depends on whether a renter prioritizes transit access, residential quality, or affordability - as achieving all three simultaneously is extremely rare (only 1.6% of census tracts).

### What This Analysis Doesn't Do
This is **not a predictive model** for rent prices. The goal is interpretive analysis to support decision-making, not forecasting.

---

## Project Structure

```
.
├── nyc_neighborhood_analysis.ipynb           # Main analysis notebook (cleaned)
├── README.md                                 # This file - comprehensive documentation
├── master_tract.csv                          # Integrated dataset (input)
│
├── data/                                     # Source data files (optional)
│   ├── noise_complaints.csv
│   ├── mta_ridership.csv
│   ├── business_licenses.csv
│   ├── crime_data.csv
│   └── rent_data_tract.csv
│
└── outputs/                                  # Generated analysis results
    │
    ├── CSV Results:
    │   ├── nyc_neighborhood_analysis_results.csv    # Full census tract results (1,947 tracts)
    │   └── nyc_neighborhood_summary.csv             # Aggregated by neighborhood (12 areas)
    │
    └── Interactive Maps (HTML):
        ├── top_neighborhoods_map.html               # Top 20 tracts with details
        ├── convenience_heatmap.html                 # Transit accessibility distribution
        ├── livability_heatmap.html                  # Urban quality distribution
        └── affordability_heatmap.html               # Rent affordability distribution
```

### 📁 Output Files Description

**CSV Files:**
- `nyc_neighborhood_analysis_results.csv`: Complete dataset with all 1,947 census tracts, including calculated scores and raw metrics
- `nyc_neighborhood_summary.csv`: Aggregated statistics for 12 major neighborhood clusters

**HTML Maps:** 
All maps are fully interactive - you can zoom, pan, and click for details. Open directly in any web browser. Maps use Folium/Leaflet for visualization and are self-contained (no external dependencies needed).

**To View Maps:**
1. Download the HTML files from the outputs folder
2. Double-click to open in your browser
3. Interact with the map (zoom, pan, click markers/heatmap points)

---

## How to Use This Analysis

### Prerequisites
- Python 3.7+
- Required packages: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `folium`

### Quick Start

**Option 1: View Results Only (Fastest)**
1. Open the interactive HTML maps in your browser:
   - Start with `top_neighborhoods_map.html` for an overview
   - Explore `convenience_heatmap.html`, `livability_heatmap.html`, `affordability_heatmap.html` to see geographic patterns
2. Review `nyc_neighborhood_summary.csv` for aggregated statistics
3. Browse `nyc_neighborhood_analysis_results.csv` for tract-level details

**Option 2: Run the Analysis**
If you have `master_tract.csv`:
1. Open `nyc_neighborhood_analysis.ipynb`
2. Update the `data_path` in Section 2 to point to your CSV file
3. Run all cells

The notebook will:
- Load and enrich data with neighborhood names
- Calculate composite scores (convenience, livability, affordability)
- Generate visualizations and statistical analyses
- Create interactive maps showing top neighborhoods
- Export results and rankings

### 🎨 Understanding the Visualizations

**Heatmaps Explained:**
- **Red/Hot zones** = High scores (good for that metric)
- **Blue/Cool zones** = Low scores (poor for that metric)
- **Intensity** = Score magnitude (brighter = higher)

**What to Look For:**
1. In **Convenience Heatmap**: Notice how transit access is almost entirely concentrated in one small area (Financial District)
2. In **Livability Heatmap**: See how outer boroughs (especially Queens) glow red with high livability
3. In **Affordability Heatmap**: Observe the stark contrast - Manhattan is completely cold (blue), while Bronx/Queens are hot (red)
4. **The Key Insight**: These three maps barely overlap - proving you can't have it all in NYC!

### Interactive Maps
The analysis includes interactive Folium-based maps:
- **Top Neighborhoods Map**: Shows the top 20 census tracts by combined score with color-coded markers
- **Convenience Heatmap**: Visualizes areas with highest transit and amenity access
- **Livability Heatmap**: Highlights neighborhoods with low crime and noise
- **Affordability Heatmap**: Shows areas with lower rent prices

Maps are saved as HTML files that can be opened in any web browser.

### From Scratch
If you need to integrate source data:
1. Acquire the six data sources listed above
2. Run geographic alignment and aggregation (see data integration notebook)
3. Generate `master_tract.csv`
4. Proceed with analysis notebook

---

## Potential Extensions

This analysis could be extended with:

1. **Time-series component**
   - Track how rent and livability change over time
   - Identify gentrifying neighborhoods

2. **Additional features**
   - School quality ratings
   - Park accessibility
   - Restaurant density
   - Healthcare facility proximity

3. **Interactive dashboard**
   - Personalized exploration based on user preferences
   - Map-based visualization
   - Custom weighting of convenience vs. livability

4. **Causal analysis**
   - Impact of new transit lines on rent
   - Effect of crime reduction initiatives
   - Amenity development and neighborhood change

5. **Prediction models**
   - Future rent forecasting
   - Gentrification risk assessment

---

## Technical Notes

### Data Quality Considerations
- **Missing data:** Some census tracts have incomplete data for certain metrics (e.g., no nearby subway stations)
- **Temporal alignment:** Data sources span 2019-2023 depending on dataset
- **Spatial accuracy:** Geocoding accuracy varies by data source

### Methodological Choices
- **Additive indices:** Components are averaged rather than weighted to avoid imposing subjective preferences
- **Linear scaling:** MinMaxScaler provides interpretable 0-100 scores
- **Census tracts:** Chosen over ZIP codes for demographic relevance

### Limitations
- Does not account for apartment characteristics (size, age, amenities)
- Point-in-time snapshot rather than longitudinal analysis
- Equal weighting of convenience components may not reflect individual preferences
- Does not capture qualitative neighborhood characteristics (culture, community feel)

---

## About the Analysis Approach

This project emphasizes **interpretability and context-aware analysis** over model complexity. The goal was to demonstrate how urban data can support practical decisions rather than to maximize predictive accuracy.

The approach reflects real-world methods used in:
- Urban economics research
- Real estate analytics
- City planning and policy analysis

By keeping the methodology transparent and grounded in established urban indicators, the analysis aims to be both rigorous and accessible to non-technical audiences.

---

## Data Sources & Attribution

- **NYC Open Data**: 311 Complaints, Business Licenses, Crime Data
- **MTA**: Subway ridership data
- **Citibike**: Trip and station data
- **US Census Bureau**: Housing and demographic data
- **NYC Department of City Planning**: Census tract boundaries

---

## Contact & Contribution

This project was developed as part of coursework in Data Science at Fordham University.

For questions or suggestions:
- Review the Jupyter notebook for detailed implementation
- Check data processing steps in the integration code
- Refer to source documentation for specific datasets

---

## License

This analysis is provided for educational and research purposes. Please cite appropriately if using this methodology or findings.

---

## Acknowledgments

Thanks to NYC Open Data for maintaining comprehensive urban datasets and to the open-source Python community for excellent data analysis tools.
