### **Install jdk 7u71 in Ubuntu 14.04**
---

##### **Download jdk from the given url and extract:**

[Click Here to download JDK7 from Oracle](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html)

```sh
sudo tar xvzf jdk-7u71-linux-x64.tar.gz
```

##### **Move the extracted file to /usr/local/java:**

```sh
sudo mv jdk1.7.0_71 /usr/local/java
```

##### **Edit the system path file:**

```sh
sudo vi /etc/profile
```

##### **Scroll down to the end of the file using the arrow keys and add the following lines below to the end of your /etc/profile file:**

```sh
JAVA_HOME=/usr/local/java/jdk1.7.0_71
JRE_HOME=$JAVA_HOME/jre
PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin
export JAVA_HOME
export JRE_HOME
export PATH
```
> Save the /etc/profile file and exit.

##### **Inform your Ubuntu linux system where your oracle jdk is located:**

* This will tell the system that the new version of Java Oracle is available for use

```sh
sudo update-alternatives --install "/usr/bin/java" "java" "/usr/local/java/jdk1.7.0_71/jre/bin/java" 1
```

* This command notifies the Oracle Java JDK is available for use

```sh
sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/local/java/jdk1.7.0_71/bin/javac" 1
```

##### **Inform your Ubuntu linux System that Oracle Java JDk must be the default Java:**

```sh
sudo update-alternatives --set java /usr/local/java/jdk1.7.0_71/jre/bin/java
```

* This command will set the java compiler for the system

```sh
sudo update-alternatives --set javac /usr/local/java/jdk1.7.0_71/bin/javac
```

##### **Reload your system wide PATH /etc/profile by typing the following command:**

```sh
. /etc/profile
```
##### **Check a version, using the below command:**

```sh
java -version
```

License
----

MIT