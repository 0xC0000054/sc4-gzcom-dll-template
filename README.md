# sc4-gzcom-dll-template

A GZCOM DLL Plugin template for SimCity 4.   

This template simplifies the process of creating a DLL plugin for SimCity 4.

To demonstrate using the game's messaging system, the plugin subscribes to the in-game messages
that are sent when loading or establishing a city and prints the city name to the debugger console.

Further information on the design of the GZCOM framework can be found on the [gzcom-dll project wiki](https://github.com/nsgomez/gzcom-dll/wiki).

# Using the Code

## Prerequisites

* Visual Studio 2022

## Building the plugin

1. Open the solution in the `src` folder
2. Set the `kExampleDirectorID` constant in `ExampleDllDirector.cpp` to a randomly generated 32-bit number.
    
    The GZCOM framework requires the director ids, message ids, etc. to be unique. To enforce this the template
    creates a compiler error by setting the `kExampleDirectorID` to `<>`.

    You will need to replace the `<>` value with a randomly generated number. The random number is typically
    written as an 8 character [hexadecimal](https://en.wikipedia.org/wiki/Hexadecimal) number in the form `0xAABBCCDD`,
    the `0x` prefix is used in C++ to indicate that the number is using the hexadecimal format.

3. Update the [post build events](https://learn.microsoft.com/en-us/cpp/build/specifying-build-events?view=msvc-170) to copy the build output to you SimCity 4 application plugins folder.
4. Build the solution

## Debugging the plugin

Visual Studio can be configured to launch SimCity 4 on the Debugging page of the project properties.
I configured the debugger to launch the game in full screen with the following command line:    
`-intro:off -CPUcount:1 -w -CustomResolution:enabled -r1920x1080x32`

You may need to adjust the window resolution for your primary screen.

# License

This project is licensed under the terms of the MIT License.    
See [LICENSE.txt](LICENSE.txt) for more information.

## 3rd party code

[gzcom-dll](https://github.com/nsgomez/gzcom-dll/tree/master) Located in the vendor folder, MIT License.    
[EABase](https://github.com/electronicarts/EABase) Located in the vendor folder, BSD 3-Clause License.    
[EASTL](https://github.com/electronicarts/EASTL) Located in the vendor folder, BSD 3-Clause License.    
