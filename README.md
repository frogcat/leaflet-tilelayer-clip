# leaflet-tilelayer-clip

leaflet 0.7.3 plugin to clip tilelayer

## Demo

<http://frogcat.github.io/leaflet-tilelayer-clip/demo.html>

## Usage

```
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>leaflet-tilelayer-clip</title>
<link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.css" />
<script src="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.js"></script>
<script src="leaflet-tilelayer-clip.js"></script>
<style>
body {
	width: 100%;
	height: 100%;
	overflow: hidden;
}

#map {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}
</style>
</head>
<body>
	<div id="map"></div>
	<script>
		var map = L.map("map", {
			zoom : 16,
			minZoom : 10,
			center : [ 36.09894, 139.96672 ]
		});

		L.tileLayer('http://cyberjapandata.gsi.go.jp/xyz/ort/{z}/{x}/{y}.jpg', {
			attribution : "国土地理院",
			maxNativeZoom : 18,
			maxZoom : 20
		}).addTo(map);

		L.tileLayer.clip('http://cyberjapandata.gsi.go.jp/xyz/20150911dol2/{z}/{x}/{y}.png', {
			attribution : "国土地理院",
			maxNativeZoom : 18,
			maxZoom : 20,
			clip : L.bounds([ 0, 0 ], [ window.innerWidth * 0.5, window.innerHeight ])
		}).addTo(map);
	</script>
</body>
</html>
```

## Options

Option  | Type | Default | Description
--------|------|---------|-------------
clip    | L.Bounds| ([0,0],[640,480]) | Clip bounds




## Methods

Mthod  | Returns | Description
----- | -------------|------
setClip(bounds)  | this | Set clip bounds.
update(bounds)  | this | update view.






