# Map Utils

Utilities for Google Maps Android API v2

### Current version

v0.1.0

## ExpandedMBTilesTileProvider

Tile provider to read MBTiles format into Google Maps API Android v2 expanding the available zoom levels to the lowest one (lower zoom levels will be interpolated from higher levels).

### Usage:

```
TileProvider tileProvider = new ExpandedMBTilesTileProvider(new File("/sdcard/mydatabase.mbtiles"), 256, 256);
TileOverlay tileOverlay = mMap.addTileOverlay(
     new TileOverlayOptions()
        .tileProvider(tileProvider));
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