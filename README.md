# tconsole

This is an aggregated Console to view the status of servers and applications running in Tomcat/TomEE instances.

### Pre-requisite
1. Deploy ROOT in webapp
2. Deploy manager in webapp.
   Update META-INF/context.xml in manager and comment out RemoteAddrValve like 
   
   `<!--
   <Valve className="org.apache.catalina.valves.RemoteAddrValve"
         allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" />
   -->`
   
   This would allow any IP to access the manager. For security, you can
   specify a certain IP like 10.11.12.13 to limit the access to that IP only.
   
   `<Valve className="org.apache.catalina.valves.RemoteAddrValve"
         allow="10\.11\.12\.13" />`

3. Deploy psi-probe in webapp. [Link to PSI-Probe](https://github.com/psi-probe/psi-probe)

### User configuration
To access tconsole, a user would need an id and password to login. Specify the users and passwords in users.conf

The format is name,password\n
Example of users.conf:\n
#name, password (comment line)\n
guest,guest123

The user name and password has to be specified in tomcat-users.xml with a **"manager-script"** role.

### Server configuration
