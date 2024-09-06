# KernelPatch

**仅使用剥离的 Linux 内核映像修补和挂接 Linux 内核。**

``` shell
 _  __                    _ ____       _       _     
| |/ /___ _ __ _ __   ___| |  _ \ __ _| |_ ___| |__  
| ' // _ \ '__| '_ \ / _ \ | |_) / _` | __/ __| '_ \ 
| . \  __/ |  | | | |  __/ |  __/ (_| | || (__| | | |
|_|\_\___|_|  |_| |_|\___|_|_|   \__,_|\__\___|_| |_|

```

- 获取所有 symbol 信息，不含源码和 symbol 信息。
- 将任意代码注入内核。（静态修补内核映像或运行时动态加载）。
- 提供 kernel function inline hook 和 syscall table hook。
- 适用于 Android 的其他 SU。

如果您使用的是 Android，[APatch]（https://github.com/bmax121/APatch） 将是更好的选择。

## 要求

CONFIG_KALLSYMS=y  

## 支持的版本

目前仅支持 arm64 架构。 

Linux 3.18 - 6.2（理论上） 
Linux 6.3+（尚未适应） 

## 参与其中

## 更多信息

[文档地址](./doc/)

## Credits

- [vmlinux-to-elf](https://github.com/marin-m/vmlinux-to-elf): Some ideas for parsing kernel symbols.
- [android-inline-hook](https://github.com/bytedance/android-inline-hook): Some code for fixing arm64 inline hook instructions.
- [tlsf](https://github.com/mattconte/tlsf): Memory allocator used for KPM. (Need another to allocate ROX memory.)

## License

KernelPatch is licensed under the **GNU General Public License (GPL) 2.0** (<https://www.gnu.org/licenses/old-licenses/gpl-2.0.html>).
