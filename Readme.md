# Kastri

<img src="kastri-logo.png" alt="logo" height="250">

From [Delphi Worlds](http://www.delphiworlds.com)

[![Twitter](https://img.shields.io/badge/-Twitter-1DA1F2?style=plastic&logo=Twitter)](https://twitter.com/DelphiWorlds)  [![Facebook](https://img.shields.io/badge/-Facebook-green?style=plastic&logo=Facebook)](https://www.facebook.com/DelphiWorlds)  [![Instagram](https://img.shields.io/badge/-Instagram-833AB4?style=plastic&logo=Instagram)](https://www.instagram.com/delphiworlds)

Compatible with [Embarcadero](https://wwww.embarcadero.com) [Delphi](https://www.embarcadero.com/products/delphi). Please note: Only the **last two point releases of major releases** (e.g. at present that includes Delphi 10.4.2 and Delphi 11) are "officially" supported. 

Development of Kastri can be helped along with [Github Sponsorship](https://github.com/sponsors/DelphiWorlds), so please consider sponsoring today!

Alternatively, you might like to make a donation via PayPal: 

[![paypal](https://www.paypalobjects.com/en_AU/i/btn/btn_donate_LG.gif)](https://www.paypal.com/donate/?hosted_button_id=CGHWQ28MKBGAA)

Please star this repo by clicking the Star box in the top right corner if you find it useful!

If you're looking to [learn Delphi, please visit this link](https://learndelphi.org)

## Kastri

* Is a cross-platform library which builds upon the existing RTL, FMX and VCL libraries in Delphi
* Supports a number of newer APIs that you won't find in FMX/RTL, and "backfills" for missing APIs
* Is structured in a way so as to avoid creating unnecessary dependencies
* Follows strict coding standards to ensure consistency and readability
* Is kept as simple as practicable
* Is named after the [place in Greece](https://en.wikipedia.org/wiki/Kastri,_Phocis) where [Delphi](https://en.wikipedia.org/wiki/Delphi) once stood

## Delphi 11 changes

With the introduction of Delphi 11, there have been some changes related to Android. You may notice new jar files in the `Lib` folder where the name is the same as an existing jar, with a suffix of `2.0.0` (or greater) e.g. `dw-kastri-base-2.0.0.jar`. Jars with a `2.0.0` suffix will work **only with Delphi 11** (and possibly later). If a jar does not have a corresponding jar with a `2.0.0` (or greater) suffix, it should also work with Delphi 11. Please also see the Demos section below.

## Intro video

[This is a link to an intro video for Kastri](https://delphiworlds.s3-us-west-2.amazonaws.com/kastri-sponsor-video.mp4)

## How To Use Kastri

For the most part, with Kastri there are no components to install. Simply clone the repo ([Fork](https://git-fork.com/) is a highly recommended Git client), or download/unzip and ensure that your Project (recommended) or IDE paths point to the folders of the units that you use.

The [Native Controls suite (Kastri FMX)](./Controls) is a set of components that can be [installed into Delphi](./Packages) and used at design-time

## Support

### Issues page

If you encounter an issue, or want to request an enhancement, please [visit the issues page](https://github.com/DelphiWorlds/Kastri/issues) to report it.

### Slack Channel

The Delphi Worlds Slack workspace has a channel (#kastri) devoted to discussing Kastri. There you will find Dave Nottage (when he is available) and other developers who are passionate about Kastri to discuss how to use Kastri, what is in it etc.

[Sponsors](https://github.com/sponsors/DelphiWorlds) of Kastri have access to the private #sponsors channel where they receive priority support.

If you would like to join the Delphi Worlds Slack workspace, [please visit this self-invite link](https://slack.delphiworlds.com)

## What Is In Kastri?

### Demos

You'll find demo applications in the [Demos](./Demos) folder, including those associated with articles posted on the [Delphi Worlds blog](http://www.delphiworlds.com/blog)

**Delphi 11 users please note**: Some of the demos that have Android support have been updated in line with changes in Delphi 11, and now have separate project (`.dproj`) and group project (`.groupproj`) (where applicable) files, which have been suffixed with `D11`. For demos that do not have a suffix of `D11` in the name, you may need to open Project Manager and for each Android target you wish to use, right-click the `Libraries` node and click `Revery System Files to Default` before building the project. 

### API imports

In the API folder you will find imports for a number of iOS, macOS, Android and Linux APIs that are either not included with Delphi, serve to complete missing APIs, or are imports for Java code contained in Kastri. 
Most of these are used in the Kastri Features and/or demos however some are included due to interest from developers.

### Core units

Units in the Core folder contain code of a wealth of cross-platform related implementations. Units that have platform specific code are suffixed with one of:

* .Android.pas
* .iOS.pas
* .Linux.pas
* .Mac.pas - can be for both iOS and macOS
* .Posix.pas - for Posix-based platforms (iOS, macOS, Android, Linux)
* .Win.pas

Implementations include:

* DW.OSLog - logging code that serves to replace Log.d, which relies on FMX, and cannot be used in an Android service
* DW.OSDevice - code that returns information that is mostly device-specific
* DW.OSTimer - leaner, less complex implementation of a timer. Also does not rely on FMX, so can be used in an Android service

### Features

The Features folder contains more feature-rich cross-platform implementations of APIs. These are structured in such a way so as to shield your cross-platform code from the platform-specific implementation.
There are demos for each of the features in the Demos folder
Features include:

#### Barcode

Based on [Google ML Vision APIs](https://developers.google.com/ml-kit/vision), it allows you to scan an image and detect barcodes within it

#### Biometric

Android and iOS implementations of biometric functions, namely: Fingerprint recognition on Android, and Fingerprint and FaceID on iOS

#### Camera

Android and iOS implementations of native camera support

#### Connectivity

Android, macOS, iOS and Windows implementations of code for checking network connectivity of a device

#### Files Selector

Uses native APIs to allow users to select one or more files on the device, for Android and iOS

#### Firebase

Android and iOS implementations of Firebase Cloud Messaging using their native libraries

#### Geofencing support on Android

Works a little like the regions support does for iOS with [TLocationSensor](http://docwiki.embarcadero.com/Libraries/Sydney/en/System.Sensors.Components.TLocationSensor). Set up geographical regions (each region is a location with a specified radius), and events fire when the user passes in/out of those regions

#### Location

Android and iOS framework made specifically for location updates when the application is in any state (e.g. even when it is not running)

#### NFC

Near-Field Communication implementations for Android and iOS

#### Notifications

Framework that is alternative to TNotificationCenter (that ships with Delphi) for Notifications on Android and iOS

#### Proximity

Support for the proximity sensor on Android and iOS, including switching the screen on/off e.g. when the user puts the device to their ear

#### Share Items

A more feature-rich alternative for the Share Sheet implementation provided with Delphi, for Android and iOS

#### Speech Recognition

Android and iOS implementations for speech-to-text services. On Android, the actual speech API is used, rather than via Intents

#### Universal Links (iOS only)

Allows users to follow links to content inside your app from your website.

### Planned Features

In addition to the features listed above, several other features are [planned for Kastri](https://github.com/DelphiWorlds/Kastri/milestones), namely:

#### Assets Manager

For accessing photos/videos stored on the device via the albums on Android and iOS

#### Google SignIn

A (hopefully) simplified variation on [Grijjy's excellent Google SignIn](https://github.com/grijjy/DelphiGoogleSignIn) implementation, **with added support for iOS**

#### Simple backend framework for managing push tokens

A simple REST backend for managing push tokens and sending messages that can be customised to your needs. Complements the existing Firebase Cloud Messaging support.

The above features take time and resources to develop. Your help via [sponsorship](https://github.com/sponsors/DelphiWorlds) can help make them a reality!

## License

Kastri is licensed under MIT, and the license file is included in this folder.


![](https://tokei.rs/b1/github/DelphiWorlds/Kastri)

