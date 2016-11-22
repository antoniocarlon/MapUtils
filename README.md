# Map Utils

Utilities for Google Maps Android API v2

### Current version

v0.2.0

## ExpandedMBTilesTileProvider

Tile provider to read MBTiles format into Google Maps API Android v2 expanding the available zoom levels to the lowest one (lower zoom levels will be interpolated from higher levels).

### Usage:

```
TileProvider tileProvider = new ExpandedMBTilesTileProvider(new File("/sdcard/mydatabase.mbtiles"), 256, 256);
TileOverlay tileOverlay = mMap.addTileOverlay(
     new TileOverlayOptions()
        .tileProvider(tileProvider));
```

## CameraUpdateAnimator

Animaes the camera position chaining a series of CameraUpdates with a given delay between them and allowing camera to move or animate.

### Usage:

```
// Create a new CameraUpdateAnimator for a given mMap
// with an OnCameraIdleListener to set when the animation ends
CameraUpdateAnimator animator = new CameraUpdateAnimator(mMap, mOnCameraIdleListener);

// Add animations
animator.add(CameraUpdateFactory.newLatLngZoom(new LatLng(40.421, -3.71), 17), true, 1000); // Animate the camera with a 1000 milliseconds delay
animator.add(CameraUpdateFactory.newLatLngZoom(new LatLng(40.421, -3.71), 18), false, 500); // Move the camera (no animation) with a 500 milliseconds delay
animator.add(CameraUpdateFactory.newLatLngZoom(new LatLng(40.422, -3.72), 18), true, 500);
animator.add(CameraUpdateFactory.newLatLngZoom(new LatLng(40.422, -3.72), 19), false, 1000);
animator.add(CameraUpdateFactory.newLatLngZoom(new LatLng(40.423, -3.73), 19), true, 500);
animator.add(CameraUpdateFactory.newLatLngZoom(new LatLng(40.421, -3.71), 17), true, 1000);

// Execute the animation and set the final OnCameraIdleListener
animator.execute();
```

## License
Copyright 2016 ANTONIO CARLON

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.