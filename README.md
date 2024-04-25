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

How to build from source code
-----------------------------

```
$ ./configure
$ make
$ make install
```
