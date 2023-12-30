## SCXvid-standalone
Standalone, cross-platform port of [the AviSynth SCXvid plugin][1].

### Usage
```
scxvid output.log < input.y4m
```

Example with ffmpeg
```
ffmpeg -i video.mkv -f yuv4mpegpipe -vf scale=640:360 -pix_fmt yuv420p - | scxvid keyframes.txt'
```
Only 4:2:0 input is supported.
### Downloads
Executable for macOS can be found in the releases section. For Windows see [here](https://github.com/soyokaze/SCXvid-standalone/releases).
### Building
#### Requirements
* Xvid 1.3.x

#### On Windows
Use the Visual Studio solution in the repository. The "xvidcore" directory from Xvid sources must be on the same level with SCXvid directory. Also make sure that you compile libxvidcore with DLL runtime, not static.
#### On Unix-like systems
Assuming you have libxvidcore properly installed somewhere in compiler's default paths, run:
```
cc -o scxvid scxvid.c libxvidcore.a
```


[1]: https://code.google.com/p/yatta-ivtc/source/browse/#svn%2Fscxvid%2Ftrunk
