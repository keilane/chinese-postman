## Chinese postman problem

This is a Python program to solve the [Chinese postman problem](http://en.wikipedia.org/wiki/Route_inspection_problem).

## Usage with Quantum GIS

Python 2.7 is required for the plugin to run. Therefore this only works on QGIS 1.8+ on Windows (which bundles Python 2.7).
The plugin may work on QGIS 1.7+ on Linux, as long as you have Python 2.7 installed.

1. Download the plugin from [here](http://plugins.qgis.org/plugins/chinesepostman/version/0.1/).
2. Extract the zip file to C:\Users\Yourname\.qgis\python\plugins on Windows, or ~/.qgis/python/plugins on Unix.
3. Under Plugins -> Manage Plugins, enable the plugin.
4. Select the layer for which you want to solve the CPP.
5. Select the features that you want to use. The "Select Features by Polygon" tool works great if you only want to use a small part of a large network.
6. Run Plugins -> Chinese Postman -> Chinese Postman.

It should create a new layer with the results.

## Command-line Usage

Requirements:

* Python2.7
* [networkx](http://networkx.lanl.gov/)


Input data file must be in CSV format, with each row containing the following columns:

* Start node ID
* End node ID
* Segment length in meters
* Segment name or ID
* Start longitude, for example 18.4167
* Start latitude, for example -33.9167
* End longitude
* End latitude

Example:

    Start Node,End Node,Segment Length,Segment ID,Start Longitude,Start Latitude,End Longitude,End Latitude
    1,13,57,Segment 1,18.4167,-33.9167,18.6532,-33.8561
    13,22,80,Segment 2,18.6532,-33.8561,18.7650,-33.7930

Then run (assuming the file is saved as input.csv):

    python postman.py --csv path.csv --gpx path.gpx input.csv


The segment ID and GPS coordinates in the input file are not used for any calculations, but are used for the CSV and GPX
output.

## License

All code is licensed under [The MIT License (MIT)](http://opensource.org/licenses/MIT).


