## mvn command to build sonar using coverage profile
```
mvn clean install -Pcoverage,adobe-public -Dsonar.host.url=$SONARQUBE_URL -Dsonar.login=$SONARQUBE_TOKEN -Dsonar.scm.disabled=true -Dsonar.projectVersion=$BUILD_VER
```
## mvn commoand to code build along with sonar scan
```
mvn clean install -Padobe-public,autoInstallPackage,autoInstallPackagePublish -Dsonar.host.url=$SONARQUBE_URL -Dsonar.login=$SONARQUBE_TOKEN -Dsonar.scm.disabled=true -Daem.host=$INSTANCE_IP -Daem.port=4502 -Daem.publish.host=$INSTANCE_IP -Daem.publish.port=4503 -Dvault.user=admin -Dvault.password=$AEM_ADMIN_PASSWORD -Dsling.user=admin -Dsling.password=$AEM_ADMIN_PASSWORD
```
