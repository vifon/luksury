luksury
=======

LUKS+LVM mounting script

SYNOPSIS
--------

    luksury [OPTIONS]

DESCRIPTION
-----------

`luksury` is a simple script mounting your LUKS-encrypted LVM volumes
in a fast and easy way. It allows you to access the LUKS volume,
activate the LVM virtual group inside and mount the LVM logical
volumes in a single command. And then unmount all of this in a second
one.

Currently there is no support for more than one LUKS volume.

CONFIGURATION
-------------

`luksury` uses a single configuration file:
`~/.config/luksury/luksury.sh` (actually it's a full-fledged shell
script but that's not important most of the time), which looks like this:

    export LUKS_UUID=[your uuid]
    export LUKS_KEYFILE=[file path]
    export LUKS_NAME=[arbitrary name]

    export LVM_VG=[vg name]
    export LVM_MOUNTS=[space-separated arguments for mount]

The devices and/or mountpoints specified in `LVM_MOUNTS` should be
configured in your `/etc/fstab` so that `mount(1)` will know what to
do exactly.

OPTIONS
-------

* `-d`/`-u` -- unmount instead of mounting
* `-w` -- mount, wait for Enter and unmount
* `-k` -- ignore all errors and keep going

AUTHOR
------

Wojciech 'vifon' Siewierski < wojciech dot siewierski at onet pl >

COPYRIGHT
---------

Copyright (C) 2015  Wojciech Siewierski

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
