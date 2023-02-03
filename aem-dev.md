## Build-Deploy

```shell
pareventVersion=$(grep --max-count=1 '<version>' ~/codes/dep-project/master/pom.xml | awk -F '>' '{ print $2 }' | awk -F '<' '{ print $1 }');  mvn clean install -PautoInstallSinglePackage -Ddep-project.version=$pareventVersion -e -Dmaven.test.skip -Djacoco.skip=true;
```

## Start AEM Instance
```shell
cd ~/codes/aem;
java -jar aem-author-p4502.jar -fork -forkargs -- -Xdebug -Xrunjdwp:transport=dt_socket,address=30303,suspend=n,server=y -Xmx1520m > /dev/null 2>&1 &
```

## Stop AEM Instance
```shell
kill -9 $(pgrep -f 'aem-author');
```
## Open Chrome with Security Disabled
```shell
open -n -a /Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --args --user-data-dir="/Users/me/tmp/chrome_dev" --disable-web-security
```

## Auto Copy Text
```bash
#!/bin/bash
echo -n "YOUR-TEXT-HERE==" | base64 -d | base64 -d | pbcopy

exit 0;
```


## IntelliJ Shell Script


clean/remove old folders
```bash
folderPath="yaya/NC-active"; rm -rf ~/codes/$folderPath/*/target; rm -rf  ~/codes/$folderPath/ui.frontend/node;  rm -rf  ~/codes/$folderPath/ui.frontend/node_modules; rm -rf  ~/codes/$folderPath/ui.frontend/package-lock.json;
```

recorrect-ports
```bash
folderPath="yaya/NC-active"; old_value="<aem.port>80<\/aem.port>";new_value="<aem.port>4502<\/aem.port>"; find ~/codes/$folderPath -name 'pom.xml' -type f -exec sed -i -e  "s#$old_value#$new_value#g" {} +; folderPath="norton/NC-active/ui.frontend"; old_value="target: 'http://local.norton.com'";new_value="target: 'http://localhost:4502'"; 
find ~/codes/$folderPath -name 'webpack.dev.js' -type f -exec sed -i -e  "s#$old_value#$new_value#g" {} +; find ~/codes/$folderPath -name 'webpack.dev.js' -type f -exec sed -i -e  "s#allowedHosts#//allowedHosts#g" {} +; find ~/codes/$folderPath -name 'webpack.dev.js' -type f -exec sed -i -e  "s#host: #//host: #g" {} +; find ~/codes/$folderPath -name 'webpack.dev.js' -type f -exec sed -i -e  "s#port: 80,#port: 8080,#g" {} +;
```
