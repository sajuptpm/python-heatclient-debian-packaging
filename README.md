How to Jenkins Create a Debian Package for OpenStack python-heatclient
----------------------------------------------------------------------

1.
Get debian packaging script for python-heatclient project.
<p>
<code>sudo apt-get install devscripts </code>
</p>

2.
Goto following link and locate your project's *.dsc file
<p>
http://ubuntu-cloud.archive.canonical.com/ubuntu/pool/main/
</p>

3.
Download the packaging script and extract it
<p><code>
dget http://ubuntu-cloud.archive.canonical.com/ubuntu/pool/main/p/python-heatclient/python-heatclient_0.2.8-0ubuntu1~cloud0.dsc
</code></p>

<p><code>
tar -xzf python-heatclient_0.2.8-0ubuntu1~cloud0.debian.tar.gz
</code></p>

<p><code>
cd debian
</code></p>

<p><code>
ls
</code></p>

4.
Clone the source code of python-heatclient
<p><code>
git clone https://github.com/sajuptpm/python-heatclient.git
</code></p>

<p><code>
cd python-heatclient
</code></p>

5.
Create a new branch named "packaging" if not exist and switch to that branch.
<p><code>
git checkout -b packaging
</code></p>

6.
Copy debian folder (packaging script) to "packaging" branch
<p><code>
cp -r ../../debian .
</code></p>

<p><code>
git status
</code></p>

<p><code>
git add debian
</code></p>

<p><code>
git commit debian
</code></p>

<p><code>
git status
</code></p>

7.
Push packaging branch to remote to remote github repo
<p><code>
git remote -v
</code></p>

<p><code>
git push origin packaging
</code></p>

8.
Create build job in jenkins
