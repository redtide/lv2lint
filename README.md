# lv2lint

## Check whether a given LV2 plugin is up to the specification

### Build status

[![build status](https://gitlab.com/OpenMusicKontrollers/lv2lint/badges/master/build.svg)](https://gitlab.com/OpenMusicKontrollers/lv2lint/commits/master)

### Dependencies

* [LV2](http://lv2plug.in) (LV2 Plugin Standard)
* [lilv](http://drobilla.net/software/lilv/) (LV2 plugin host library)

### Build / install

	git clone https://gitlab.com/OpenMusicKontrollers/lv2lint.git
	cd lv2lint
	mkdir build
	cd build
	cmake -DCMAKE_BUILD_TYPE="Release" ..
	make
	sudo make install

### Usage

	lv2lint http://lv2plug.in/plugins/eg-scope#Stereo

### License

Copyright (c) 2016-2017 Hanspeter Portner (dev@open-music-kontrollers.ch)

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
