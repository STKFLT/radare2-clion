# radare2-clion
Information and scripts to make developing radare2 with CLion easier

### This project does NOT let you build r2 with CLion or CMake

It includes just enough to get CLion's fancy features working (Go to Definition, refactor/rename, etc.)

## Usage
To use, just drop CMakeLists.txt into Radare2's root directory and open radare2 as a project in CLion
If you want to debug with CLion, just build radare2 with `./sys/build.sh CFLAGS='-g'` and then add binr/radare2/radare2 as an debug configuration.


It is possible that the list of directories containing header files in CMakeLists.txt is out of date. If so, just run
```bash
for file in $(find . -name '*.h'); do dirname $file; done | sort | uniq
```
then paste the output into include_directories().

Lastly, I apologize to anyone who actually knows how CMake works that had to look at this.
