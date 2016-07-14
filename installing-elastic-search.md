#Installing Elastic Search on UPOD's Vagrant Machine

```powershell
sudo apt-get update
sudo apt-get install openjdk-7-jre
java -version
```

Output of java -version

```powershell
java version "1.7.0_79"
OpenJDK Runtime Environment (IcedTea 2.5.6) (7u79-2.5.6-0ubuntu1.14.04.1)
OpenJDK 64-Bit Server VM (build 24.79-b02, mixed mode)
```
Add the Oracle Java PPA to apt:

	sudo add-apt-repository -y ppa:webupd8team/java

Update your apt package database:

	sudo apt-get update

Install the latest stable version of Oracle Java 8 with this command (and accept the license agreement that pops up):

	sudo apt-get -y install oracle-java8-installer

Lastly, verify it is installed:

	java -version

Step 2 — Downloading and Installing Elasticsearch

```
cd ~/
wget https://download.elastic.co/elasticsearch/elasticsearch/elasticsearch-1.7.2.deb
cd /vagrant
```
Then install it in the usual Ubuntu way with the dpkg command like this:

	sudo dpkg -i elasticsearch-1.7.2.deb

To make sure Elasticsearch starts and stops automatically with the Droplet, add its init script to the default runlevels with the command:

	sudo update-rc.d elasticsearch defaults

Add the following line to your `Vagrantfile`
	config.vm.provider "virtualbox" do |v|
	    v.memory = 1024
	end

Restart your Vagrant machine
```
logout
vagrant halt
vagrant up
vagrant ssh
```
