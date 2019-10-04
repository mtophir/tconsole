# tconsole

This is an aggregated Console to view the status of servers and applications running in Tomcat/TomEE instances.

Pre-requisite
1. Deploy ROOT in webapp
2. Deploy manager in webapp
   Update META-INF/context.xml in manager and comment out RemoteAddrValve like
   '<!--
   <Valve className="org.apache.catalina.valves.RemoteAddrValve"
         allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" />
   -->'
   or if you want to allow a specific IP like 10.11.12.13 to access it
   '<Valve className="org.apache.catalina.valves.RemoteAddrValve"
         allow="10\.11\.12\.13" />'
3. Deploy psi-probe in webapp. Link: [Githib.com] (https://github.com/psi-probe/psi-probe)

