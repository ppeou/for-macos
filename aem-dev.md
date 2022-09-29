## Build-Deploy

```shell
pareventVersion=$(grep --max-count=1 '<version>' ~/codes/rinato/master/pom.xml | awk -F '>' '{ print $2 }' | awk -F '<' '{ print $1 }');  mvn clean install -PautoInstallSinglePackage -Drinato.version=$pareventVersion -e -Dmaven.test.skip -Djacoco.skip=true;
```

## Start AEM Instance
```shell
java -jar aem-author-p4502.jar -fork -forkargs -- -Xdebug -Xrunjdwp:transport=dt_socket,address=30303,suspend=n,server=y -Xmx1520m > /dev/null 2>&1 &
```

## Stop AEM Instance
```shell
kill -9 $(pgrep -f 'aem-author');
```
