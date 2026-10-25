 Los Angeles Cuisine Explorer

SSCI 591 — Web GIS | Project 3 | Haokang Jin

1. What This Map Shows

Taste of Asia is an interactive Web GIS application showing the distribution of Chinese, Japanese, and Korean restaurants in central Los Angeles. Restaurants are displayed as colored markers based on cuisine: red for Chinese, blue for Japanese, and green for Korean. Users can click individual locations to view restaurant information and use the Layer List to show or hide different categories.

2. Starting Sample

This project was developed using Esri's official [Intro to Graphics sample](https://developers.arcgis.com/javascript/latest/sample-code/get-started-graphics/) from the ArcGIS Maps SDK for JavaScript. The original example demonstrates how to create map graphics with geometries, symbols, attributes, and popups.

3. What I Changed

I changed the map's center and zoom level to focus on Los Angeles and replaced the original hybrid basemap with streets-vector. I also replaced the sample point, line, and polygon graphics with restaurant markers created from online data.

I assigned different colors to the three cuisines, configured restaurant information popups, and added a page header, an About section, a color legend, and a loading-status display.

4. Data Source

Restaurant data comes from [OpenStreetMap](https://www.openstreetmap.org/) through the [Overpass API](https://wiki.openstreetmap.org/wiki/Overpass_API).

I used JavaScript `fetch()` to send a POST request containing an Overpass QL query for restaurants with Chinese, Japanese, or Korean cuisine tags within a geographic bounding box.

The API returns JSON data. My JavaScript processes the restaurant coordinates and attributes, converts the records into ArcGIS Graphic objects, and adds them to three separate GraphicsLayers.

I selected this approach to practice REST API requests, JSON processing, and dynamic Web GIS visualization.

5. Component I Added

I added the ArcGIS Layer List component to the upper-right corner of the map. It allows users to turn individual cuisine layers on or off. I also created a separate HTML color legend to explain the marker colors.

6. Problems and What I'd Improve Next

The first API endpoint I tried produced a browser request error. Switching to another public Overpass endpoint resolved the problem during local testing.

Some OpenStreetMap restaurant records also have missing names or addresses. The application displays a fallback value when this information is unavailable.

In the future, I would improve the restaurant filtering interface, add a search function, and provide better handling for temporary API failures. Since OpenStreetMap is community-maintained, its restaurant information may be incomplete or outdated.

7. Credits

- **Map SDK:** Esri ArcGIS Maps SDK for JavaScript 5.1
- **Starting code:** Esri Intro to Graphics sample
- **Restaurant data:** © OpenStreetMap contributors
- **Data API:** OpenStreetMap Overpass API
- **AI assistance:** ChatGPT was used to help understand JavaScript syntax, adapt the sample code. The application was tested in a local browser during development.
