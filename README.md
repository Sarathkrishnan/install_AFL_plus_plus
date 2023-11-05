# install_AFL_plus_plus

Download the `install_AFL.sh`

Open terminal in folder containg `install_AFL.sh`

Run the tool using command `bash install_AFL.sh`
```
$ bash install_AFL.sh 
Hit:1 http://packages.microsoft.com/repos/code stable InRelease
Hit:2 https://dl.google.com/linux/chrome/deb stable InRelease                                      
Hit:3 https://packages.microsoft.com/repos/edge stable InRelease                                   
Hit:4 http://apt.pop-os.org/proprietary jammy InRelease                      
Hit:5 http://apt.pop-os.org/release jammy InRelease
Hit:6 http://apt.pop-os.org/ubuntu jammy InRelease
Hit:7 http://apt.pop-os.org/ubuntu jammy-security InRelease
Hit:8 http://apt.pop-os.org/ubuntu jammy-updates InRelease
Hit:9 http://apt.pop-os.org/ubuntu jammy-backports InRelease
```


Verify installation by running command `afl-cc`. Make sure all modes are available
```$ afl-cc
afl-cc++4.07c by Michal Zalewski, Laszlo Szekeres, Marc Heuse

afl-cc/afl-c++ [options]

This is a helper application for afl-fuzz. It serves as a drop-in replacement
for gcc and clang, letting you recompile third-party code with the required
runtime instrumentation. A common use pattern would be one of the following:

  CC=afl-cc CXX=afl-c++ ./configure --disable-shared
  cmake -DCMAKE_C_COMPILERC=afl-cc -DCMAKE_CXX_COMPILER=afl-c++ .
  CC=afl-cc CXX=afl-c++ meson

                                       |------------- FEATURES -------------|
MODES:                                  NCC PERSIST DICT   LAF CMPLOG SELECT
  [LTO] LLVM LTO:          AVAILABLE
      PCGUARD              DEFAULT      yes yes     yes    yes yes    yes
      CLASSIC                           yes yes     yes    yes yes    yes
  [LLVM] LLVM:             AVAILABLE [SELECTED]
      PCGUARD              DEFAULT      yes yes     module yes yes    yes
      CLASSIC                           no  yes     module yes yes    yes
        - NORMAL
        - CALLER
        - CTX
        - NGRAM-{2-16}
  [GCC_PLUGIN] gcc plugin: AVAILABLE
      CLASSIC              DEFAULT      no  yes     no     no  no     yes
  [GCC/CLANG] simple gcc/clang: AVAILABLE
      CLASSIC              DEFAULT      no  no      no     no  no     no

Modes:
  To select the compiler mode use a symlink version (e.g. afl-clang-fast), set
  the environment variable AFL_CC_COMPILER to a mode (e.g. LLVM) or use the
  command line parameter --afl-MODE (e.g. --afl-llvm). If none is selected,
  afl-cc will select the best available (LLVM -> GCC_PLUGIN -> GCC).
  The best is LTO but it often needs RANLIB and AR settings outside of afl-cc.```