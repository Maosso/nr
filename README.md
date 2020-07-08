---


---

<h2 id="configure-apm-agents-backend-services">Configure APM agents (backend services)</h2>
<p><a href="https://docs.newrelic.com/docs/agents/java-agent/additional-installation/install-new-relic-java-agent-docker#app-name">reference</a></p>
<ol>
<li>change license key and app name in <code>newrelic.yml</code></li>
<li>add <code>JAVA_OPTS="$JAVA_OPTS -javaagent:path/newrelic.jar</code> to <code>catalina.sh</code></li>
<li>in <code>/usr/local/apache.../bin</code>, give tomcat ownership of <code>newrelic.jar</code> with <code>chown tomcat:tomcat *.*</code></li>
<li>then run <code>sh catalina.sh run</code></li>
<li>go to <a href="https://rpm.eu.newrelic.com/accounts/YOURACCOUNT/applications;">https://rpm.eu.newrelic.com/accounts/YOURACCOUNT/applications;</a> your app will be listed there as a monitored service in the New Relic APM.</li>
</ol>
<p><img src="https://github.com/Maosso/nr/blob/master/APM%20app.png" alt="your app listed"></p>
<p><img src="https://github.com/Maosso/nr/blob/master/transactions_host.png" alt="server response times"></p>

