<!--
    This Source Code Form is subject to the terms of the Mozilla Public
    License, v. 2.0. If a copy of the MPL was not distributed with this
    file, You can obtain one at http://mozilla.org/MPL/2.0/.
-->

<!--
    Copyright 2019 Joyent, Inc.
-->

# sdc-scripts

This repository is part of the Joyent Triton project. See the [contribution
guidelines](https://github.com/joyent/triton/blob/master/CONTRIBUTING.md)
and general documentation at the main
[Triton project](https://github.com/joyent/triton) page.

The files/scripts here are used for configuring sdc zones.  Currently used are:

* setup.sh: called once when first setting up the zone.
* configure.sh: called on every zone boot.
* lib/util.sh: contains common functions for setting up SDC zones.
* etc/root.bashrc: will be loaded as /root/.bashrc in SDC zones.

The files in the sdc-scripts.git repo are copied in first and then the files
in the zone's `<repo>.git/boot` directory are copied over.  This way the
sdc-scripts.git files act as defaults but the zone can (and must in the case
of setup.sh and configure.sh) use its own files.

## package.json

This repo includes a package.json even though it isn't a Node.js package.
It is used to hold a version. At the time of writing that version isn't
used for anything but manually reading.
