maps_toolkit2 update
======

This is a fork of https://github.com/kb0/maps_toolkit. **The goal is to make it compatible with flutter_map**


[![Pub Package](https://img.shields.io/pub/v/maps_toolkit2.svg)](https://pub.dartlang.org/packages/maps_toolkit2)
[![Dart Publish](https://github.com/faqcodes/maps_toolkit2/actions/workflows/publish.yml/badge.svg)](https://github.com/faqcodes/maps_toolkit2/actions/workflows/publish.yml)
[![Coverage Status](https://coveralls.io/repos/github/faqcodes/maps_toolkit2/badge.svg?branch=main)](https://coveralls.io/github/faqcodes/maps_toolkit2?branch=main)
[![GitHub Issues](https://img.shields.io/github/issues/faqcodes/maps_toolkit2.svg?branch=main)](https://github.com/faqcodes/maps_toolkit2/issues)
[![GitHub Forks](https://img.shields.io/github/forks/faqcodes/maps_toolkit2.svg?branch=main)](https://github.com/faqcodes/maps_toolkit2/network)
[![GitHub Stars](https://img.shields.io/github/stars/faqcodes/maps_toolkit2.svg?branch=main)](https://github.com/faqcodes/maps_toolkit2/stargazers)
[![GitHub License](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://github.com/faqcodes/maps_toolkit2/main/LICENSE)


A library for area, distance, heading measurements (spherical_util.dart if port from `android-maps-utils`).

## Getting Started

In your dart/flutter project add the dependency:

```dart
 dependencies:
   ...
   maps_toolkit2: ^1.0.1
```

A simple usage example:

```dart
import 'package:maps_toolkit2/maps_toolkit2.dart';

main() {
  val distanceBetweenPoints = SphericalUtil.computeDistanceBetween(
    LatLng(51.5073509, -0.1277583),
    LatLng(48.856614, 2.3522219)
  );

  final p1 = LatLng(45.153474463955796, 39.33852195739747);
  final p2 = LatLng(45.153474463955796, 39.33972358703614);
  final p3 = LatLng(45.15252112936569, 39.33972358703614);
  final p4 = LatLng(45.1525022138355, 39.3385460972786);

  val areaInSquareMeters = SphericalUtil.computeArea([p1, p2, p3, p4, p1]);
}
```

Usage with Google Maps package (specify a prefix for an import):

```dart
import 'package:maps_toolkit2/maps_toolkit2.dart' as mp;
import 'package:google_maps/google_maps.dart';
import 'package:test/test.dart';

void main() {
  final pointFromToolkit = LatLng(90, 0);
  final pointFromGoogleMap = LatLng(90, 0);

  mp.SphericalUtil.computeAngleBetween(pointFromToolkit, pointFromToolkit);
}
``` 

## List of functions

* `SphericalUtil.computeArea` - calculate the area of a closed path on Earth.
* `SphericalUtil.computeDistanceBetween` - calculate the distance between two points, in meters.
* `SphericalUtil.computeHeading` - calculate the heading from one point to another point.
* `SphericalUtil.computeLength` - calculate the length of the given path, in meters, on Earth.
* `SphericalUtil.computeOffset` - calculate the point resulting from moving a distance from an origin in the specified heading (expressed in degrees clockwise from north).
* `SphericalUtil.computeOffsetOrigin` - calculate the location of origin when provided with a point destination, meters travelled and original heading.
* `SphericalUtil.computeSignedArea` - calculate the signed area of a closed path on Earth.
* `SphericalUtil.interpolate` - calculate the point which lies the given fraction of the way between the origin and the destination.

* `PolygonUtil.containsLocation` - computes whether the given point lies inside the specified polygon.
* `PolygonUtil.isLocationOnEdge` - computes whether the given point lies on or near the edge of a polygon, within a specified tolerance in meters.
* `PolygonUtil.isLocationOnPath` - computes whether the given point lies on or near a polyline, within a specified tolerance in meters.
* `PolygonUtil.locationIndexOnPath` - computes whether (and where) a given point lies on or near a polyline, within a specified tolerance.
* `PolygonUtil.locationIndexOnEdgeOrPath` - computes whether (and where) a given point lies on or near a polyline,  within a specified tolerance.
* `PolygonUtil.simplify` - simplifies the given poly (polyline or polygon) using the Douglas-Peucker decimation algorithm.
* `PolygonUtil.isClosedPolygon` - returns true if the provided list of points is a closed polygon.
* `PolygonUtil.distanceToLine` - computes the distance on the sphere between the point p and the line segment start to end.
* `PolygonUtil.decode` - decodes an encoded path string into a sequence of LatLngs.
* `PolygonUtil.encode` - encodes a sequence of LatLngs into an encoded path string.

## Features and bugs

Please file feature requests and bugs at the [issue tracker][tracker].

[tracker]: https://github.com/faqcodes/maps_toolkit2/issues
