========================
 How to build PSI Probe
========================

1. Check out or download PSI Probe's source code.

   You may acquire it from the following URL:
   https://github.com/padcom/psi-probe

2. Install Maven 2.

   You may download it from the following URL:
   http://maven.apache.org

3. Create the required ojdbc14 Maven artifact.

   Oracle's JDBC drivers are protected by the OTN (Oracle Technology Network)
   Development and Distribution License.  For this reason, the .jar cannot be
   legally hosted in any Maven repository or distributed with PSI Probe.

   a. Download version 10.2.0.5.0 of the ojdbc14.jar.

      You may download it from the following URL:
      http://www.oracle.com/technetwork/database/enterprise-edition/jdbc-10201-088211.html

   b. Locate the ojdbc14-pom.xml file (where this readme.txt file resides).

   c. Install ojdbc14.jar as a Maven artifact.

      Execute the following command:
      mvn install:install-file \
      -Dfile=/path/to/ojdbc14.jar \
      -DpomFile=/path/to/ojdbc14-pom.xml
      
4. Prepare Oracle UCP dependencies
  * Download ucp.jar from this URL:
    http://www.oracle.com/technetwork/database/enterprise-edition/downloads/ucp-112010-099129.html
  * create a ucp-pom.xml 
  * Install ucp.jar to Maven's local repository
    
5. Prepare JMXRMI 1.2.1 dependencies (found only pom from public maven repository)
  * Download jmxrmi.jar from this URL:
    http://www.oracle.com/technetwork/java/javasebusiness/downloads/java-archive-downloads-java-plat-419418.html#7657-jmx-1.2.1-oth-JPR
    
  * create a jmxri-1.2.1-pom.xml
  * Install jmxrmi.jar to Maven's local repository 
  
6. Run Maven.

   Execute the following command from the PSI Probe base directory (where this
   readme.txt file resides):
   mvn package

   This will create probe.war in web/target.
