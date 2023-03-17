# Mutiny

GTK4 Revolt client

## Installation

The following components are required beforehand:

* (The meson build system)[https://mesonbuild.com/Quick-guide.html]
* (The Rust toolchain)[https://www.rust-lang.org/tools/install]
* (The GTK4 library)[https://github.com/ToshioCP/Gtk4-tutorial/blob/main/gfm/sec2.md]
* (The Adwaita library)[https://github.com/GNOME/libadwaita]

It's then essential to setup the build directory with meson:
```sh
meson setup builddir
```

Once this is succesful; It's then proper to perform the compilation procedure:
```sh
cd builddir && meson compile
```

Unfortunely, in some cases it is difficult to utilize `meson install` properly. In this case the user can just specify the prefix to the current build directory:
```sh
# inside builddir
meson configure -D`pwd`
```

When this is done, the resources will be located inside the `share` folder on the build directory.

If not installing the program with `meson install` then it is nescesary to notify glib of the schemas residing inside the `data/` folder; so the client shall be run as:
```sh
# inside builddir
XDG_DATA_DIRS="$XDG_DATA_DIRS:$PWD/share" ./src/mutiny 
```

## Useful References

https://world.pages.gitlab.gnome.org/Rust/libadwaita-rs/stable/latest/docs/libadwaita/
