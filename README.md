# GLFW NuGet #

![GLFW Icon](https://bytebucket.org/sgrottel_nuget/glfw/raw/7bab6beb2556f884bb37f730571e09341993197d/glfw.png)

This repository contains all files and information to create a NuGet package out of the officiel pre-compiled binaries of GLFW.

I do not compile the library myself! I only package the available pre-compiled binaries.

For problems with the NuGet package contact SGrottel: 

* https://github.com/sgrottel/nuget-glfw
* https://www.sgrottel.de
* https://go.grottel.net/nuget/glfw

For problems with the library itself contact the authors:

* http://www.glfw.org/

## GLFW ##

[GLFW](http://www.glfw.org/) is an Open Source, multi-platform library for creating windows with OpenGL contexts and receiving input and events.
It is easy to integrate into existing applications and does not lay claim to the main loop.

GLFW is written in C and has native support for Windows, OS X and many Unix-like systems using the X Window System, such as Linux and FreeBSD.

GLFW is licensed under the [zlib/libpng license](http://www.glfw.org/license.html).

Project Website: http://www.glfw.org/

## How do I get set up? ##

* Download the pre-compiled GLFW for Windows (`WIN32` and `WIN64`): http://www.glfw.org/download.html
* Copy the following items into the corresponding folders:
    * `docs` > `.`
    * `include` > `.`
    * `lib-vc*` > `Win32` or `x64`
    * `README.md` > `docs`
    * `LICENSE.md` > `docs`
* You might need to adjust `glfw.nuspec`, `glfw.targets`, and `glfw-propertiesui.xml`
    * `glfw.nuspec` stores the meta data and which files to include in the package.
	* `glfw.targets` contains all MSBuild settings to consume the package. This includes automatic adjustment of platforms, configurations and toolsets.
	* `glfw-propertiesui.xml` provides some Visual Studio UI to allow the consume of the package to force some settings.

## Building the NuGet Package ##

Install nuget command line tool.

Run: `make_nuget.ps1 . 5`

The first argument is this project directory.

The second argument is the build number, which is to be increased each time a new package for the same version is published.
