# GeoRSS xml format to GeoJSON conversion, 
## with metadata rescue

by Nikhil VJ, http://nikhilvj.co.in  
28 October 2018

- Made specifically to handle georss (.xml) downloads from Bhuvan
- Parses the metadata trapped in HTML description
- Tested to work with points, polygons, lines, and can handle a file that mixes these
- Does "right hand rule" fix for polygons (see https://mapster.me/right-hand-rule-geojson-fixer/)
- Saves an extra CSV with the metadata neatly laid out
- Saves numerical metadata as number instead of string, this helps when you want to render features based on the numbers (example: choropleth maps). Can recognise numbers like "-3.43e-4"
- Gets rid of an html whitespace (\xa0) encountered in metadata in one file

Runs on Python 3.6. modules you'll need:  
`feedparser geojson geojson_utils pandas bs4 lxml`

Note: feedparser module gets a [runtime error](https://github.com/kurtmckee/feedparser/pull/131) on python 3.7 as of Oct-2018. Please create a virtual environment ([windows guide](https://github.com/WRI-Cities/static-GTFS-manager/wiki/Running-on-Windows-OS-with-Python-3)) ([ubuntu guide](https://github.com/WRI-Cities/static-GTFS-manager/wiki/Running-on-Ubuntu-OS)) and run in python 3.6 .
