# Syncthing for CentOS

## RPM Install

```
yum install https://github.com/mlazarov/syncthing-centos/releases/download/v0.13.1/syncthing-0.13.1-0.el7.centos.x86_64.rpm
```


## RPM Build


#### Install rpmbuild requirements

```
yum install -y yum-utils vim rpm-build rpmdevtools redhat-rpm-config make gcc gcc-c++ git
```


### Clone the repo and build rpm package

```
cd ~
git clone https://github.com/mlazarov/syncthing-centos.git rpmbuild/
mkdir -p ~/rpmbuild/{BUILD,RPMS,SOURCES,SPECS,SRPMS}
echo '%_topdir %(echo $HOME)/rpmbuild' > ~/.rpmmacros
cd rpmbuild/SPECS/
rpmbuild -bb syncthing.spec
```

### Start  syncthing systemd service

```
sudo systemctl start syncthing@<username>
```

You can now access the GUI through this URL: 
http://localhost:8080
