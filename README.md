## Configure APM agents (backend services)
[reference](https://docs.newrelic.com/docs/agents/java-agent/additional-installation/install-new-relic-java-agent-docker#app-name)

1. change license key and app name in `newrelic.yml`
2. add `JAVA_OPTS="$JAVA_OPTS -javaagent:path/newrelic.jar` to `catalina.sh`
3. in `/usr/local/apache.../bin`, give tomcat ownership of `newrelic.jar` with `chown tomcat:tomcat *.*`
4. then run `sh catalina.sh run`
5. go to https://rpm.eu.newrelic.com/accounts/YOURACCOUNT/applications; your app will be listed there as a monitored service in the New Relic APM.

![your app listed](https://github.com/Maosso/nr/blob/master/APM%20app.png)

![server response times](https://github.com/Maosso/nr/blob/master/transactions_host.png)

## Deploy Infrastructure agents
for reference, go to https://infrastructure.eu.newrelic.com/accounts/YOURACCOUNT/install

create a configuration file
```
echo "license_key: eu01xxab1d00046e2b7a7853fad39227f13cNRAL" | sudo tee -a /etc/newrelic-infra.yml`
```
enable key
```
curl https://download.newrelic.com/infrastructure_agent/gpg/newrelic-infra.gpg | sudo apt-key add -
```
create agent's apt repo
```
printf "deb [arch=amd64] http://download.newrelic.com/infrastructure_agent/linux/apt bionic main" | sudo tee -a /etc/apt/sources.list.d/newrelic-infra.list
```
update apt cache and install the agent
```
sudo apt-get update
sudo apt-get install newrelic-infra -y
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY4NzIzOTAyMF19
-->