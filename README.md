<h2>Hibersap Plugin for Forge</h2>


A plugin to generate classes to get used by the Hibersap framework to connect to a SAP system.

The plugin allows to search for function names at a given SAP system and generates all required classes and configuration files to use the given function with the Hibersap framework.

You can find more information about Hibersap at http://hibersap.sourceforge.net/

This plugin is licensed under LGPL, like Forge and Hibersap

<h2>How to use - shortcut</h2>
You will find:
- the according jboss forge version as ZIP in src/main/resources
- the sapjco3.jar of version 3.0.10 in src/main/resources

1. Install sapjco3 jar to your local Maven repository from the command line (to be found of the plugin POM): 


	mvn install:install-file -DgroupId=com.sap -DartifactId=sap-jco -Dversion=3.0.10 -Dpackaging=jar -Dfile=src/main/resource/sapjco3.jar

2. clean and build hibersap-plugin
3. Unzip forge
4. Run forge and install plugin


	forge source-plugin <path-to-plugin>

5. To use the plugin read the following blogposts: 

Also read the akquinet blogpost and watch the screen-cast that shows the usage of the Hibersap-Forge-Plugin:

* <a href="http://blog.akquinet.de/2012/07/12/use-jboss-forge-to-generate-hibersap-classes-calling-sap-functions/">Use JBoss Forge to generate Hibersap Classes that call SAP Functions</a>
* <a href="http://vimeo.com/45260307">JBoss Forge Hibersap Plugin Screencast</a> from <a href="http://vimeo.com/user12377452">mxsb</a> on <a href="http://vimeo.com">Vimeo</a>


<h2>How to use - official ;-)</h2>


This plugin is using Hibersap, which is using the SAP Java Connector (JCo).<br>
Before using download SAP Java Connector 3 (http://service.sap.com/connectors) and extract the sapjco3.jar and the sapjco3 native library.<br>

Install sapjco3 jar to your local Maven repository from the command line: 

	mvn install:install -file -DgroupId=com.sap -DartifactId=sap-jco -Dversion=3.0.7 -Dpackaging=jar -Dfile= sapjco3.jar 


* Create or use an existing a Maven project (project may be created with Forge from the command line).
* Navigate into the project
* Set your session manager name and connection properties
* Use the generate-sap-entities command to connect to your SAP system and generate Java classes which are used by Hibersap. 

Also read the akquinet blogpost and watch the screen-cast that shows the usage of the Hibersap-Forge-Plugin:

* <a href="http://blog.akquinet.de/2012/07/12/use-jboss-forge-to-generate-hibersap-classes-calling-sap-functions/">Use JBoss Forge to generate Hibersap Classes that call SAP Functions</a>
* <a href="http://vimeo.com/45260307">JBoss Forge Hibersap Plugin Screencast</a> from <a href="http://vimeo.com/user12377452">mxsb</a> on <a href="http://vimeo.com">Vimeo</a>

<h2>Commands</h2>


[list-properties] - Lists all connection properties and the current session manager name.

[set-property] - Sets a new or existing property<br>
[OPTIONS]<br>
[--key] - The property key<br>
[--value] - The property value

[delete-property] - Deletes an existing property<br>
[OPTIONS]<br>
[--key] - The property key<br>

[generate-sap-entities] - Defalt command; generates SAP entities from a SAP system<br>
[OPTIONS]<br>
[--name-pattern] - Pattern to search SAP function names. Use * and ? as wildcards.<br>
[--max-results] - Number of max. results. Use 0 for unlimited result list (Default value is 20)
