
# animalquiz "game" imgui graphical interface

this examle modifies https://github.com/ocornut/imgui/tree/master/examples/example_sdl_opengl3
to play the "animalquiz" game, visualizing the tree.

create a new directory with this project at the same level of that example and it should work.

note: this example works using a busy wait cycle, so it will load the cpu.


- On Windows with Visual Studio's CLI

```
set SDL2_DIR=path_to_your_sdl2_folder
cl /Zi /MD /I.. /I..\.. /I%SDL2_DIR%\include /I..\libs\gl3w main.cpp animal_quiz.cpp myutils.cpp ..\imgui_impl_sdl.cpp ..\imgui_impl_opengl3.cpp ..\..\imgui*.cpp ..\libs\gl3w\GL\gl3w.c /FeDebug/example_sdl_opengl3.exe /FoDebug/ /link /libpath:%SDL2_DIR%\lib\x86 SDL2.lib SDL2main.lib opengl32.lib /subsystem:console
#          ^^ include paths                                 ^^ source files                                                                                  ^^ output exe                    ^^ output dir   ^^ libraries
# or for 64-bit:
cl /Zi /MD /I.. /I..\.. /I%SDL2_DIR%\include /I..\libs\gl3w main.cpp animal_quiz.cpp myutils.cpp..\imgui_impl_sdl.cpp ..\imgui_impl_opengl3.cpp ..\..\imgui*.cpp ..\libs\gl3w\GL\gl3w.c /FeDebug/example_sdl_opengl3.exe /FoDebug/ /link /libpath:%SDL2_DIR%\lib\x64 SDL2.lib SDL2main.lib opengl32.lib /subsystem:console
```

- On Linux and similar Unixes

```
c++ `sdl2-config --cflags` -I .. -I ../.. -I ../libs/gl3w main.cpp animal_quiz.cpp myutils.cpp ../imgui_impl_sdl.cpp ../imgui_impl_opengl3.cpp ../../imgui*.cpp ../libs/gl3w/GL/gl3w.c `sdl2-config --libs` -lGL -ldl
```

- On Mac OS X

```
brew install sdl2
c++ `sdl2-config --cflags` -I .. -I ../.. -I ../libs/gl3w main.cpp animal_quiz.cpp myutils.cpp ../imgui_impl_sdl.cpp ../imgui_impl_opengl3.cpp ../../imgui*.cpp ../libs/gl3w/GL/gl3w.c `sdl2-config --libs` -framework OpenGl -framework CoreFoundation
```


#running just tests: 
compile (using commands like c++ or g++) the following files: animal_quiz.cpp animal_quiz_test_class.cpp myutils.cpp
run the executable file produced (a.out in unix-like systems).

#run the animal quiz by command line
comment the line with #NO_MAIN in the animal_quiz.cpp file,\
Compile the animal_quiz.cpp and myutils.cpp files.




