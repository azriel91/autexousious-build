[![Build Status](https://travis-ci.org/azriel91/autexousious-build.svg?branch=master)](https://travis-ci.org/azriel91/autexousious-build) [![Build status](https://ci.appveyor.com/api/projects/status/b5sj0evgt4clksu2/branch/master?svg=true)](https://ci.appveyor.com/project/azriel91/autexousious-build/branch/master)

## Autexousious

This repository exists to allow the full integration build for (most of<sup>1</sup>) the blocks that make up Autexousious.

Each block has its own individual repository, as the intent is for them to be versioned / released individually.

<sup>1</sup> The [CppMicroServices](https://github.com/saschazelzer/CppMicroServices) block is not yet included as part of this repository, waiting on [PR#26](https://github.com/saschazelzer/CppMicroServices/pull/26) to be merged.

## Development

This is implemented as a [CppMicroServices](https://github.com/saschazelzer/CppMicroServices) module, and is built using [biicode](https://www.biicode.com/).

When bumping the version of a block, please ensure to build this repository as the integration of the new version of one block with the existing versions of the other blocks may not be successful and require changes to the other blocks for them to work together.

### Requirements

* [biicode](https://www.biicode.com/downloads)
* [CMake](http://www.cmake.org/install/)
* [g++ 4.8](https://gcc.gnu.org/)

### Building

After cloning, in the repository directory run the following to initialize this as a biicode project:

	bii init

Depending on whether you wish to build the blocks as static or dynamic CppMicroServices modules, run configure with the `BUILD_SHARED_LIBS` flag set to `OFF` or `ON`. If you leave the flag out, it defaults to `OFF`.

	bii configure -DBUILD_SHARED_LIBS=ON

Finally to build Autexousious and test executables, run:

	bii build

To run the tests, run one of the following commands:

	bii build --target test 		# linux
	bii build --target RUN_TESTS 	# windows

## License

Copyright (c) Azriel Hoh. Licensed under the [Apache License v2.0](http://www.apache.org/licenses/LICENSE-2.0).
