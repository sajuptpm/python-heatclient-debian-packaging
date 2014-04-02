python-heatclient-debian-packaging
==================================

python heatclient debian packaging script


How to Jenkins Create a Debian Package for OpenStack python-heatclient
========================================================================

a)
Get debian packaging script for python-heatclient project.
#sudo apt-get install devscripts

Goto following link and locate your project's *.dsc file
http://ubuntu-cloud.archive.canonical.com/ubuntu/pool/main/

Download the packaging script and extract it
#dget http://ubuntu-cloud.archive.canonical.com/ubuntu/pool/main/p/python-heatclient/python-heatclient_0.2.8-0ubuntu1~cloud0.dsc
#tar -xzf python-heatclient_0.2.8-0ubuntu1~cloud0.debian.tar.gz
#cd debian
#ls

b)
Clone the source code of python-heatclient
#git clone https://github.com/sajuptpm/python-heatclient.git
#cd python-heatclient

Create a new branch named "packaging" if not exist and switch to that branch.
#git checkout -b packaging

c)
Copy debian folder (packaging script) to "packaging" branch
#cp -r ../../debian .
#git status
#git add debian
#git commit debian
#git status

d)
Push packaging branch to remote to remote github repo
#git remote -v
#git push origin packaging

e)
Create build job in jenkins
