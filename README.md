gtk-wayland-textinputv1
=======================

What's this?
------------

An input method module for GTK3 to support Wayland's text-input-unstable-v1
protocol. Although GTK3 includes 2 IM modules to support Wayland:

* im-wayland.so (text-input-unstable-v3 protocol)
* im-waylandgtk.so (gtk-text-input protocol)

both of them don't support text-input-unstable-v1 protocol. So that they aren't
usable on Wayland compositors which don't support v1 protocol such as Weston.

This module enables text input on such Wayland compositors.

How to build from source code
-----------------------------

```
$ ./configure
$ make
$ make install
```
