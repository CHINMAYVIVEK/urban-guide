# Build and install Filezilla 3.47.1 from source:
Install the prerequisites for installing from source:

``sudo apt install build-essential wx-common libpugixml-dev libsqlite3-dev libwxgtk3.0-dev nettle-dev gnutls-bin libgnutls28-dev libdbus-1-dev libdbus-glib-1-dev libgtk2.0-dev
 ``

***Download libfilezilla-0.20.1(latest) that is needed from [here](https://lib.filezilla-project.org/download.php). 
NOTE: Only libfilezilla-0.11.0 is available in the Ubuntu 18.04 LTS repositories.***

Then extract, build and install:

* `` tar -xvjf libfilezilla-0.20.1.tar.bz2 ``
* ``cd libfilezilla-0.20.1/``
* ``./configure``
* ``make``
* ``sudo make install ``

***Now get the source for Filezilla 3.47.1(latest) from [here](https://filezilla-project.org/download.php?show_all=1) Then extract, build and install:***

* `` tar -xvjf FileZilla_3.47.1_src.tar.bz2`` 
* ``cd filezilla-3.47.1/``
* ``./configure``
* ``make``
* ``sudo make install ``

***With the lib installs you might get the following message if it doesn't start:***

___``filezilla: error while loading shared libraries: libfilezilla.so.0: cannot open shared object file: No such file or directory``___

## To fix it, simply run

`` sudo ldconfig ``
