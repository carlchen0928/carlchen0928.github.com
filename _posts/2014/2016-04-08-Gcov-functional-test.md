### create an empty folder in project home
```sh
mkdir build && cd build
```

### create static library used in main
```sh
gcc -c ../calc_mean.c
ar rcs libmean.a calc_mean.o
```

### link the static library and take gcov option
```sh
gcc -fprofile-arcs -ftest-coverage -static ../main.c ../calc_sum.c -L. -lmean -o main
```

### build another main use the same header file
```sh
gcc -fprofile-arcs -ftest-coverage _main.c -o _main
```

### run two exe file
```sh
./main
./_main
```

### gather code coverage data
```sh
gcov main.c
gcov _main.c
```
