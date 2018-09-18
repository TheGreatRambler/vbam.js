# VBAM.js

Game Boy Advance Emulator in Webassembly. Based upon the popular [Visual Boy Advance Emulator](http://vba-m.com).

## Building

Assuming you have LibPng, Zlib, SDL2, OpenAl, Make, CMake and Git installed ([list of deps](https://github.com/visualboyadvance-m/visualboyadvance-m#building)):
```bash
git clone https://github.com/TheGreatRambler/vbam.js.git
cd visualboyadvance-m
./installdeps
```
This will give you a list of instructions to follow. Upon arriving at `cmake`, run this command instead:
```bash
cmake .. -DENABLE_SDL=ON -DENABLE_WX=OFF -DENABLE_NLS=OFF -DENABLE_LINK=OFF -DENABLE_DIRECT3D=OFF -DENABLE_XAUDIO2=OFF
```
Then, run this command:
```bash
emmake make -j [number of cores]
emcc -02 -lopenal -lSDL -s "USE_ZLIB=1;USE_SDL=2;USE_LIBPNG=1" project.bc project.js
```
