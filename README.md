gtk-wayland-textinputv1
=======================

What's this?
------------

An input method module for GTK3 to support Wayland's text-input-unstable-v1
protocol. Although GTK3 includes 2 IM modules to support Wayland:

* im-wayland.so (text-input-unstable-v3 protocol)
* im-waylandgtk.so (gtk-text-input protocol)

both of them don't support text-input-unstable-v1 protocol. So that they aren't
usable on Weston which supports only v1 protocol.

This module enables text input in GTK apps on Weston or any other Wayland
compositors which support text-input-unstable-v1.

How to build & install from source code
-----------------------------

```console
$ ./configure
$ make
$ make install
```

Then you need to update immodules.cache in your system.
Here is an example to do this on Ubuntu 22.04, but the path of the command &
immodules.cache are depends on your system:

```console
$ /usr/lib/x86_64-linux-gnu/libgtk-3-0/gtk-query-immodules-3.0 > /usr/lib/x86_64-linux-gnu/gtk-3.0/3.0.0/immodules.cache
```

How to run GTK applications with this module
-----------------------------

You need to set the enviroment variable `GTK_IM_MODULE=wltextinputv1` to enable this module.
e.g.)
```console
$ GTK_IM_MODULE=wltextinputv1 gtk3-demo
```
