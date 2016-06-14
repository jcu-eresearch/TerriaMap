Tropical Data Hub at JCU: Map Theatre
=====================================
![JCU Maps logo](blue-shadow.png "JCU Maps logo")

This is a theatre for data exploration that presents TDH data in a
spatial context.  Or as a normal human would say, shows stuff on a
map.

It's based on Terria Map, which powers the awesome
[NationalMap](nationalmap.gov.au).

To get started:

```
git clone https://github.com/jcu-eresearch/jcu-maps.git
cd jcu-maps
npm install      # Install dependencies, including gulp
npm start        # Start the server in the background
npm run watch    # Build the site, and watch for changes
```

### Positioning the map's viewing camera

You can start the map with the camera at whatever you like.  Here's
an example JSON config, with commentary.

`homeCamera` and `initialCamera` are specified identically.
`initialCamera` is what you get when the map starts.  The `homeCamera`
is what you get when you click the "reload"-looking button between the
zoom in and zoom out buttons.

**Option 1: specify bounds**

The `homeCamera` example here specifies `north`, `east `,`south`, and
`west`.  The camera will be positioned looking at the Earth's centre,
zoomed back enough to include the specified bounds.

**Option 2: specify position in super-fixed coordinates**

This overrides Option 1.

You can specify `position`, `direction`, and `up` (as well as
`north`, `east `,`south`, and `west`). `position` and `direction`
need `x`, `y` and `z` keys specifying locations in [ECEF] metre
coordinates, which is basically un-usable for normal humans. To see
an example of this, fly the camera around a bit on national map,
click the "share" button (and choose to not use the URL shortner),
and URL-decode the URL you get.

**Option 3: locate the camera like a spaceship**

This overrides Options 1 and 2.

You can specify:

 - `positionHeadingPitchRoll.cameraLongitude`
 - `positionHeadingPitchRoll.cameraLatitude`
 - `positionHeadingPitchRoll.cameraHeight`, probably in metres
 - `positionHeadingPitchRoll.heading`, in degrees clockwise from north
 - `positionHeadingPitchRoll.pitch`, in degrees down from horizontal
 - `positionHeadingPitchRoll.roll`, probably in degrees?


...and get what you expect.

**Option 4: look at a feature**

This is *the good one*, and overrides Options 1, 2, and 3.

 - `lookAt.targetLongitude`
 - `lookAt.targetLatitude`
 - `lookAt.targetHeight`, in metres from sealevel (positive is up)
 - `lookAt.heading`, in degrees clockwise from north
 - `lookAt.pitch`, in degrees down from horizontal (so negative values mean you're looking at the sky)
 - `lookAt.range`, in metres from the thing you're looking at

The example below uses plain old bounds for the `homeCamera`, and
a `lookAt` key for the `initialCamera`.

```
{
	"homeCamera": {
		"north": -8,
		"east": 158,
		"south": -45,
		"west": 109
	},
	"initialCamera": {
		// the initial camera is what you get when the map initialises.
		// it can include north/east/south/west like the homeCamera.
		"lookAt": {
			"targetLongitude": 145,
			"targetLatitude": -17,
			"targetHeight": 100,
			"heading": 45,
			"pitch": 45,
			"range": 100000
		}
	},
	"baseMapName": "Bing Maps Aerial",
	"viewerMode": "3d"
}
```