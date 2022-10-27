# Setup Java 
https://www.oracle.com/java/technologies/javase/jdk11-archive-downloads.html

# Setup Maven
- download maven via https://maven.apache.org/install.html
- move maven to ~/apps/apache/maven/x.x.x

# Setup Git
can install via xcode

# Add maven to path to profile

- ```vim ~/.zshrc```
- add below text
```
export PATH=/Users/me/apps/apache/maven/3.8.6/bin:$PATH
JAVA_HOME=`/usr/libexec/java_home -v 11`
export PATH=$JAVA_HOME/bin:$PATH
```

# Add default Java version to profile
- ```vim ~/.zprofile```
- add below text
```
export JAVA_HOME="$(/usr/libexec/java_home -v 11)"
export PATH="$HOME/.daml/bin:$PATH"
```
