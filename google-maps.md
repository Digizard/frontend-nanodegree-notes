Google Maps
===========

Google Maps is a required part of Project 5 for the FEWD Nanodegree. It came up a little bit as part of Project 2.


Sample Map
----------

A basic example map to get started with, [here](https://developers.google.com/maps/documentation/javascript/examples/map-simple).


Markers
--------------

### Adding Markers

Taken from [here](https://developers.google.com/maps/documentation/javascript/examples/marker-simple).

```JavaScript
var marker = new google.maps.Marker({
  position: myLatlng,
  map: map,
  title: 'Hello World!'
});
```

### Hiding Markers

Simply change their map property to null. Change it back to the map when you want them back.

Source [here](https://developers.google.com/maps/documentation/javascript/examples/marker-remove).


Places API
----------

This API has detailed information about different places around the world. In Project 2, the Places API was used to fetch the location of cities mentioned in the resume so that markers could be put there.

### Script Tag
```HTML
<script src="http://maps.googleapis.com/maps/api/js?libraries=places"></script>
```

### Example of Fetching Locations

Taken from Project 2.

```JavaScript
/*
pinPoster(locations) takes in the array of locations created by locationFinder()
and fires off Google place searches for each location
*/
function pinPoster(locations) {

  // creates a Google place search service object. PlacesService does the work of
  // actually searching for location data.
  var service = new google.maps.places.PlacesService(map);

  // Iterates through the array of locations, creates a search object for each location
  for (var place in locations) {

    // the search request object
    var request = {
      query: locations[place]
    };

    // Actually searches the Google Maps API for location data and runs the callback
    // function with the search results after each search.
    service.textSearch(request, callback);
  }
}
```
