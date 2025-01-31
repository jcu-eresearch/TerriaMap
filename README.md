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

Open your browser to http://localhost:3001


## Updating release deploys on server

From http://terria.io/Documentation/guide/deploying/deploying-terriamap/

```shell
# Stop the server
npm stop
# If that doesn't halt correctly kill the process
killall node
# Pull the update changes from github
git clone github master
# Install the new node_modules
npm install
# Prepare the release Build
gulp release

# Wait a while till it finishes

# Start up the node server
npm start

# Check it out
curl https://maps.jcu.io
```

## Camera positioning

If you are chasing how to position the camera look at `wwwroot/init/camera.json`.
TODO: Update this with new .ejs files to correctly preview datasets
