<p align="center">
   <img src="https://raw.githubusercontent.com/NeighTools/UnityDoorstop/master/docs/logo_sm.png"/>
</p>


*Run managed code before Unity does!*

*This is a small fork of UnityDoorstop that enables loading a dynamic libary with native code as well. Nothing else changed.*
*Be aware that the native code is loaded when mono is initialized, just like the managed code.*
*It loads the library defined by the targetNative config variable*

# Unity Doorstop

*NOTE:* Version 3.0.0.0 brought some breaking changes to how command line arguments are passed. Refer to the release changelogs for more info.

Doorstop is a tool to execute managed assemblies inside Unity as early as possible!

This repository is indented mainly for developers!  
Developers should package Doorstop into their applications for the end-users.

## Features

* **Runs first**: Doorstop runs its own code before Unity has an ability to do so.
* **Configurable**: A very basic configuration file allows to specify your own assembly to execute!
* **Public domain!** You are fully free to embed Doorstop into your application!

## Guides for users and developers on [the wiki](https://github.com/NeighTools/UnityDoorstop/wiki)

## Building

To build, you will need:

* PowerShell 2.0 or newer
* Visual Studio 2019 (2015 might work as well with some modifications)
* Visual C++ Toolset v142
* .NET Framework 3.5 or newer (only for the example, not used by the proxy)

Clone, open in Visual Studio, select the platform (x86/x64) and build.

#### Custom proxy functions

Doorstop's proxy is flexible and allows to be load as different DLLs.
You can modify which functions are proxied by adding/removing entries in dll.def

The current set up allows to use the proxy for the following DLLs:

* `winhttp.dll` (All exports, works better with Wine)
* `version.dll` (All exports, better support for Unity 3)

Simply rename the Doorstop DLL to use it as a different proxy (as long as the exports are included).
