## Installation of prerequisites for cdk-minishift-testsuite
### MacOS
#### Avocado
To successfully install and run Avocado several packages need to be installed:
 - pip
 - brew
 - libvirt
 - libvirt-python
 - pkg-config
 
Run following commands to install them:
 
```sh
sudo easy install pip
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" < /dev/null 2> /dev/null
brew install libvirt
brew install pkg-config
sudo pip install libvirt-python
```
To install Avocado run:
```sh
git clone https://github.com/avocado-framework/avocado.git
cd avocado
sudo python setup.py install 
```
In systems with MacOS version 10.11+ installation there is possibility that last command will end with following error:
```
error: could not create '/usr/share/avocado': Operation not permitted
```
To overcome this issue SIP (System Integrity Protection), which protects /usr/share folder even for sudo users, needs to be disabled on this system. After reboot to recovery mode run this command:
```
crsutil disable
```
