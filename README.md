<!DOCTYPE html>
<html>
<head>
    <title>Google Maps Example</title>
    <script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyANnndFqCJ2ozY7v5Co4A_sEQ0HcTwW9U8&callback=initMap"
            async defer></script>
   <script>
        var map;
        var marker;

        function initMap() {
            var location = {lat: -34.397, lng: 150.644}; // Default location
            map = new google.maps.Map(document.getElementById('map'), {
                zoom: 8,
                center: location
            });
            marker = new google.maps.Marker({
                position: location,
                map: map
            });
        }

        function updateMap() {
            var lat = parseFloat(document.getElementById('latitude').value);
            var lng = parseFloat(document.getElementById('longitude').value);

            if (!isNaN(lat) && !isNaN(lng)) {
                var newLocation = {lat: lat, lng: lng};
                map.setCenter(newLocation);
                marker.setPosition(newLocation);
            } else {
                alert("Please enter valid latitude and longitude!");
            }
        }
    </script>
</head>
<body onload="initMap()">
    
    <h3>Enter Latitude and Longitude:</h3>
    <input type="text" id="latitude" placeholder="Enter latitude">
    <input type="text" id="longitude" placeholder="Enter longitude">
    <button onclick="updateMap()">Update Map</button>

    <div id="map" style="height: 500px; width: 100%; margin-top: 20px;"></div>

</body>
</html>

