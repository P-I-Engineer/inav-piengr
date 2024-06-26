# Building with Vagrant

> **On Windows building with this method is not advised and should be used only if Windows Linux Subsystem can not be used. In all other cases all Windows users should be using Linux Subsystem (WSL) instead**

Setting up build environment with Vagrant is remarkably simple, but you still need to have some basic knowlage of your OS.

## Installing Vagrant
Vagrant needs some kind of virtualization software to run, i.e. VirtualBox.
You can get VirtualBox from here:
```
https://www.virtualbox.org/wiki/Downloads
```

Download and install Vagrant for you OS from here:
```
https://www.vagrantup.com/downloads.html
```

## Cloning INAV repository
Using git (The preferred way!)
```
git clone https://github.com/iNavFlight/inav.git
```

Or download the .zip file from
```
https://github.com/iNavFlight/inav
```
and extract it to folder of your choosing.

## Running the virtual machine
Open up a terminal or command line interface (In windows search for CMD.exe and run it as administrator!)
Navigate in to the directory of your cloned/unzipped INAV repository. (Where the "Vagrantfile" is located.) and start the virtual machine.
```
vagrant up
```

Starting the virtual machine might take some time depending on your computer speed.
When you start the virtual machine for the first time, it has to download the base virtual machine files and do some installation steps, 
so it takes longer than the following times you start it.


When the start up has finished succesfully and you are back to your command prompt. Login in to the virtual machine.
```
vagrant ssh
```

## Building firmware
In the virtual machine, go to the INAV directory
```
cd inav
```

If you downloadet the repository as a zip file, you may have to type:
```
git init
```

To stop the file system boundary warnings.

Build your desired target
i.e.
```
make TARGET=AIRBOTF4
```

## Updating and rebuilding the firmware

```
git reset --hard
git pull
make clean TARGET=AIRBOTF4
make TARGET=AIRBOTF4
```

## Additional virtual machine commands

Exit from the virtual machine interface with:
```
exit
```

Shutdown the virtual machine with:
```
vagrant halt
```

Remove the virtual machine files from your computer with:
```
vagrant destroy
```
