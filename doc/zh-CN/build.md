# KernelPatch编译文档

## 编译kpimg

### 下载编译环境配置

需要裸机交叉编译器

[下载编译工具链](https://developer.arm.com/downloads/-/arm-gnu-toolchain-downloads)

```shell
export TARGET_COMPILE=aarch64-none-elf-
cd kernel
export ANDROID=1 # Android version, including support for the 'su' command
make
```

## 编译kptools

kptools可以在任何地方运行，只需编译即可。

- 使用`Makefile`配置编译

```shell
export ANDROID=1
cd tools
make
```

- 使用`CMake`配置编译

```shell
cd tools
mkdir build
cd build
cmake ..
make
```

## 编译kpatch


kpatch在目标系统的用户空间中运行，因此您可以像往常一样构建它。
如果你在Android上使用它，你可以使用AndroidKernelPatch。

- 使用 Makefile

```shell
cd user
make
```

- 使用 CMake

```shell
cd user
mkdir build
cd build
cmake ..
make
```

- 为Android系统编译

```shell
export ANDROID_NDK=/path/to/ndk
export ANDROID=1
cd user
mkdir -p build/android && cd build/android
cmake -DCMAKE_TOOLCHAIN_FILE=$ANDROID_NDK/build/cmake/android.toolchain.cmake \
    -DCMAKE_BUILD_TYPE=Release \
    -DANDROID_PLATFORM=android-33 \
    -DANDROID_ABI=arm64-v8a ../..
cmake --build .
```

## 编译KPM(KernelPatch Module)

示例:

```shell
export TARGET_COMPILE=aarch64-none-elf-
cd kpm-demo/hello
make
```


