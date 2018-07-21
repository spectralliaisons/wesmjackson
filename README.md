# multimap
https://spectralliaisons.github.io/multimap/

Overlay gps tracks on Google Maps with pins for photos and audio taken.


##
How to add a track with images and optional audio:

###
Create directory for the place in `gps/Places/`. You can copy an existing directory and clear out img/, imgErr/, imgSm/, aud/ and kml/.

####

`gps/Places/{{PLACE NAME}}/`

#####
`/info_template.json`

Basic map style for this place, e.g.:

`{
  "zoom":15,
  "center":"head of the russian river",
  "mapType":"hybrid",
  "locations":[
    {
      "label":"head of the russian river",
      "loc":{"lat": 39.3816387, "lng": -123.2364948},
      "img":null,
      "aud":null
    }
  ]
}`

#####
`/info.json`
  
This is the data file for placing images, audio, KML on Google Maps. It is generated by `gps/python/create gps info.ipynb`
If your directories are syntactically kosher, this python script will generate info.json files for every directory in gps/Places/

####
`gps/Places/{{PLACE NAME}}/img/`

Image files you want to place on map. If the python script finds GPS coordinates in the image, it will create a map marker on the map that, when clicked, will show the image, image name, and an audio file if one is found with the same name as this image.


`gps/Places/{{PLACE NAME}}/aud/`

  Audio files. File name sans extension must match an image with valid GPS coordinates or else will not appear.
