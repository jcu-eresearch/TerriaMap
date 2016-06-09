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

----

Original Terria Map docs follow...

----

Terria Map
==========

![Terria screenshot](terria-screenshot.png "Terria screenshot")


### Technical

* Built in Ecmascript 2015, compiled with Babel to ES5 using Gulp.
* Supports IE9 and later.
* [TerriaJS Server component](https://github.com/TerriajS/TerriaJS-Server) runs in NodeJS and provides proxying for web services that don't support CORS or require authentication.
* Dependencies are [managed in NPM](https://www.npmjs.com/~terria) and assembled using WebPack.

### Getting Started ###
Pre-requisites: Git, NodeJS, NPM, GDAL (optional).

```
sudo npm install -g gulp                           # Install gulp, the build tool
git clone https://github.com/TerriaJS/TerriaMap    # Get the code
cd TerriaMap
npm install                                        # Install dependencies
npm start                                          # Start the server in the background
gulp watch                                         # Build the site, and watch for changes.
```

Now visit the site in your browser at `http://localhost:3001`.

See the [wiki](https://github.com/NICTA/nationalmap/wiki) for more detailed information about how to build and run it.
