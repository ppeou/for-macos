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
## Open Chrome with Security Disabled
```shell
open -n -a /Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --args --user-data-dir="/Users/Piseth.Peou/tmp/chrome_dev" --disable-web-security
```

## Auto Copy Text
```bash
#!/bin/bash
echo -n "YOUR-TEXT-HERE==" | base64 -d | base64 -d | pbcopy

exit 0;
```
