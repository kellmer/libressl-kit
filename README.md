# libressl-kit

My personal libressl-kit for funtoo
Here I host all packages I need to use my funtoo system with libressl

## Install

```
# cd /var/git/
# git clone https://github.com/kellmer/meta-repo
# cd meta-repo
# git submodule update --init
# chown portage:portage -R /var/git/meta-repo/
```

Make sure you set the libressl and the ssl USE flag gloably in /etc/portage/make.conf

Now unmerge openssl and install libressl, but befor you go, you should download libressl
```
emerge -f libressl
emerge --unmerge openssl
emerge libressl
```

The current funtoo branch will install a iputils version which is not libressl compatible.
So we need to unmask the newer version
```
# cat /etc/portage/package.unmask/iputils.unmask                                                                             
>net-misc/iputils-20121221-r2                 
```
