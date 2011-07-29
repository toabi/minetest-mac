# Xcode project to build minetest

This Xcode project can be used to build [mintest-delta](https://github.com/erlehmann/minetest-delta),
a fork of [minetest-c55](https://bitbucket.org/celeron55/minetest).

Use the branch `delta` if you want to build [minetest-delta](https://github.com/erlehmann/minetest-delta).

## Requirements

This was tested on OS X 10.6 with Xcode 3. It includes all needed 3rd party libraries.
It builds a 32bit 10.5 compatible application bundle.

## How to build minetest

### Getting the code

	$ mkdir ~/code && cd ~/code
	$ git clone https://github.com/erlehmann/minetest-delta.git
	$ cd minetest-delta
	$ git submodule add --branch delta https://github.com/toabi/minetest-mac.git
	$ cd minetest-mac

There are now two easy ways to get your app. The final product always ends up in ./build/(Release|Debug)/.

### Commandline

* Run `xcodebuild` in the minetest-mac folder

### Xcode GUI

* Doubleclick the .xcodeproj
* Hit "Build & Run"
* If everything is OK, the application should launch.

## So you don't like to build?

You can also download a build from [there](https://github.com/toabi/minetest-mac/downloads). But they may be old.

## Credits

I'm distributing the binary Irrlicht framework release from this [thread](http://irrlicht.sourceforge.net/phpBB2/viewtopic.php?t=42601).
