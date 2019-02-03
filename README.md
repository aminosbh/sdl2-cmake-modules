# SDL2 CMake modules

This repository contains [CMake][] modules for finding and using the SDL2
library as well as other related libraries:

- [SDL2][]
- [SDL2_image][]
- [SDL2_ttf][]
- [SDL2_net][]
- [SDL2_mixer][]
- [SDL2_gfx][]

These modules are based on the SDL (1.2) modules, with the same names,
distributed with the CMake project. The SDL2_gfx module is also based
on the SDL_image module.

## Details and Improvements

The improvements made to these modules are as follows:

**FindSDL2.cmake**

- Adapt `FindSDL.cmake` to `SDL2` (`FindSDL2.cmake`).
- Add cache variables for more flexibility:<br>
    `SDL2_PATH`, `SDL2_NO_DEFAULT_PATH`
- Mark `Threads` as a required dependency for non-OSX systems.
- Modernize the `FindSDL2.cmake` module by creating specific targets:
  - `SDL2::Core` : Library project should link to `SDL2::Core`
  - `SDL2::Main` : Application project should link to `SDL2::Main`

*For more details, please see the embedded documentation in `FindSDL2.cmake` file.*

**FindSDL2_&lt;COMPONENT&gt;.cmake**

- Adapt `FindSDL_<COMPONENT>.cmake` to `SDL2_<COMPONENT>` (`FindSDL2_<COMPONENT>.cmake`).
- Add cache variables for more flexibility:<br>
    `SDL2_<COMPONENT>_PATH`, `SDL2_<COMPONENT>_NO_DEFAULT_PATH`
- Add `SDL2` as a required dependency.
- Modernize the `FindSDL2_<COMPONENT>.cmake` modules by creating specific targets:<br>
    `SDL2::Image`, `SDL2::TTF`, `SDL2::Net`, `SDL2::Mixer` and `SDL2::GFX`.

*For more details, please see the embedded documentation in
`FindSDL2_<COMPONENT>.cmake` file.*



[CMake]: https://cmake.org
[SDL2]: https://www.libsdl.org
[SDL2_image]: https://www.libsdl.org/projects/SDL_image
[SDL2_ttf]: https://www.libsdl.org/projects/SDL_ttf
[SDL2_net]: https://www.libsdl.org/projects/SDL_net
[SDL2_mixer]: https://www.libsdl.org/projects/SDL_mixer
[SDL2_gfx]: http://www.ferzkopp.net/wordpress/2016/01/02/sdl_gfx-sdl2_gfx
