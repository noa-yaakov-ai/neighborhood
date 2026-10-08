# Noa's Neighborhood / שכונת נועה

Small static Three.js neighborhood for @noa_yaakov_ai. Pastel daytime low-poly world, cat statue with turquoise glasses, one house per follower. No follower names or personal information are collected.

## Preview

Serve this directory with any static HTTP server. For example:

```sh
node serve.cjs
```

Open localhost port 4173. A filesystem file URL will not load the JSON/module files correctly.

## Real follower count

`neighborhood.json` is the source of truth. `followers: null` means unverified, not zero. After checking the Instagram profile, set `followers` to the non-negative integer shown and set `updatedAt` to the verification timestamp. No scraper or scheduled update is enabled. A future GitHub Action may edit this same file when a permitted follower-data source exists.

`?demo=25` or `?demo=50` shows clearly labelled demo houses without changing the data. Do not use a demo URL as the real follower count.

Roads unlock at 10, 25, 50, 100. The first cat statue is always there; the coffee statue starts at 50 and can be changed in the JSON. Existing house slots do not move when the count grows.

## GitHub Pages

After publishing these source files to Noa's own repository, choose Settings > Pages > Deploy from branch > main / root. The site uses relative URLs and supports a repository subpath. No paid service or build step is required. Do not upload node_modules, browser checks or temporary working files.

## Controls and limits

Drag to orbit, pinch/wheel to zoom, right drag/two-finger gesture to pan. Phone-sized viewports default to light mode with shadows off and pixel ratio 1. Desktop uses cached soft shadows. The renderer draws only when the camera or viewport changes and stops while hidden. Minimal chrome contains the neighborhood name and count only, with a small data-status footer. The data accepts up to 100,000 houses; very large scenes can still exceed a low-end phone's resources. Facade number plates are drawn from one small atlas for the first 256 houses; later houses keep their stable internal slot numbers without visible plaques. Street signs use lightweight textures rather than Mars City’s extruded letters. The static WebGL fallback reports that 3D is unavailable and keeps the neighborhood facts accessible. No analytics, trackers, local account creation or cookies are included. Optional Google Fonts requests are made for Hebrew typography; Arial is the fallback.

Checked with headless Chromium at 390×844 and 1280×900, and growth thresholds through 1,000 houses. Physical Android/iPhone, Safari, screen readers and low-end FPS remain unverified. This is a simpler procedural scene than the concept illustrations.

## License

Original code and scene geometry are provided for this project. Three.js and OrbitControls are included under the MIT license in vendor/THREE-LICENSE.txt. No model/image assets from the concept illustrations are shipped.
