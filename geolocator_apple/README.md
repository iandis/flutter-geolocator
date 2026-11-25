# geolocator_apple

[![pub package](https://img.shields.io/pub/v/geolocator.svg)](https://pub.dartlang.org/packages/geolocator) ![Build status](https://github.com/Baseflow/flutter-geolocator/workflows/geolocator_apple/badge.svg?branch=master) [![style: effective dart](https://img.shields.io/badge/style-effective_dart-40c4ff.svg)](https://github.com/tenhobi/effective_dart)

The official iOS and macOS implementation of the [geolocator](https://pub.dev/packages/geolocator) plugin by [Baseflow](https://baseflow.com).

## About this fork

This branch is geolocator_apple 2.3.14 with one change for Swift Package Manager: `Package.swift` defines
`BYPASS_PERMISSION_LOCATION_ALWAYS=1`, so the request for Always location is compiled out. Our app only asks for When
In Use location, and with that request in the binary App Store Connect asks for
`NSLocationAlwaysAndWhenInUseUsageDescription`. Under CocoaPods the app's `Podfile` set the same flag.

Why a fork: newer versions (2.3.15 and later) can read this flag only from an environment variable at build time.
That would mean setting it on Codemagic and on every developer's machine, adding a build check that catches a build
without it, and telling the team about both. The fork sets it once, in the code, for every build, with nothing to set
up.

## Usage

Since version 7.5.0 of the [geolocator](https://pub.dev/packages/geolocator) plugin this is the endorsed iOS and macOS implementation. This means it will automatically be added to your dependencies when you depend on `geolocator: ^7.5.0` in your applications pubspec.yaml.

More detailed instructions on using the API can be found in the [README.md](../geolocator/README.md) of the [geolocator](https://pub.dev/packages/geolocator) package.

## Issues

Please file any issues, bugs or feature requests as an issue on our [GitHub](https://github.com/Baseflow/flutter-geolocator/issues) page. Commercial support is available, you can contact us at <hello@baseflow.com>.

## Want to contribute

If you would like to contribute to the plugin (e.g. by improving the documentation, solving a bug or adding a cool new feature), please carefully review our [contribution guide](../CONTRIBUTING.md) and send us your [pull request](https://github.com/Baseflow/flutter-geolocator/pulls).

## Author

This Geolocator plugin for Flutter is developed by [Baseflow](https://baseflow.com).