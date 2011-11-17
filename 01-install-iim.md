# Media Used :

RDz801Server.iso - From the IIMInstaller_Linux, extract the zip file, then
                   run 'sudo ./install' bringing you to IIM installer.

		   It's like windows : Next, Next Finish :)

		   I used default location of /opt/IBM/InstallationManager/eclipse

		   Then restart IIM, add the CD repository.config to the repo and go :)  


Install RD4z.

## Issue 01  : (see issue01.png). 
libstdc++so.5 or libstd++s0.6 not in system library path :(

    henri@inst:~/setuplog$ sudo apt-get install libstdc++6
    [sudo] password for henri: 
    Reading package lists... Done
    Building dependency tree       
    Reading state information... Done
    libstdc++6 is already the newest version.
    0 upgraded, 0 newly installed, 0 to remove and 186 not upgraded.
    henri@inst:~/setuplog$ sudo apt-get install lib32stdc++6
    Reading package lists... Done
    Building dependency tree       
    Reading state information... Done
    lib32stdc++6 is already the newest version.
    lib32stdc++6 set to manually installed.
    0 upgraded, 0 newly installed, 0 to remove and 186 not upgraded.

Not working :LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/lib32:/usr/lib32
             export LD_LIBRARY_PATH

Not working : ln -s /usr/lib32/libstdc++.so.6 /usr/lib32/libstdc++.so

Working!!!!   sudo ln -s /usr/lib32/libstdc++.so.5 /usr/lib/libstdc++.so.5
Moved to 00-file
