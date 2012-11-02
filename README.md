# Xcode project to build minetest

**Discontinued. The alternative is: <https://github.com/toabi/minetest/tree/cmake-osx>**

**This doesn't work anymore with recent minetest versions.**

This Xcode project can be used to build [minetest-c55](https://github.com/celeron55/minetest).

Fore more information have a look the [official homepage](http://c55.me/minetest/).

## Requirements

This was tested on OS X 10.7 with Xcode 4. It includes all needed 3rd party libraries.
It builds a 32bit 10.6 compatible application bundle.

Somebody also reported that he was able to build it with Xcode 3.2.5 under 10.6 using
the debugging build settings from the commandline.

## How to build minetest

### Getting the code

	$ git clone https://github.com/celeron55/minetest.git
	$ cd minetest
	$ git clone https://github.com/toabi/minetest-mac.git
	$ cd minetest-mac

There are now two easy ways to get your app. The final product always ends up in ./build/(Release|Debug)/.

### Commandline

### Build for debugging

You probably don't care about correctly set version information and stuff while coding.
So just run `xcodebuild -target "App Bundle"` in the minetest-mac folder.

### Building for release

`xcodebuild -target "Release Bundle"`

The release version is not very different to the above 'App Bundle'. The important
difference is, that it contains the proper version strings everywhere. It's set up
to work on my machine so you may have to modify some build settings in Xcode:

It uses `git describe --tags` to get the version. So the minetest code should reside in
a git repository. If your `git` doesn't live in `/usr/local/bin/` you have to modify the
'Version from git' target in the build settings.

### Xcode GUI

* Doubleclick the .xcodeproj
* Hit "Build & Run"
* If everything is OK, the application should launch.

### Targets and Schemes

When developing, use the **Debug** scheme. It just builds the application bundle and doesn't do other magic.
Therefore only changed files are recompiled.

When releasing an application bundle then use the **Release** scheme. It will automatically update the *VERSION_STRING*
with the output of `git describe` and also write the version into the `Info.plist` so the Finder can display it.

## So you don't like to build?

You can also download a build from [there](https://github.com/toabi/minetest-mac/downloads). But they may be old.

## Credits

I'm distributing the binary Irrlicht framework release from this [thread](http://irrlicht.sourceforge.net/phpBB2/viewtopic.php?t=42601).
