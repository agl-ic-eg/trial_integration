# How to build

Each local.conf and bblayers.conf is included in this repo.  Please clone this repo. to local.  


## host
The host is based on minimal agl qm env.  It's now developing.  

### Create local tree  

repo init -u https://github.com/AGLExport/trial_integration.git -b working -m host.xml  

### Install eva binary  
Ref To :  
https://github.com/renesas-rcar/meta-renesas/blob/dunfell-dev/meta-rcar-gen3/README.evaproprietary.md  


### Setup build env.  
source poky/oe-init-build-env  
cp /path/to/thisrepo/trial_integration/hostconf/* conf/


### Build host 
bitbake host-image-minimal  


## dummy-guest  
The dummy guest is based on minimal agl ivi.  It's including many workarounds.  

### Create local tree  

repo init -u https://github.com/AGLExport/trial_integration.git -b working -m dummy-guest.xml  

### Install eva binary  
Ref To :  
https://github.com/renesas-rcar/meta-renesas/blob/dunfell-dev/meta-rcar-gen3/README.evaproprietary.md  


### Setup build env.  
source poky/oe-init-build-env  
cp /path/to/thisrepo/trial_integration/dummy-guestconf/* conf/


### Build dummy-guest  
bitbake core-image-minimal  


## cluster-guest  
The cluster guest is based on minimal agl qm env.  It's now developping.  

### Create local tree  

repo init -u https://github.com/AGLExport/trial_integration.git -b working -m cluster-guest.xml  

### Install eva binary  
Ref To :  
https://github.com/renesas-rcar/meta-renesas/blob/dunfell-dev/meta-rcar-gen3/README.evaproprietary.md  


### Setup build env.  
source poky/oe-init-build-env  
cp /path/to/thisrepo/trial_integration/cluster-guestconf/* conf/


### Build dummy-guest  
bitbake guest-ic-image-minimal  



# How to install  

cd /path/to/sdcard

tar xvjf /path/to/host/deploydir/host-image-minimal-h3ulcb.tar.bz2  

cd /path/to/sdcard/opt/guests/cluster-guest/  

tar xvjf /path/to/host/deploydir/guest-ic-image-minimal-h3ulcb.tar.bz2  

cd /path/to/sdcard/opt/guests/dummy-guest/ 

tar xvjf /path/to/host/deploydir/core-image-minimal-h3ulcb.tar.bz2  


# How to run  

Booting H3 SK.  

Login.  

lxc-start -n cluster-guest  
lxc-start -n dummy-guest  

When you want to login cluster-guest,  
lxc-attach -n cluster-guest  


