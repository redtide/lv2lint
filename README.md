# lv2lint

## Check whether a given LV2 plugin is up to the specification

### Build status

[![build status](https://gitlab.com/OpenMusicKontrollers/lv2lint/badges/master/build.svg)](https://gitlab.com/OpenMusicKontrollers/lv2lint/commits/master)

### Dependencies

#### Mandatory

* [LV2](http://lv2plug.in/) (LV2 Plugin Standard)
* [lilv](https://drobilla.net/software/lilv/) (LV2 plugin host library)

#### Optional

* [libcurl](https://curl.haxx.se/libcurl/) (The multiprotocol file transfer library)
* [libelf](https://sourceware.org/elfutils/) (ELF object file access library)

lv2lint can optionally test your plugin URIs for existence. If you want that,
you need to enable it at compile time (-Donline-tests=true) and link to libcurl.
You will also need to enable it at run-time (-o).

lv2lint can optionally test your plugin symbol visibility and link dependencies.
If you want that, you need to enable it at compile time (-Delf-tests=true) and
link to libelf.

### Build / install

	git clone https://git.open-music-kontrollers.ch/lv2/lv2lint
	cd lv2lint
	meson -Donline-tests=true -Delf-tests=true build
	cd build
	ninja
	sudo ninja install

### Usage

An __acceptable plugin__ *SHOULD* pass without triggering any fails, this is also the
default configuration:

	lv2lint http://lv2plug.in/plugins/eg-scope#Stereo

A __good plugin__ *SHOULD* pass without triggering any warnings:

	lv2lint -Ewarn http://lv2plug.in/plugins/eg-scope#Stereo

A __perfect plugin__ *SHOULD* pass without triggering any warnings or notes:

	lv2lint -Ewarn -Enote http://lv2plug.in/plugins/eg-scope#Stereo

If you get any warnings or notes, you can enable debugging output to help you

	lv2lint -d -Ewarn -Enote http://lv2plug.in/plugins/eg-scope#Stereo
fix the problems:

### License

Copyright (c) 2016-2019 Hanspeter Portner (dev@open-music-kontrollers.ch)

This is free software: you can redistribute it and/or modify
it under the terms of the Artistic License 2.0 as published by
The Perl Foundation.

This source is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
Artistic License 2.0 for more details.

You should have received a copy of the Artistic License 2.0
along the source as a COPYING file. If not, obtain it from
<http://www.perlfoundation.org/artistic_license_2_0>.
