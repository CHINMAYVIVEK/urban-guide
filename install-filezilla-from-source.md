# Build and install Filezilla 3.48.0 from source Ubuntu 20.04 LTS:

Install the prerequisites for installing from source:

``sudo apt install build-essential wx-common libpugixml-dev libsqlite3-dev libgtk-3-dev nettle-dev gnutls-bin libgnutls28-dev libdbus-1-dev libdbus-glib-1-dev libgtk2.0-dev
 ``

***Download libfilezilla-0.21.0(latest) that is needed from [here](https://lib.filezilla-project.org/download.php).***

Then extract, build and install:

* `` tar -xvjf libfilezilla-0.21.0.tar.bz2 ``
* ``cd libfilezilla-0.21.0/``
* ``./configure``
* ``make``
* ``sudo make install ``

***Now get the source for Filezilla 3.48.0(latest) from [here](https://filezilla-project.org/download.php?show_all=1) Then extract, build and install:***

* `` tar -xvjf FileZilla_3.48.0_src.tar.bz2`` 
* ``cd filezilla-3.48.0/``
* ``./configure``
* ``make``
* ``sudo make install ``

___``filezilla: might shows error for wxWidget while installing Filezilla {ubuntu 20.04 LTS required wxWidget 3.0.x}``___  
 checking for wx-config... no   
configure: error:  
        wxWidgets must be installed on your system   
        but either the wx-config script couldn't be found or  
        no compatible wxWidgets configuration has been installed.  
</br>
        Compatible wxWidgets configurations are the unicode builds  
        of wxGTK, wxMac and wxMSW.  
</br>
        Please check that wx-config is in path, the directory  
        where wxWidgets libraries are installed (returned by  
        'wx-config --libs' command) is in LD_LIBRARY_PATH or  
        equivalent variable and wxWidgets version is 3.0.4 or above.  
## To fix it, Follow the instruction 
* get the source for wxWidget Latest Stable Release: 3.0.5 from [here](https://github.com/wxWidgets/wxWidgets/releases/download/v3.0.5/wxWidgets-3.0.5.tar.bz2)

* `` tar -xvjf wxWidgets-3.0.5.tar.bz2`` 
* `` cd ~/wxWidgets-3.0.5``
* ``mkdir gtk-build             # the name is not really relevant``
* ``cd gtk-build``
* ``../configure                # builds unicode, shared lib``
* ``make``
* ``sudo make install           # some platforms require to use 'su' instead of 'sudo'``
* ``sudo ldconfig               # not required in each system``

***With the lib installs you might get the following message if it doesn't start:***

___``filezilla: error while loading shared libraries: libfilezilla.so.0: cannot open shared object file: No such file or directory``___

## To fix it, simply run

`` sudo ldconfig ``
